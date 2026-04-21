# Estrutura da planilha

Especificação das abas, colunas e fórmulas do Google Sheets que serve como ponto de partida da Fase 1.

A planilha é montada manualmente seguindo este documento. Não há automação.

## Abas

1. `Transações` — registro de tudo que entra e sai
2. `Contas` — saldo atual por conta
3. `Categorias` — lista de categorias (validação de dados)
4. `Dashboard` — visão consolidada (só leitura)

## Aba `Transações`

O coração da planilha. Toda entrada ou saída vira uma linha aqui.

| Coluna | Tipo | Observação |
|---|---|---|
| A — Data | Data | Data em que a transação aconteceu |
| B — Descrição | Texto | Como veio do extrato/fatura ou livre |
| C — Categoria | Texto | Validação de dados apontando pra aba `Categorias` |
| D — Valor | Número | Sempre positivo. O sinal vem do `Tipo` |
| E — Conta | Texto | Validação de dados apontando pra aba `Contas` |
| F — Tipo | Texto | `Receita`, `Despesa` ou `Transferência` |
| G — Mês | Fórmula | `=TEXT(A2;"YYYY-MM")` — facilita agrupar |

Transferência entre contas vira **duas linhas**: uma com `Tipo = Transferência` saindo da conta origem (valor sai do saldo dela) e outra com `Tipo = Transferência` entrando na conta destino. Descrição sugerida: `Transferência: Origem → Destino`.

## Aba `Contas`

| Coluna | Observação |
|---|---|
| A — Nome | `Nubank CC`, `Nubank Cartão`, `Santander`, `Mercado Pago` |
| B — Saldo Inicial | Saldo na data em que começar a controlar |
| C — Data Inicial | Data de referência do saldo inicial |
| D — Saldo Atual | Fórmula (ver abaixo) |

Fórmula sugerida para `Saldo Atual` (linha 2, ajustar para cada linha):

```
= B2
  + SUMIFS(Transações!D:D; Transações!E:E; A2; Transações!F:F; "Receita")
  - SUMIFS(Transações!D:D; Transações!E:E; A2; Transações!F:F; "Despesa")
  + SUMIFS(Transações!D:D; Transações!E:E; A2; Transações!F:F; "Transferência"; Transações!B:B; "*→ " & A2 & "*")
  - SUMIFS(Transações!D:D; Transações!E:E; A2; Transações!F:F; "Transferência"; Transações!B:B; A2 & " →*")
```

Alternativa mais simples (se não quiser depender do padrão da descrição): criar duas colunas extras em `Transações` — `Conta Origem` e `Conta Destino` — e ajustar as fórmulas. Para começar, a abordagem acima com descrição padronizada é suficiente.

### Cartão de crédito como conta separada

`Nubank Cartão` é uma conta como qualquer outra, mas o saldo costuma ficar **negativo** (representa dívida em aberto). Compras no cartão entram como `Despesa` na conta `Nubank Cartão`. Pagamento da fatura é uma **Transferência** `Nubank CC → Nubank Cartão`, que aproxima o saldo do cartão de zero.

Isso segue o padrão de YNAB/Copilot e evita contar a mesma despesa duas vezes (na compra e no pagamento da fatura).

## Aba `Categorias`

Uma única coluna com o nome das categorias. Usada como fonte de validação de dados na coluna `Categoria` de `Transações`. Ver `CATEGORIAS.md` para a lista inicial.

## Aba `Dashboard`

Visão consolidada e só leitura. Sugestão de blocos:

### Saldo por conta
Tabela puxando direto de `Contas` (colunas `Nome` e `Saldo Atual`) + linha de total.

### Mês corrente
Célula com o mês atual: `=TEXT(TODAY();"YYYY-MM")`. Serve de filtro pros blocos abaixo.

- **Receitas do mês**: `=SUMIFS(Transações!D:D; Transações!F:F; "Receita"; Transações!G:G; <célula do mês>)`
- **Despesas do mês**: mesma fórmula com `"Despesa"`
- **Resultado do mês**: `Receitas - Despesas`

### Gasto por categoria no mês
Usar tabela dinâmica ou `QUERY`:

```
=QUERY(Transações!A:G;
  "SELECT C, SUM(D)
   WHERE F = 'Despesa' AND G = '" & <célula do mês> & "'
   GROUP BY C
   ORDER BY SUM(D) DESC
   LABEL SUM(D) 'Total'"; 1)
```

## Ordem de criação

1. Criar `Categorias` (lista inicial de `CATEGORIAS.md`)
2. Criar `Contas` (com as 4 contas e saldos iniciais do dia em que for começar)
3. Criar `Transações` (vazia, com validações apontando pras abas acima)
4. Criar `Dashboard` por último, depois que tiver pelo menos algumas transações pra testar as fórmulas
