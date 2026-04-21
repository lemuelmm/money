# Transações

Registro corrido de receitas, despesas e transferências. Linhas em ordem de data crescente. Valores sempre positivos — o sinal vem de `Tipo`.

Convenções:
- `Data` no formato `YYYY-MM-DD`
- `Valor` em formato brasileiro (`1.234,56`), sempre positivo
- `Tipo` ∈ {`Receita`, `Despesa`, `Transferência`}
- `Conta` ∈ nomes listados em `contas.md`
- `Categoria` ∈ lista de `docs/CATEGORIAS.md`; para `Tipo = Transferência`, usar `Transferência`
- Transferência entre contas próprias vira **duas linhas** (saída + entrada), descrição no padrão `Origem → Destino`

Ver `docs/ESTRUTURA.md` para spec completa e `docs/WORKFLOW.md` pra rotina mensal.

| Data       | Descrição           | Categoria     | Valor  | Conta         | Tipo          |
|------------|---------------------|---------------|--------|---------------|---------------|
|            |                     |               |        |               |               |
