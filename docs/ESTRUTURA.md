# Estrutura dos arquivos

Especificação dos arquivos markdown que sustentam a Fase 1. A solução substitui a ideia original de Google Sheets/Excel porque conectar planilha ao Claude no iPad estava inviável.

Dois arquivos de dados na raiz do repositório:

1. `transacoes.md` — registro corrido de tudo que entra e sai
2. `contas.md` — saldo inicial por conta

Categorias ficam em `docs/CATEGORIAS.md` (referência, não dado).

Visão consolidada (saldos atuais, gasto por categoria, resumo do mês) é **calculada sob demanda** pelo Claude a partir dos dois arquivos — não existe arquivo de dashboard.

## Arquivo `transacoes.md`

Uma única tabela markdown. Toda entrada ou saída vira uma linha.

| Coluna | Tipo | Observação |
|---|---|---|
| Data | `YYYY-MM-DD` | Data em que a transação aconteceu |
| Descrição | Texto | Como veio do extrato/fatura, ou livre |
| Categoria | Texto | Uma das listadas em `CATEGORIAS.md`; `Transferência` para transferências |
| Valor | Número BR | Sempre positivo (`1.234,56`). O sinal vem do `Tipo` |
| Conta | Texto | Nome exato de uma conta em `contas.md` |
| Tipo | Texto | `Receita`, `Despesa` ou `Transferência` |

### Transferência entre contas próprias

Vira **duas linhas** — uma saindo da conta origem e outra entrando na destino. Mesma data, mesmo valor, descrição no padrão `Origem → Destino`. Exemplo de pagamento da fatura do cartão:

| Data | Descrição | Categoria | Valor | Conta | Tipo |
|---|---|---|---|---|---|
| 2026-04-15 | Nubank CC → Nubank Cartão | Transferência | 1.234,56 | Nubank CC | Transferência |
| 2026-04-15 | Nubank CC → Nubank Cartão | Transferência | 1.234,56 | Nubank Cartão | Transferência |

Dessa forma o saldo do `Nubank CC` diminui e o saldo do `Nubank Cartão` aproxima de zero.

### Ordem das linhas

Data crescente. Dentro do mesmo dia, não importa a ordem — só não misturar a ordem do arquivo ao longo do tempo (fica confuso pra revisar).

## Arquivo `contas.md`

Tabela com as contas monitoradas e o saldo inicial — o ponto de partida a partir do qual as transações em `transacoes.md` passam a contar.

| Coluna | Observação |
|---|---|
| Nome | `Nubank CC`, `Nubank Cartão`, `Santander`, `Mercado Pago` |
| Saldo Inicial | Saldo real na `Data Inicial` (formato BR) |
| Data Inicial | Data em que o controle começou |

### Cartão de crédito como conta separada

`Nubank Cartão` é uma conta como qualquer outra, mas o saldo costuma ficar **negativo** (dívida em aberto). Compras no cartão entram como `Despesa` na conta `Nubank Cartão`. Pagamento da fatura é uma `Transferência` `Nubank CC → Nubank Cartão`, que aproxima o saldo do cartão de zero.

Isso segue o padrão de YNAB/Copilot e evita contar a mesma despesa duas vezes (na compra e no pagamento).

## Como a visão consolidada é feita

Não há arquivo de dashboard. Para ver saldos e resumos, perguntar direto ao Claude:

- "Qual o saldo atual de cada conta?" — lê os dois arquivos e aplica: `Saldo Inicial + Receitas − Despesas + Transferências recebidas − Transferências enviadas`
- "Quanto gastei nesse mês por categoria?" — filtra `Tipo = Despesa` no mês e agrupa por `Categoria`
- "Qual o resultado do mês?" — `Receitas − Despesas` no mês

## Ordem de criação

1. Preencher `contas.md` (4 contas + saldo inicial + data inicial)
2. Garantir que `docs/CATEGORIAS.md` está atualizado (já vem populado)
3. `transacoes.md` começa vazia e vai sendo preenchida via workflow mensal (ver `WORKFLOW.md`)
