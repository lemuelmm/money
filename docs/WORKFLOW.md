# Workflow mensal

Rotina pra manter os arquivos de finanças atualizados. Ideia: gastar ~30 min por mês (ou 10 min por semana) colando extratos/faturas no chat e conferindo.

A interação é sempre via Claude: você cola CSV, texto do extrato ou descreve a transação, e o Claude edita `transacoes.md` e `contas.md` pra você.

## Setup inicial (uma vez)

1. Preencher `contas.md` com os **saldos iniciais** no dia de hoje, agrupados por papel:
   - **Liquidez**: `Nubank CC`, `Bradesco`, `Mercado Pago` (saldos positivos)
   - **Cartões**: `Nubank Cartão`, `Mercado Pago Cartão`, `Cartão Amazon` (**negativos** = fatura em aberto)
   - **Empréstimos**: `Nubank Empréstimo 1`, `Nubank Empréstimo 2`, `Naassom` (**negativos** = dívida em aberto)
   - **Investimentos**: `Nubank Renda Fixa`, `Nubank Bolsa` (saldos positivos, atualização periódica)
2. Deixar `transacoes.md` vazia (só o cabeçalho da tabela)

A partir daqui, todas as transações novas (posteriores à `Data Inicial` de cada conta) passam a ser registradas.

## Rotina mensal

Idealmente fazer uma vez por mês, logo depois de fechar a fatura do Nubank.

### 1. Importar fatura do Nubank (cartão)

1. No app do Nubank → fatura do cartão → exportar CSV
2. Colar o CSV inteiro no chat do Claude ("adiciona essas linhas em `transacoes.md`")
3. O Claude transforma em linhas da tabela com:
   - `Data` ← coluna `date`
   - `Descrição` ← coluna `title`
   - `Valor` ← coluna `amount` (mantém positivo, converte pra formato BR se preciso)
   - `Conta` ← `Nubank Cartão`
   - `Tipo` ← `Despesa`
   - `Categoria` ← melhor palpite com base na descrição (você revisa no passo 2)

### 2. Categorizar

Revisar as novas linhas e pedir ajustes ao Claude ("muda todas as linhas com descrição X pra categoria Y"). Ordenar por descrição mentalmente ajuda — lojas iguais ficam juntas e dá pra categorizar em bloco.

Em dúvida, deixar `Outros` e seguir. Não trava o fluxo.

### 3. Lançar o que não vem do CSV

Descrever pro Claude adicionar em `transacoes.md`:

- **Salário** no Bradesco (`Tipo = Receita`, `Categoria = Salário`)
- **Contas fixas** pagas pelo Bradesco: água, luz, internet, aluguel — cada uma como `Despesa` na categoria certa
- **Faturas de cartões não-Nubank** (Mercado Pago Cartão, Cartão Amazon): se não der pra exportar CSV, descrever manualmente ou colar o texto da fatura — Claude estrutura
- **Parcelas de empréstimo** pagas no mês: transferência da conta pagadora → conta do empréstimo (aproxima o saldo de zero)
- **Transações do Mercado Pago** (conta) do mês
- **Transações da Nubank CC** que não sejam cartão (Pix, débito, transferência)

Se tiver extrato em CSV/PDF/texto, pode colar direto — o Claude estrutura.

### 4. Registrar pagamento da fatura do Nubank

Quando pagar a fatura do cartão, pedir pro Claude adicionar as **duas linhas** de transferência:

| Data | Descrição | Categoria | Valor | Conta | Tipo |
|---|---|---|---|---|---|
| (data do pagamento) | `Nubank CC → Nubank Cartão` | Transferência | (valor) | Nubank CC | Transferência |
| (data do pagamento) | `Nubank CC → Nubank Cartão` | Transferência | (valor) | Nubank Cartão | Transferência |

O saldo do Nubank CC reduz e o saldo do Nubank Cartão aproxima de zero.

### 5. Conferir saldos

Pedir: "qual o saldo atual de cada conta?" e comparar com o saldo real nos apps dos bancos.

- Se bater (ou diferença for só de transações pendentes/não compensadas) — ok
- Se não bater — tem transação faltando ou duplicada. Pedir ao Claude pra listar as transações de uma conta específica e investigar

## Transferências entre contas próprias

Sempre que mover dinheiro de uma conta própria pra outra (ex: mandar pro Mercado Pago pra pagar alguém), registrar como transferência seguindo o padrão do passo 4 — **duas linhas**. Nunca registrar como despesa, senão o dinheiro "some" da consolidação.

## Se faltar tempo

Ordem de prioridade se não der pra fazer tudo:

1. Importar fatura do Nubank (maior volume, maior impacto)
2. Categorizar (mesmo que rápido)
3. Lançar salário e contas fixas
4. Conferir saldos

Transações da Nubank CC e do Mercado Pago podem ficar pra uma próxima rodada se o volume for pequeno — só não deixar passar mais de um mês.
