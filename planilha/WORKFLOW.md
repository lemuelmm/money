# Workflow mensal

Rotina pra manter a planilha atualizada. Ideia: gastar ~30 min por mês (ou 10 min por semana) registrando e conferindo.

## Setup inicial (uma vez)

1. Criar a planilha no Google Sheets seguindo `ESTRUTURA.md`
2. Popular `Categorias` com a lista de `CATEGORIAS.md`
3. Popular `Contas` com as 4 contas e **saldos iniciais** no dia de hoje:
   - `Nubank CC` — saldo da conta corrente
   - `Nubank Cartão` — **negativo** do valor da fatura em aberto (dívida)
   - `Santander` — saldo da conta corrente
   - `Mercado Pago` — saldo disponível
4. Deixar `Transações` vazia

A partir daqui, todas as transações novas (posteriores à data do saldo inicial) passam a ser registradas.

## Rotina mensal

Idealmente fazer uma vez por mês, logo depois de fechar a fatura do Nubank.

### 1. Importar fatura do Nubank (cartão)

1. No app do Nubank → fatura do cartão → exportar CSV
2. Abrir o CSV. As colunas típicas são: `date`, `title`, `amount`, `category` (categoria do Nubank — dá pra ignorar)
3. Copiar as linhas e colar em `Transações`, ajustando:
   - `Data` ← `date`
   - `Descrição` ← `title`
   - `Valor` ← `amount` (manter positivo)
   - `Conta` ← `Nubank Cartão` (preencher em todas)
   - `Tipo` ← `Despesa`
   - `Categoria` ← deixar em branco, vai ser preenchido no passo 2
4. Arrastar a fórmula do `Mês` pras novas linhas

### 2. Categorizar

Ir linha por linha preenchendo `Categoria`. Atalho útil: ordenar por `Descrição` — lojas iguais ficam agrupadas e dá pra categorizar em bloco.

Se ficar em dúvida, usar `Outros` e seguir. Não trava o fluxo.

### 3. Lançar o que não vem do CSV

Lançar manualmente em `Transações`:

- **Salário** no Santander (`Tipo = Receita`, `Categoria = Salário`)
- **Contas fixas** pagas pelo Santander: água, luz, internet, aluguel — cada uma como `Despesa` na categoria certa
- **Transações do Mercado Pago** do mês
- **Transações da Nubank CC** que não sejam cartão (ex: Pix, débito, transferência)

### 4. Registrar pagamento da fatura do Nubank

Quando pagar a fatura do cartão, criar **duas linhas** em `Transações`:

| Data | Descrição | Categoria | Valor | Conta | Tipo |
|---|---|---|---|---|---|
| (data do pagamento) | `Nubank CC → Nubank Cartão` | Transferência | (valor da fatura) | Nubank CC | Transferência |
| (data do pagamento) | `Nubank CC → Nubank Cartão` | Transferência | (valor da fatura) | Nubank Cartão | Transferência |

O saldo do Nubank CC reduz e o saldo do Nubank Cartão aproxima de zero.

### 5. Conferir saldos

Abrir `Dashboard` e comparar o `Saldo Atual` de cada conta com o saldo real nos apps dos bancos.

- Se bater (ou diferença for só de transações pendentes/não compensadas) — ok
- Se não bater — tem transação faltando ou duplicada. Voltar em `Transações` e investigar

## Transferências entre contas próprias

Sempre que mover dinheiro de uma conta própria pra outra (ex: mandar pro Mercado Pago pra pagar alguém), registrar como transferência seguindo o padrão do passo 4. Nunca registrar como despesa — senão o dinheiro "some" da consolidação.

## Se faltar tempo

Ordem de prioridade se não der pra fazer tudo:

1. Importar fatura do Nubank (maior volume, maior impacto)
2. Categorizar (mesmo que rápido)
3. Lançar salário e contas fixas
4. Conferir saldos

Transações da Nubank CC e do Mercado Pago podem ficar pra uma próxima rodada se o volume for pequeno — só não deixar passar mais de um mês.
