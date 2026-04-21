# Categorias

Lista inicial de categorias pra usar na coluna `Categoria` de `transacoes.md`. É um ponto de partida — ajustar conforme o padrão real de gastos aparecer nos primeiros 1-2 meses.

## Princípios

- **Poucas categorias, bem definidas.** 8-12 cobrem bem a maioria dos casos. Mais que isso começa a fragmentar e dificulta enxergar padrão
- **Subcategoria só quando fizer falta.** Se `Alimentação` for suficiente, não quebrar em `Supermercado` vs `Restaurante` ainda
- **Uma categoria = uma intenção de consumo**, não a forma de pagamento. `Uber` vai em `Transporte`, não em "cartão"

## Despesas

- **Moradia** — aluguel, condomínio, IPTU
- **Contas da casa** — água, luz, internet, gás
- **Alimentação** — supermercado, restaurante, delivery, café
- **Transporte** — combustível, Uber/99, transporte público, estacionamento
- **Saúde** — plano, farmácia, consultas, exames
- **Assinaturas** — streaming, apps, software
- **Lazer** — eventos, passeios, viagens, hobbies
- **Compras pessoais** — roupa, eletrônico, presentes
- **Educação** — cursos, livros
- **Outros** — o que não encaixar (tentar manter esse balde pequeno)

## Receitas

- **Salário**
- **Reembolso**
- **Outros**

## Transferências

Transferências entre contas próprias não são despesa nem receita (o `Tipo = Transferência` já identifica). Usar `Transferência` como valor da coluna `Categoria` pra manter a tabela consistente.

## Como evoluir

Depois do 1º mês, pedir ao Claude um resumo por categoria e perguntar:

- Tem categoria com gasto muito grande e heterogêneo? Pode valer quebrar (ex: `Alimentação` em `Supermercado` e `Fora de casa`)
- Tem categoria que quase nunca é usada? Juntar com `Outros`
- Tem muita coisa caindo em `Outros`? Criar a categoria que está faltando
