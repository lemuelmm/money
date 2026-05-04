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

| Data       | Descrição                              | Categoria        | Valor      | Conta     | Tipo          |
|------------|----------------------------------------|------------------|------------|-----------|---------------|
| 2026-01-02 | Vivian Lima (recebido)                 | Outros           | 50,00      | Nubank CC | Receita       |
| 2026-01-03 | Patrick do Nascimento Ferreira         | Saúde            | 275,00     | Nubank CC | Despesa       |
| 2026-01-05 | Boleto Banco IBI                       | Empréstimo       | 168,13     | Nubank CC | Despesa       |
| 2026-01-06 | Luana Chaves de Mendonça               | Outros           | 21,00      | Nubank CC | Despesa       |
| 2026-01-07 | Salário (Bradesco → Nubank CC)         | Salário          | 5.129,16   | Nubank CC | Receita       |
| 2026-01-07 | Resgate de empréstimo                  | Empréstimo       | 775,24     | Nubank CC | Despesa       |
| 2026-01-07 | Resgate de empréstimo                  | Empréstimo       | 387,16     | Nubank CC | Despesa       |
| 2026-01-07 | Domingos Sávio Montenegro              | Outros           | 400,00     | Nubank CC | Despesa       |
| 2026-01-08 | Raimunda Maria Barbosa Souza           | Outros           | 5,00       | Nubank CC | Despesa       |
| 2026-01-08 | Briziany Albuquerque Bezerra           | Outros           | 47,00      | Nubank CC | Despesa       |
| 2026-01-08 | Paulo Danusio Lima da Silva (recebido) | Outros           | 125,00     | Nubank CC | Receita       |
| 2026-01-09 | Nubank CC → Nubank Cartão              | Transferência    | 3.137,82   | Nubank CC | Transferência |
| 2026-01-09 | Nubank CC → Nubank Cartão              | Transferência    | 3.137,82   | Nubank Cartão | Transferência |
| 2026-01-10 | Patrick do Nascimento Ferreira         | Saúde            | 100,00     | Nubank CC | Despesa       |
| 2026-01-12 | Maria Nelcy Parente de Siqueira        | Outros           | 60,00      | Nubank CC | Despesa       |
| 2026-01-13 | MP*CANTINADANALU (débito)              | Alimentação      | 7,00       | Nubank CC | Despesa       |
| 2026-01-14 | Naassom Monteiro Macedo                | Empréstimo       | 666,66     | Nubank CC | Despesa       |
| 2026-01-16 | Cláudia Clementino Beserra Mendes      | Alimentação      | 9,50       | Nubank CC | Despesa       |
| 2026-01-16 | Shop do Bolo                           | Alimentação      | 3,00       | Nubank CC | Despesa       |
| 2026-01-16 | Valtemias Xavier Soares                | Outros           | 4,00       | Nubank CC | Despesa       |
| 2026-01-17 | Maria Arlet Silva de Almeida           | Outros           | 12,00      | Nubank CC | Despesa       |
| 2026-01-17 | Patrick do Nascimento Ferreira         | Saúde            | 100,00     | Nubank CC | Despesa       |
| 2026-01-18 | Cláudia Clementino Beserra Mendes      | Alimentação      | 10,50      | Nubank CC | Despesa       |
| 2026-01-20 | Cláudia Clementino Beserra Mendes      | Alimentação      | 9,00       | Nubank CC | Despesa       |
| 2026-01-20 | Roger José dos Santos Silva            | Outros           | 57,00      | Nubank CC | Despesa       |
| 2026-01-20 | Rejane Monteiro Macedo                 | Compras pessoais | 175,00     | Nubank CC | Despesa       |
| 2026-01-22 | Cláudia Clementino Beserra Mendes      | Alimentação      | 6,00       | Nubank CC | Despesa       |
| 2026-01-23 | Juazeiro Coco                          | Alimentação      | 28,00      | Nubank CC | Despesa       |
| 2026-01-23 | José Cordeiro Mendes                   | Outros           | 8,00       | Nubank CC | Despesa       |
| 2026-01-26 | Assoc. Cuidar de Cannabis Medicinal    | Saúde            | 300,00     | Nubank CC | Despesa       |
| 2026-01-26 | Beatriz Borba Lira                     | Outros           | 9,50       | Nubank CC | Despesa       |
| 2026-01-27 | Recarga de celular                     | Assinaturas      | 30,00      | Nubank CC | Despesa       |
| 2026-01-28 | Cláudia Clementino Beserra Mendes      | Alimentação      | 5,50       | Nubank CC | Despesa       |
| 2026-01-28 | Viafit Academia                        | Saúde            | 3,00       | Nubank CC | Despesa       |
| 2026-01-29 | Cláudia Clementino Beserra Mendes      | Alimentação      | 10,00      | Nubank CC | Despesa       |
| 2026-01-29 | Vivian do Nascimento Lima              | Outros           | 22,00      | Nubank CC | Despesa       |
| 2026-02-01 | Naassom Monteiro Macedo                | Outros           | 19,00      | Nubank CC | Despesa       |
| 2026-02-02 | Cláudia Clementino Beserra Mendes      | Alimentação      | 5,50       | Nubank CC | Despesa       |
| 2026-02-03 | CAGECE (água e esgoto)                 | Contas da casa   | 138,70     | Nubank CC | Despesa       |
| 2026-02-06 | Salário (Bradesco → Nubank CC)         | Salário          | 5.137,65   | Nubank CC | Receita       |
| 2026-02-06 | Patrick do Nascimento Ferreira         | Saúde            | 120,00     | Nubank CC | Despesa       |
| 2026-02-06 | Resgate de empréstimo                  | Empréstimo       | 773,68     | Nubank CC | Despesa       |
| 2026-02-06 | Resgate de empréstimo                  | Empréstimo       | 386,44     | Nubank CC | Despesa       |
| 2026-02-06 | Boleto Banco IBI                       | Empréstimo       | 104,97     | Nubank CC | Despesa       |
| 2026-02-06 | Francisco Leôncio da Silva Sobrinho    | Outros           | 40,00      | Nubank CC | Despesa       |
| 2026-02-06 | Francisco Neto da Silva                | Outros           | 72,00      | Nubank CC | Despesa       |
| 2026-02-06 | Patrick do Nascimento Ferreira         | Saúde            | 100,00     | Nubank CC | Despesa       |
| 2026-02-06 | Ian Botelho Marques Xenofonte          | Outros           | 21,10      | Nubank CC | Despesa       |
| 2026-02-09 | Nubank CC → Nubank Cartão              | Transferência    | 2.087,77   | Nubank CC | Transferência |
| 2026-02-09 | Nubank CC → Nubank Cartão              | Transferência    | 2.087,77   | Nubank Cartão | Transferência |
| 2026-02-10 | Paulo Danusio Lima da Silva            | Outros           | 60,00      | Nubank CC | Despesa       |
| 2026-02-10 | Frances Bistro                         | Alimentação      | 6,00       | Nubank CC | Despesa       |
| 2026-02-10 | Frances Bistro                         | Alimentação      | 4,00       | Nubank CC | Despesa       |
| 2026-02-11 | Rejane Monteiro Macedo                 | Compras pessoais | 175,00     | Nubank CC | Despesa       |
| 2026-02-11 | Vivian do Nascimento Lima              | Outros           | 70,00      | Nubank CC | Despesa       |
| 2026-02-11 | Juliana Ester Monteiro Macedo          | Compras pessoais | 170,00     | Nubank CC | Despesa       |
| 2026-02-11 | ENEL (energia elétrica)                | Contas da casa   | 99,81      | Nubank CC | Despesa       |
| 2026-02-11 | Ambiental Crato (saneamento)           | Contas da casa   | 27,65      | Nubank CC | Despesa       |
| 2026-02-11 | Viafit Academia                        | Saúde            | 3,00       | Nubank CC | Despesa       |
| 2026-02-11 | Antonio Lopes de Lima (recebido)       | Outros           | 140,00     | Nubank CC | Receita       |
| 2026-02-12 | ENEL (energia elétrica)                | Contas da casa   | 168,78     | Nubank CC | Despesa       |
| 2026-02-13 | Maria Beatriz de Melo Felix            | Outros           | 110,00     | Nubank CC | Despesa       |
| 2026-02-17 | Rozangela Goncalves Cassiano Brito     | Alimentação      | 32,00      | Nubank CC | Despesa       |
| 2026-02-20 | Transferência de saldo NuInvest        | Outros           | 0,10       | Nubank CC | Receita       |
| 2026-02-20 | Transferência de saldo NuInvest        | Outros           | 5,61       | Nubank CC | Receita       |
| 2026-02-21 | Cláudia Clementino Beserra Mendes      | Alimentação      | 2,25       | Nubank CC | Despesa       |
| 2026-02-21 | Maria do Socorro Silva de Souza        | Outros           | 6,80       | Nubank CC | Despesa       |
| 2026-02-21 | Moesio Ferreira Marcelino (recebido)   | Outros           | 33,26      | Nubank CC | Receita       |
| 2026-02-22 | Franklin Rodrigo Caetano (recebido)    | Outros           | 132,50     | Nubank CC | Receita       |
| 2026-02-23 | Francisco Neto da Silva                | Outros           | 42,00      | Nubank CC | Despesa       |
| 2026-02-26 | Rozangela Goncalves Cassiano Brito     | Alimentação      | 5,00       | Nubank CC | Despesa       |
| 2026-02-27 | Isaac Wanderson de Pontes Xavier       | Outros           | 70,00      | Nubank CC | Despesa       |
| 2026-02-28 | Roger José dos Santos Silva            | Outros           | 150,00     | Nubank CC | Despesa       |
| 2026-03-02 | Beatriz Borba Lira                     | Outros           | 8,77       | Nubank CC | Despesa       |
| 2026-03-03 | Cláudia Clementino Beserra Mendes      | Alimentação      | 20,00      | Nubank CC | Despesa       |
| 2026-03-03 | Naassom Monteiro Macedo (recebido)     | Empréstimo       | 20,00      | Nubank CC | Receita       |
| 2026-03-03 | Isaac Wanderson de Pontes Xavier       | Outros           | 35,00      | Nubank CC | Despesa       |
| 2026-03-05 | Boleto Banco IBI                       | Empréstimo       | 74,48      | Nubank CC | Despesa       |
| 2026-03-06 | Salário (Bradesco → Nubank CC)         | Salário          | 5.138,31   | Nubank CC | Receita       |
| 2026-03-06 | Francisco Neto da Silva                | Outros           | 70,00      | Nubank CC | Despesa       |
| 2026-03-06 | Resgate de empréstimo                  | Empréstimo       | 773,18     | Nubank CC | Despesa       |
| 2026-03-06 | Resgate de empréstimo                  | Empréstimo       | 385,59     | Nubank CC | Despesa       |
| 2026-03-06 | Beatriz Borba Lira                     | Outros           | 12,05      | Nubank CC | Despesa       |
| 2026-03-08 | Cariri Farma                           | Saúde            | 22,89      | Nubank CC | Despesa       |
| 2026-03-09 | Nubank CC → Nubank Cartão              | Transferência    | 2.262,18   | Nubank CC | Transferência |
| 2026-03-09 | Nubank CC → Nubank Cartão              | Transferência    | 2.262,18   | Nubank Cartão | Transferência |
| 2026-03-10 | Beatriz Borba Lira                     | Outros           | 12,78      | Nubank CC | Despesa       |
| 2026-03-10 | Miguel Vieira de Souza                 | Outros           | 15,00      | Nubank CC | Despesa       |
| 2026-03-10 | Rejane Monteiro Macedo                 | Compras pessoais | 100,00     | Nubank CC | Despesa       |
| 2026-03-11 | Naassom Monteiro Macedo                | Empréstimo       | 1.000,00   | Nubank CC | Despesa       |
| 2026-03-11 | Ester Burmann Faustino                 | Outros           | 50,00      | Nubank CC | Despesa       |
| 2026-03-11 | Ester Burmann Faustino                 | Outros           | 10,00      | Nubank CC | Despesa       |
| 2026-03-13 | WEpayments TheStarter Lda              | Outros           | 300,00     | Nubank CC | Despesa       |
| 2026-03-13 | Cícera Daniele dos Santos              | Outros           | 90,00      | Nubank CC | Despesa       |
| 2026-03-13 | José Bernardino da Silva               | Outros           | 30,00      | Nubank CC | Despesa       |
| 2026-03-18 | Vivian do Nascimento Lima              | Outros           | 160,00     | Nubank CC | Despesa       |
| 2026-03-18 | Rozangela Goncalves Cassiano Brito     | Alimentação      | 5,00       | Nubank CC | Despesa       |
| 2026-03-20 | Crédito em conta                       | Outros           | 6,39       | Nubank CC | Receita       |
| 2026-03-20 | Fellipe Pacheco Melo                   | Outros           | 32,71      | Nubank CC | Despesa       |
| 2026-03-24 | Domingos Sávio Montenegro              | Outros           | 15,00      | Nubank CC | Despesa       |
| 2026-03-24 | Patrick do Nascimento Ferreira         | Saúde            | 100,00     | Nubank CC | Despesa       |
| 2026-03-25 | Salário (Bradesco → Nubank CC)         | Salário          | 3.593,40   | Nubank CC | Receita       |
| 2026-03-25 | Patrick do Nascimento Ferreira         | Saúde            | 25,00      | Nubank CC | Despesa       |
| 2026-03-25 | Beatriz Borba Lira                     | Outros           | 8,00       | Nubank CC | Despesa       |
| 2026-03-25 | ENEL (energia elétrica)                | Contas da casa   | 250,47     | Nubank CC | Despesa       |
| 2026-03-25 | Juliana Ester Monteiro Macedo          | Compras pessoais | 31,00      | Nubank CC | Despesa       |
| 2026-03-27 | Lemuel Monteiro Macedo (recebido 99Pay)| Outros           | 0,05       | Nubank CC | Receita       |
| 2026-03-27 | Patrick do Nascimento Ferreira         | Saúde            | 100,00     | Nubank CC | Despesa       |
| 2026-03-27 | Juazeiro Coco                          | Alimentação      | 29,00      | Nubank CC | Despesa       |
| 2026-03-27 | Rozangela Goncalves Cassiano Brito     | Alimentação      | 5,00       | Nubank CC | Despesa       |
| 2026-03-31 | Débito em conta                        | Outros           | 30,00      | Nubank CC | Despesa       |
| 2026-04-01 | Uber (NuPay débito)                    | Transporte       | 32,48      | Nubank CC | Despesa       |
| 2026-04-01 | Ian Botelho Marques Xenofonte          | Outros           | 24,00      | Nubank CC | Despesa       |
| 2026-04-03 | IPVA + Multas (Secretaria da Fazenda)  | Transporte       | 1.332,95   | Nubank CC | Despesa       |
| 2026-04-05 | Resgate de empréstimo                  | Empréstimo       | 772,12     | Nubank CC | Despesa       |
| 2026-04-05 | Resgate de empréstimo                  | Empréstimo       | 385,72     | Nubank CC | Despesa       |
| 2026-04-06 | Boleto Banco IBI                       | Empréstimo       | 160,45     | Nubank CC | Despesa       |
| 2026-04-06 | Natalia Bezerra Patrício               | Outros           | 5,20       | Nubank CC | Despesa       |
| 2026-04-06 | Patrick do Nascimento Ferreira         | Saúde            | 125,00     | Nubank CC | Despesa       |
| 2026-04-06 | Paulo Danusio Lima da Silva            | Outros           | 39,20      | Nubank CC | Despesa       |
| 2026-04-07 | Salário (Bradesco → Nubank CC)         | Salário          | 5.094,78   | Nubank CC | Receita       |
| 2026-04-07 | Paulo Danusio Lima da Silva            | Outros           | 19,25      | Nubank CC | Despesa       |
| 2026-04-08 | Nubank CC → Nubank Cartão              | Transferência    | 488,20     | Nubank CC | Transferência |
| 2026-04-08 | Nubank CC → Nubank Cartão              | Transferência    | 488,20     | Nubank Cartão | Transferência |
| 2026-04-09 | Nubank CC → Nubank Cartão              | Transferência    | 3.000,00   | Nubank CC | Transferência |
| 2026-04-09 | Nubank CC → Nubank Cartão              | Transferência    | 3.000,00   | Nubank Cartão | Transferência |
| 2026-04-09 | Ygor Teixeira                          | Outros           | 160,00     | Nubank CC | Despesa       |
| 2026-04-09 | Luanderson da Silva Araújo             | Outros           | 300,00     | Nubank CC | Despesa       |
| 2026-04-10 | Beatriz Borba Lira                     | Outros           | 9,87       | Nubank CC | Despesa       |
| 2026-04-11 | Alex Germano da Silva Teles            | Outros           | 8,00       | Nubank CC | Despesa       |
| 2026-04-12 | Naassom Monteiro Macedo                | Empréstimo       | 600,00     | Nubank CC | Despesa       |
| 2026-04-13 | 99 Tecnologia (99app)                  | Transporte       | 5,70       | Nubank CC | Despesa       |
| 2026-04-13 | Dennys Wandson de Souza Luna           | Outros           | 1,00       | Nubank CC | Despesa       |
| 2026-04-16 | Maria Beatriz de Melo Felix (recebido) | Outros           | 25,00      | Nubank CC | Receita       |
| 2026-04-17 | Espaço Verde                           | Lazer            | 20,00      | Nubank CC | Despesa       |
| 2026-04-17 | Fabio dos Santos Sena                  | Outros           | 17,00      | Nubank CC | Despesa       |
| 2026-04-17 | Rozangela Goncalves Cassiano Brito     | Alimentação      | 25,00      | Nubank CC | Despesa       |
| 2026-04-18 | Cláudia Clementino Beserra Mendes      | Alimentação      | 8,00       | Nubank CC | Despesa       |
| 2026-01-01 | Restaurante Ponto do C                 | Alimentação      | 38,60      | Nubank Cartão | Despesa    |
| 2026-01-01 | Auto Posto Grangeiro (combustível)     | Transporte       | 14,30      | Nubank Cartão | Despesa    |
| 2026-01-01 | Uber                                   | Transporte       | 2,24       | Nubank Cartão | Despesa    |
| 2026-01-02 | Juazeiro do N — remédio (parcela 3/3)  | Saúde            | 120,00     | Nubank Cartão | Despesa    |
| 2026-01-02 | Mix Rações — pet (parcela 3/4)         | Compras pessoais | 67,00      | Nubank Cartão | Despesa    |
| 2026-01-02 | Amazon (parcela 7/10)                  | Compras pessoais | 125,88     | Nubank Cartão | Despesa    |
| 2026-01-02 | Mix Rações — pet (parcela 3/5)         | Compras pessoais | 50,60      | Nubank Cartão | Despesa    |
| 2026-01-03 | iFood restaurante                      | Alimentação      | 25,36      | Nubank Cartão | Despesa    |
| 2026-01-03 | Amazon Assinaturas                     | Assinaturas      | 19,90      | Nubank Cartão | Despesa    |
| 2026-01-04 | Uber                                   | Transporte       | 5,70       | Nubank Cartão | Despesa    |
| 2026-01-04 | Diniz Supermercados (parcela 1/2)      | Alimentação      | 48,34      | Nubank Cartão | Despesa    |
| 2026-01-05 | Microsoft 365                          | Assinaturas      | 69,90      | Nubank Cartão | Despesa    |
| 2026-01-05 | Elisangela Mendes                      | Outros           | 62,70      | Nubank Cartão | Despesa    |
| 2026-01-05 | Diniz Supermercados                    | Alimentação      | 4,99       | Nubank Cartão | Despesa    |
| 2026-01-07 | Uber One Membership                    | Assinaturas      | 19,90      | Nubank Cartão | Despesa    |
| 2026-01-09 | Uber                                   | Transporte       | 5,34       | Nubank Cartão | Despesa    |
| 2026-01-10 | Uber                                   | Transporte       | 8,39       | Nubank Cartão | Despesa    |
| 2026-01-10 | iFood Club                             | Assinaturas      | 7,95       | Nubank Cartão | Despesa    |
| 2026-01-10 | Frances Bistro                         | Alimentação      | 34,23      | Nubank Cartão | Despesa    |
| 2026-01-12 | Posto Nossa Senhora (combustível)      | Transporte       | 40,00      | Nubank Cartão | Despesa    |
| 2026-01-12 | Galeteria e Peixaria                   | Alimentação      | 70,00      | Nubank Cartão | Despesa    |
| 2026-01-12 | Uber                                   | Transporte       | 16,09      | Nubank Cartão | Despesa    |
| 2026-01-13 | Uber                                   | Transporte       | 5,19       | Nubank Cartão | Despesa    |
| 2026-01-14 | Uber                                   | Transporte       | 4,25       | Nubank Cartão | Despesa    |
| 2026-01-14 | Viafit Academia (mensalidade)          | Saúde            | 159,90     | Nubank Cartão | Despesa    |
| 2026-01-15 | Uber                                   | Transporte       | 6,73       | Nubank Cartão | Despesa    |
| 2026-01-15 | Google One                             | Assinaturas      | 31,99      | Nubank Cartão | Despesa    |
| 2026-01-16 | Smiles Clube                           | Assinaturas      | 42,00      | Nubank Cartão | Despesa    |
| 2026-01-16 | Luandersondasilva                      | Outros           | 68,00      | Nubank Cartão | Despesa    |
| 2026-01-17 | iFood restaurante                      | Alimentação      | 34,47      | Nubank Cartão | Despesa    |
| 2026-01-17 | Freitas Varejo (parcela 1/2)           | Compras pessoais | 23,96      | Nubank Cartão | Despesa    |
| 2026-01-17 | Carajas Construções (parcela 1/2)      | Compras pessoais | 39,99      | Nubank Cartão | Despesa    |
| 2026-01-18 | Uber                                   | Transporte       | 6,60       | Nubank Cartão | Despesa    |
| 2026-01-18 | Uber                                   | Transporte       | 1,00       | Nubank Cartão | Despesa    |
| 2026-01-18 | 507Mateus Supermercado                 | Alimentação      | 138,02     | Nubank Cartão | Despesa    |
| 2026-01-18 | Uber                                   | Transporte       | 7,68       | Nubank Cartão | Despesa    |
| 2026-01-18 | Uber                                   | Transporte       | 3,30       | Nubank Cartão | Despesa    |
| 2026-01-18 | Uber                                   | Transporte       | 2,61       | Nubank Cartão | Despesa    |
| 2026-01-18 | Mercadinho São Luiz                    | Alimentação      | 64,78      | Nubank Cartão | Despesa    |
| 2026-01-19 | Uber                                   | Transporte       | 5,57       | Nubank Cartão | Despesa    |
| 2026-01-20 | Uber                                   | Transporte       | 9,41       | Nubank Cartão | Despesa    |
| 2026-01-21 | Uber                                   | Transporte       | 7,18       | Nubank Cartão | Despesa    |
| 2026-01-21 | Uber                                   | Transporte       | 11,51      | Nubank Cartão | Despesa    |
| 2026-01-21 | Crema                                  | Alimentação      | 34,00      | Nubank Cartão | Despesa    |
| 2026-01-22 | Uber                                   | Transporte       | 20,65      | Nubank Cartão | Despesa    |
| 2026-01-22 | Uber                                   | Transporte       | 3,36       | Nubank Cartão | Despesa    |
| 2026-01-24 | Google YouTube Premium                 | Assinaturas      | 24,90      | Nubank Cartão | Despesa    |
| 2026-01-24 | iFood McDonald's                       | Alimentação      | 40,79      | Nubank Cartão | Despesa    |
| 2026-01-24 | Uber                                   | Transporte       | 7,50       | Nubank Cartão | Despesa    |
| 2026-01-24 | Uber                                   | Transporte       | 5,54       | Nubank Cartão | Despesa    |
| 2026-01-25 | Uber                                   | Transporte       | 3,60       | Nubank Cartão | Despesa    |
| 2026-01-25 | Atacadão                               | Alimentação      | 18,90      | Nubank Cartão | Despesa    |
| 2026-01-25 | iFood 2 I Hamburgueria                 | Alimentação      | 71,89      | Nubank Cartão | Despesa    |
| 2026-01-25 | Atacadão                               | Alimentação      | 98,01      | Nubank Cartão | Despesa    |
| 2026-01-25 | Uber                                   | Transporte       | 9,16       | Nubank Cartão | Despesa    |
| 2026-01-26 | Uber                                   | Transporte       | 2,99       | Nubank Cartão | Despesa    |
| 2026-01-26 | Amazon Ad Free for Prime               | Assinaturas      | 10,00      | Nubank Cartão | Despesa    |
| 2026-01-26 | Uber                                   | Transporte       | 14,72      | Nubank Cartão | Despesa    |
| 2026-01-27 | Uber                                   | Transporte       | 11,45      | Nubank Cartão | Despesa    |
| 2026-01-27 | iFood Club                             | Assinaturas      | 5,95       | Nubank Cartão | Despesa    |
| 2026-01-28 | Uber                                   | Transporte       | 2,81       | Nubank Cartão | Despesa    |
| 2026-01-28 | Posto Prime (combustível)              | Transporte       | 30,00      | Nubank Cartão | Despesa    |
| 2026-01-28 | Uber                                   | Transporte       | 5,97       | Nubank Cartão | Despesa    |
| 2026-01-29 | Uber                                   | Transporte       | 4,81       | Nubank Cartão | Despesa    |
| 2026-01-29 | Uber                                   | Transporte       | 22,68      | Nubank Cartão | Despesa    |
| 2026-01-30 | Amazon Prime                           | Assinaturas      | 19,90      | Nubank Cartão | Despesa    |
| 2026-01-30 | Uber                                   | Transporte       | 2,57       | Nubank Cartão | Despesa    |
| 2026-01-30 | Uber                                   | Transporte       | 4,99       | Nubank Cartão | Despesa    |
| 2026-01-30 | Uber                                   | Transporte       | 6,64       | Nubank Cartão | Despesa    |
| 2026-01-31 | Uber                                   | Transporte       | 6,20       | Nubank Cartão | Despesa    |
| 2026-01-31 | Uber                                   | Transporte       | 8,29       | Nubank Cartão | Despesa    |
| 2026-02-01 | Uber                                   | Transporte       | 4,50       | Nubank Cartão | Despesa    |
| 2026-02-01 | Uber                                   | Transporte       | 4,08       | Nubank Cartão | Despesa    |
| 2026-02-01 | Cariri Center Supermercado             | Alimentação      | 104,51     | Nubank Cartão | Despesa    |
| 2026-02-02 | Freitas Varejo (parcela 2/2)           | Compras pessoais | 23,96      | Nubank Cartão | Despesa    |
| 2026-02-02 | Diniz Supermercados (parcela 2/2)      | Alimentação      | 48,34      | Nubank Cartão | Despesa    |
| 2026-02-02 | Mix Rações — pet (parcela 4/4)         | Compras pessoais | 67,00      | Nubank Cartão | Despesa    |
| 2026-02-02 | Amazon (parcela 8/10)                  | Compras pessoais | 125,88     | Nubank Cartão | Despesa    |
| 2026-02-02 | Mix Rações — pet (parcela 4/5)         | Compras pessoais | 50,60      | Nubank Cartão | Despesa    |
| 2026-02-02 | Carajas Construções (parcela 2/2)      | Compras pessoais | 39,99      | Nubank Cartão | Despesa    |
| 2026-02-03 | Uber                                   | Transporte       | 6,77       | Nubank Cartão | Despesa    |
| 2026-02-03 | Amazon Assinaturas                     | Assinaturas      | 19,90      | Nubank Cartão | Despesa    |
| 2026-02-03 | Prime Xii                              | Assinaturas      | 30,00      | Nubank Cartão | Despesa    |
| 2026-02-03 | Uber                                   | Transporte       | 2,10       | Nubank Cartão | Despesa    |
| 2026-02-03 | Uber                                   | Transporte       | 7,41       | Nubank Cartão | Despesa    |
| 2026-02-04 | Uber                                   | Transporte       | 7,19       | Nubank Cartão | Despesa    |
| 2026-02-06 | Uber                                   | Transporte       | 6,56       | Nubank Cartão | Despesa    |
| 2026-02-06 | Supermercado Moreira                   | Alimentação      | 16,32      | Nubank Cartão | Despesa    |
| 2026-02-06 | Atacadão                               | Alimentação      | 97,56      | Nubank Cartão | Despesa    |
| 2026-02-07 | Uber                                   | Transporte       | 5,80       | Nubank Cartão | Despesa    |
| 2026-02-07 | Uber One Membership                    | Assinaturas      | 19,90      | Nubank Cartão | Despesa    |
| 2026-02-07 | Uber                                   | Transporte       | 3,46       | Nubank Cartão | Despesa    |
| 2026-02-10 | Mercadinho São Luiz                    | Alimentação      | 99,00      | Nubank Cartão | Despesa    |
| 2026-02-10 | Uber                                   | Transporte       | 5,55       | Nubank Cartão | Despesa    |
| 2026-02-10 | iFood Club                             | Assinaturas      | 7,95       | Nubank Cartão | Despesa    |
| 2026-02-11 | Uber                                   | Transporte       | 5,40       | Nubank Cartão | Despesa    |
| 2026-02-11 | Uber                                   | Transporte       | 4,48       | Nubank Cartão | Despesa    |
| 2026-02-11 | Uber                                   | Transporte       | 4,41       | Nubank Cartão | Despesa    |
| 2026-02-12 | Uber                                   | Transporte       | 4,49       | Nubank Cartão | Despesa    |
| 2026-02-12 | Veteranos Barb (barbearia)             | Compras pessoais | 50,00      | Nubank Cartão | Despesa    |
| 2026-02-12 | Prime Xii                              | Assinaturas      | 50,00      | Nubank Cartão | Despesa    |
| 2026-02-13 | Uber                                   | Transporte       | 4,49       | Nubank Cartão | Despesa    |
| 2026-02-13 | Uber                                   | Transporte       | 5,51       | Nubank Cartão | Despesa    |
| 2026-02-14 | Viafit Academia (mensalidade)          | Saúde            | 159,90     | Nubank Cartão | Despesa    |
| 2026-02-14 | Uber                                   | Transporte       | 7,53       | Nubank Cartão | Despesa    |
| 2026-02-15 | Mundo dos Sorvetes                     | Alimentação      | 6,00       | Nubank Cartão | Despesa    |
| 2026-02-15 | Google One                             | Assinaturas      | 31,99      | Nubank Cartão | Despesa    |
| 2026-02-15 | 507Mateus Supermercado                 | Alimentação      | 23,78      | Nubank Cartão | Despesa    |
| 2026-02-16 | Smiles Clube                           | Assinaturas      | 42,00      | Nubank Cartão | Despesa    |
| 2026-02-21 | Mg Derivados                           | Alimentação      | 50,00      | Nubank Cartão | Despesa    |
| 2026-02-21 | Frances Bistro                         | Alimentação      | 25,57      | Nubank Cartão | Despesa    |
| 2026-02-21 | Empório Kariri                         | Alimentação      | 11,90      | Nubank Cartão | Despesa    |
| 2026-02-21 | Uber                                   | Transporte       | 8,16       | Nubank Cartão | Despesa    |
| 2026-02-21 | Empório Marco Polo                     | Alimentação      | 242,76     | Nubank Cartão | Despesa    |
| 2026-02-21 | Floricultura Espaço Fl                 | Outros           | 31,15      | Nubank Cartão | Despesa    |
| 2026-02-22 | Uber                                   | Transporte       | 12,12      | Nubank Cartão | Despesa    |
| 2026-02-22 | Carajas Construções (parcela 1/3)      | Compras pessoais | 33,30      | Nubank Cartão | Despesa    |
| 2026-02-22 | Irmãos Chagas da Car                   | Alimentação      | 232,84     | Nubank Cartão | Despesa    |
| 2026-02-24 | Google YouTube Premium                 | Assinaturas      | 24,90      | Nubank Cartão | Despesa    |
| 2026-02-24 | Apple.Com/Bill                         | Assinaturas      | 14,90      | Nubank Cartão | Despesa    |
| 2026-02-25 | Juazeiro Coco                          | Alimentação      | 30,00      | Nubank Cartão | Despesa    |
| 2026-02-26 | Posto Prime (combustível)              | Transporte       | 30,00      | Nubank Cartão | Despesa    |
| 2026-02-26 | Atacadão                               | Alimentação      | 82,80      | Nubank Cartão | Despesa    |
| 2026-02-26 | Amazon Ad Free for Prime               | Assinaturas      | 10,00      | Nubank Cartão | Despesa    |
| 2026-02-27 | Recarga de celular                     | Assinaturas      | 30,00      | Nubank Cartão | Despesa    |
| 2026-02-27 | iFood Club                             | Assinaturas      | 5,95       | Nubank Cartão | Despesa    |
| 2026-02-28 | Atacadão                               | Alimentação      | 0,96       | Nubank Cartão | Despesa    |
| 2026-02-28 | Atacadão                               | Alimentação      | 273,75     | Nubank Cartão | Despesa    |
| 2026-03-01 | Amazon Prime                           | Assinaturas      | 19,90      | Nubank Cartão | Despesa    |
| 2026-03-02 | Carajas Construções (parcela 2/3)      | Compras pessoais | 33,30      | Nubank Cartão | Despesa    |
| 2026-03-02 | Posto Nsa das Graças (combustível)     | Transporte       | 30,95      | Nubank Cartão | Despesa    |
| 2026-03-02 | Amazon (parcela 9/10)                  | Compras pessoais | 125,88     | Nubank Cartão | Despesa    |
| 2026-03-02 | Mix Rações — pet (parcela 5/5)         | Compras pessoais | 50,60      | Nubank Cartão | Despesa    |
| 2026-03-03 | Academia Viafit                        | Saúde            | 3,00       | Nubank Cartão | Despesa    |
| 2026-03-03 | Amazon Assinaturas                     | Assinaturas      | 19,90      | Nubank Cartão | Despesa    |
| 2026-03-05 | 507Mateus Supermercado                 | Alimentação      | 97,31      | Nubank Cartão | Despesa    |
| 2026-03-06 | Premmia Petrobras (combustível)        | Transporte       | 100,00     | Nubank Cartão | Despesa    |
| 2026-03-07 | Restaurante Ponto do C                 | Alimentação      | 65,00      | Nubank Cartão | Despesa    |
| 2026-03-07 | Uber One Membership                    | Assinaturas      | 19,90      | Nubank Cartão | Despesa    |
| 2026-03-07 | Diniz Supermercados                    | Alimentação      | 42,01      | Nubank Cartão | Despesa    |
| 2026-03-10 | iFood Club                             | Assinaturas      | 7,95       | Nubank Cartão | Despesa    |
| 2026-03-11 | e. A. Turatto                          | Outros           | 10,90      | Nubank Cartão | Despesa    |
| 2026-03-11 | Uber                                   | Transporte       | 6,17       | Nubank Cartão | Despesa    |
| 2026-03-11 | Juazeiro Burgues                       | Alimentação      | 27,90      | Nubank Cartão | Despesa    |
| 2026-03-11 | Bookshop (parcela 1/2)                 | Educação         | 41,90      | Nubank Cartão | Despesa    |
| 2026-03-11 | Cacau Show                             | Alimentação      | 39,99      | Nubank Cartão | Despesa    |
| 2026-03-12 | Uber                                   | Transporte       | 3,46       | Nubank Cartão | Despesa    |
| 2026-03-12 | Uber                                   | Transporte       | 6,63       | Nubank Cartão | Despesa    |
| 2026-03-14 | Mp *Juagarden                          | Lazer            | 18,00      | Nubank Cartão | Despesa    |
| 2026-03-14 | Espaço Verde (parcela 1/2)             | Lazer            | 43,50      | Nubank Cartão | Despesa    |
| 2026-03-14 | Mp *Juagarden                          | Lazer            | 20,00      | Nubank Cartão | Despesa    |
| 2026-03-14 | Viafit Academia (mensalidade)          | Saúde            | 159,90     | Nubank Cartão | Despesa    |
| 2026-03-15 | Google One                             | Assinaturas      | 31,99      | Nubank Cartão | Despesa    |
| 2026-03-17 | Amazon Marketplace                     | Compras pessoais | 20,61      | Nubank Cartão | Despesa    |
| 2026-03-17 | Doctors Coffee                         | Alimentação      | 8,00       | Nubank Cartão | Despesa    |
| 2026-03-17 | Amazon Marketplace                     | Compras pessoais | 16,98      | Nubank Cartão | Despesa    |
| 2026-03-17 | Smiles Clube                           | Assinaturas      | 42,00      | Nubank Cartão | Despesa    |
| 2026-03-17 | Amazon Marketplace                     | Compras pessoais | 16,88      | Nubank Cartão | Despesa    |
| 2026-03-17 | Amazon Marketplace                     | Compras pessoais | 22,87      | Nubank Cartão | Despesa    |
| 2026-03-17 | Amazon Marketplace                     | Compras pessoais | 116,65     | Nubank Cartão | Despesa    |
| 2026-03-19 | Mercadinho São Luiz                    | Alimentação      | 22,35      | Nubank Cartão | Despesa    |
| 2026-03-19 | Uber                                   | Transporte       | 2,77       | Nubank Cartão | Despesa    |
| 2026-03-19 | Mercadinho São Luiz                    | Alimentação      | 263,04     | Nubank Cartão | Despesa    |
| 2026-03-19 | Pague Menos                            | Saúde            | 11,88      | Nubank Cartão | Despesa    |
| 2026-03-19 | Cacau Show                             | Alimentação      | 69,99      | Nubank Cartão | Despesa    |
| 2026-03-19 | Juazeiro Coco                          | Alimentação      | 30,00      | Nubank Cartão | Despesa    |
| 2026-03-19 | Lasa                                   | Compras pessoais | 57,98      | Nubank Cartão | Despesa    |
| 2026-03-19 | Uber                                   | Transporte       | 11,30      | Nubank Cartão | Despesa    |
| 2026-03-19 | Arca Digital Marke (curso)             | Educação         | 37,00      | Nubank Cartão | Despesa    |
| 2026-03-19 | Atacadão                               | Alimentação      | 122,03     | Nubank Cartão | Despesa    |
| 2026-03-20 | Frances Bistro                         | Alimentação      | 59,92      | Nubank Cartão | Despesa    |
| 2026-03-20 | Uber                                   | Transporte       | 3,15       | Nubank Cartão | Despesa    |
| 2026-03-20 | Uber                                   | Transporte       | 6,68       | Nubank Cartão | Despesa    |
| 2026-03-21 | Sergionaokazu (japonês)                | Alimentação      | 101,00     | Nubank Cartão | Despesa    |
| 2026-03-21 | iFood restaurante                      | Alimentação      | 51,99      | Nubank Cartão | Despesa    |
| 2026-03-21 | IOF Claude.Ai Subscription             | Assinaturas      | 4,02       | Nubank Cartão | Despesa    |
| 2026-03-21 | Claude.Ai Subscription                 | Assinaturas      | 114,99     | Nubank Cartão | Despesa    |
| 2026-03-23 | Belavista                              | Alimentação      | 40,00      | Nubank Cartão | Despesa    |
| 2026-03-23 | Mp *Xannd                              | Outros           | 100,00     | Nubank Cartão | Despesa    |
| 2026-03-23 | Diniz Supermercados                    | Alimentação      | 38,71      | Nubank Cartão | Despesa    |
| 2026-03-24 | Apple.Com/Bill                         | Assinaturas      | 14,90      | Nubank Cartão | Despesa    |
| 2026-03-24 | Academia Viafit                        | Saúde            | 3,00       | Nubank Cartão | Despesa    |
| 2026-03-24 | Uber                                   | Transporte       | 6,59       | Nubank Cartão | Despesa    |
| 2026-03-24 | Google YouTube Premium                 | Assinaturas      | 24,90      | Nubank Cartão | Despesa    |
| 2026-03-26 | Amazon Ad Free for Prime               | Assinaturas      | 10,00      | Nubank Cartão | Despesa    |
| 2026-03-26 | Pague Menos (parcela 1/2)              | Saúde            | 77,78      | Nubank Cartão | Despesa    |
| 2026-03-26 | iFood N1 Chicken Crato                 | Alimentação      | 18,48      | Nubank Cartão | Despesa    |
| 2026-03-27 | Uber                                   | Transporte       | 23,80      | Nubank Cartão | Despesa    |
| 2026-03-27 | Flor de Juá (parcela 1/2)              | Compras pessoais | 64,00      | Nubank Cartão | Despesa    |
| 2026-03-27 | iFood Club                             | Assinaturas      | 5,95       | Nubank Cartão | Despesa    |
| 2026-03-27 | iFood Juazeiro do Norte                | Alimentação      | 34,99      | Nubank Cartão | Despesa    |
| 2026-03-27 | Uber                                   | Transporte       | 11,40      | Nubank Cartão | Despesa    |
| 2026-03-28 | Uber                                   | Transporte       | 6,71       | Nubank Cartão | Despesa    |
| 2026-03-28 | iFood 88 Smash                         | Alimentação      | 57,00      | Nubank Cartão | Despesa    |
| 2026-03-28 | Uber                                   | Transporte       | 5,22       | Nubank Cartão | Despesa    |
| 2026-03-28 | Uber                                   | Transporte       | 7,39       | Nubank Cartão | Despesa    |
| 2026-03-29 | Arca Digital Marke (curso)             | Educação         | 103,11     | Nubank Cartão | Despesa    |
| 2026-03-29 | iFood 2 I Hamburgueria                 | Alimentação      | 24,89      | Nubank Cartão | Despesa    |
| 2026-03-29 | Uber                                   | Transporte       | 4,57       | Nubank Cartão | Despesa    |
| 2026-03-29 | Veteranos Barb (barbearia)             | Compras pessoais | 50,00      | Nubank Cartão | Despesa    |
| 2026-03-29 | Uber                                   | Transporte       | 3,35       | Nubank Cartão | Despesa    |
| 2026-03-29 | Mercadinho São Luiz                    | Alimentação      | 186,45     | Nubank Cartão | Despesa    |
| 2026-03-29 | Ml Alimentos — pet                     | Compras pessoais | 59,00      | Nubank Cartão | Despesa    |
| 2026-03-29 | Mix Rações — pet (parcela 1/5)         | Compras pessoais | 59,00      | Nubank Cartão | Despesa    |
| 2026-03-29 | Frances Bistro                         | Alimentação      | 66,82      | Nubank Cartão | Despesa    |
| 2026-03-30 | Temu (parcela 1/3)                     | Compras pessoais | 35,52      | Nubank Cartão | Despesa    |
| 2026-03-30 | Amazon Prime                           | Assinaturas      | 19,90      | Nubank Cartão | Despesa    |
| 2026-03-30 | Diniz Supermercados                    | Alimentação      | 29,93      | Nubank Cartão | Despesa    |
| 2026-04-01 | Diniz Supermercados                    | Alimentação      | 49,08      | Nubank Cartão | Despesa    |
| 2026-04-01 | Diniz Supermercados                    | Alimentação      | 25,54      | Nubank Cartão | Despesa    |
| 2026-04-02 | Carajas Construções (parcela 3/3)      | Compras pessoais | 33,30      | Nubank Cartão | Despesa    |
| 2026-04-02 | Espaço Verde (parcela 2/2)             | Lazer            | 43,50      | Nubank Cartão | Despesa    |
| 2026-04-02 | Temu (parcela 2/3)                     | Compras pessoais | 35,52      | Nubank Cartão | Despesa    |
| 2026-04-02 | Flor de Juá (parcela 2/2)              | Compras pessoais | 64,00      | Nubank Cartão | Despesa    |
| 2026-04-02 | Pague Menos (parcela 2/2)              | Saúde            | 77,78      | Nubank Cartão | Despesa    |
| 2026-04-02 | Bookshop (parcela 2/2)                 | Educação         | 41,90      | Nubank Cartão | Despesa    |
| 2026-04-02 | Amazon (parcela 10/10)                 | Compras pessoais | 125,88     | Nubank Cartão | Despesa    |
| 2026-04-02 | Instituto Aho — medicina natural       | Saúde            | 152,00     | Nubank Cartão | Despesa    |
| 2026-04-02 | Mix Rações — pet (parcela 2/5)         | Compras pessoais | 59,00      | Nubank Cartão | Despesa    |
| 2026-04-03 | iFood 2 I Hamburgueria                 | Alimentação      | 81,63      | Nubank Cartão | Despesa    |
| 2026-04-03 | Amazon Assinaturas                     | Assinaturas      | 19,90      | Nubank Cartão | Despesa    |
| 2026-04-03 | Drogaria Feitosa                       | Saúde            | 114,81     | Nubank Cartão | Despesa    |
| 2026-04-03 | Andersondantasdos                      | Outros           | 42,00      | Nubank Cartão | Despesa    |
| 2026-04-03 | iFood Churrascaria Nativa              | Alimentação      | 32,89      | Nubank Cartão | Despesa    |
| 2026-04-03 | Petrobras Premmia (combustível)        | Transporte       | 188,00     | Nubank Cartão | Despesa    |
| 2026-04-03 | Luandersondasilva                      | Outros           | 71,00      | Nubank Cartão | Despesa    |
| 2026-04-04 | Atacarejo Cariri                       | Alimentação      | 122,96     | Nubank Cartão | Despesa    |
| 2026-04-04 | Gela Prime Mercadinho                  | Alimentação      | 9,50       | Nubank Cartão | Despesa    |
| 2026-04-05 | Mp *Luanakarla                         | Outros           | 12,00      | Nubank Cartão | Despesa    |
| 2026-04-06 | Uber                                   | Transporte       | 3,73       | Nubank Cartão | Despesa    |
| 2026-04-06 | Uber                                   | Transporte       | 5,91       | Nubank Cartão | Despesa    |
| 2026-04-06 | Uber                                   | Transporte       | 6,02       | Nubank Cartão | Despesa    |
| 2026-04-06 | Uber                                   | Transporte       | 6,21       | Nubank Cartão | Despesa    |
| 2026-04-07 | Uber                                   | Transporte       | 14,95      | Nubank Cartão | Despesa    |
| 2026-04-07 | Uber One Membership                    | Assinaturas      | 19,90      | Nubank Cartão | Despesa    |
| 2026-04-08 | Amazon Marketplace (parcela 1/3)       | Compras pessoais | 39,61      | Nubank Cartão | Despesa    |
| 2026-04-09 | Uber                                   | Transporte       | 2,72       | Nubank Cartão | Despesa    |
| 2026-04-09 | Uber                                   | Transporte       | 4,52       | Nubank Cartão | Despesa    |
| 2026-04-10 | Amazon Marketplace (parcela 1/4)       | Compras pessoais | 36,39      | Nubank Cartão | Despesa    |
| 2026-04-10 | Uber                                   | Transporte       | 16,55      | Nubank Cartão | Despesa    |
| 2026-04-10 | Uber                                   | Transporte       | 3,57       | Nubank Cartão | Despesa    |
| 2026-04-10 | iFood Club                             | Assinaturas      | 7,95       | Nubank Cartão | Despesa    |
| 2026-04-11 | Diniz Supermercados                    | Alimentação      | 37,54      | Nubank Cartão | Despesa    |
| 2026-04-13 | Uber                                   | Transporte       | 5,80       | Nubank Cartão | Despesa    |
| 2026-04-13 | Uber                                   | Transporte       | 6,66       | Nubank Cartão | Despesa    |
| 2026-04-14 | Viafit Academia (mensalidade)          | Saúde            | 159,90     | Nubank Cartão | Despesa    |
| 2026-04-16 | Uber                                   | Transporte       | 3,38       | Nubank Cartão | Despesa    |
| 2026-04-16 | Uber                                   | Transporte       | 3,65       | Nubank Cartão | Despesa    |
| 2026-04-16 | Smiles Clube                           | Assinaturas      | 42,00      | Nubank Cartão | Despesa    |
| 2026-04-17 | Uber                                   | Transporte       | 15,75      | Nubank Cartão | Despesa    |
| 2026-04-17 | iFood Juazeiro do Norte                | Alimentação      | 27,98      | Nubank Cartão | Despesa    |
| 2026-04-17 | Mercadinho São Luiz                    | Alimentação      | 217,64     | Nubank Cartão | Despesa    |
| 2026-04-17 | Temu (parcela 1/6)                     | Compras pessoais | 27,69      | Nubank Cartão | Despesa    |
| 2026-04-18 | Wwwemba*Emb*Catedral                   | Compras pessoais | 144,99     | Nubank Cartão | Despesa    |
| 2026-04-18 | Apple.Com/Bill                         | Assinaturas      | 19,90      | Nubank Cartão | Despesa    |
| 2026-04-19 | iFood Churrascaria Nativa              | Alimentação      | 23,89      | Nubank Cartão | Despesa    |
| 2026-04-19 | Uber                                   | Transporte       | 24,13      | Nubank Cartão | Despesa    |
| 2026-04-21 | Uber                                   | Transporte       | 15,51      | Nubank Cartão | Despesa    |
| 2026-04-21 | Claude.Ai Subscription                 | Assinaturas      | 114,51     | Nubank Cartão | Despesa    |
| 2026-04-21 | IOF Claude.Ai Subscription             | Assinaturas      | 4,00       | Nubank Cartão | Despesa    |
| 2026-04-21 | Uber                                   | Transporte       | 9,40       | Nubank Cartão | Despesa    |
| 2026-04-22 | iFood Antonia Elias                    | Alimentação      | 53,77      | Nubank Cartão | Despesa    |
| 2026-04-23 | Uber                                   | Transporte       | 14,40      | Nubank Cartão | Despesa    |
| 2026-04-23 | Uber                                   | Transporte       | 2,62       | Nubank Cartão | Despesa    |
| 2026-04-23 | Uber                                   | Transporte       | 4,90       | Nubank Cartão | Despesa    |
| 2026-04-23 | Uber                                   | Transporte       | 15,16      | Nubank Cartão | Despesa    |
| 2026-04-24 | Diniz Supermercados                    | Alimentação      | 37,81      | Nubank Cartão | Despesa    |
| 2026-04-24 | Uber                                   | Transporte       | 5,29       | Nubank Cartão | Despesa    |
| 2026-04-24 | Cariri Farma                           | Saúde            | 34,79      | Nubank Cartão | Despesa    |
| 2026-04-24 | Uber                                   | Transporte       | 3,91       | Nubank Cartão | Despesa    |
| 2026-04-24 | Uber                                   | Transporte       | 22,50      | Nubank Cartão | Despesa    |
| 2026-04-24 | Apple.Com/Bill                         | Assinaturas      | 14,90      | Nubank Cartão | Despesa    |
| 2026-04-24 | Google YouTube Premium                 | Assinaturas      | 24,90      | Nubank Cartão | Despesa    |
| 2026-04-24 | iFood restaurante                      | Alimentação      | 52,79      | Nubank Cartão | Despesa    |
| 2026-04-25 | Uber                                   | Transporte       | 3,06       | Nubank Cartão | Despesa    |
| 2026-04-25 | Mercadinho São Luiz                    | Alimentação      | 148,99     | Nubank Cartão | Despesa    |
| 2026-04-25 | iFood Mana Restaurante                 | Alimentação      | 27,92      | Nubank Cartão | Despesa    |
| 2026-04-25 | Ml Alimentos — pet                     | Compras pessoais | 61,90      | Nubank Cartão | Despesa    |
| 2026-04-25 | Uber                                   | Transporte       | 8,38       | Nubank Cartão | Despesa    |
| 2026-04-26 | Matuto Pizzaria                        | Alimentação      | 70,00      | Nubank Cartão | Despesa    |
| 2026-04-26 | Amazon Ad Free for Prime               | Assinaturas      | 10,00      | Nubank Cartão | Despesa    |
| 2026-04-26 | Uber                                   | Transporte       | 11,04      | Nubank Cartão | Despesa    |
| 2026-04-26 | Drogaria Feitosa                       | Saúde            | 38,90      | Nubank Cartão | Despesa    |
| 2026-04-27 | iFood Club                             | Assinaturas      | 5,95       | Nubank Cartão | Despesa    |
| 2026-04-27 | Uber                                   | Transporte       | 0,70       | Nubank Cartão | Despesa    |
| 2026-04-27 | Uber                                   | Transporte       | 23,71      | Nubank Cartão | Despesa    |
| 2026-04-27 | Uber                                   | Transporte       | 6,65       | Nubank Cartão | Despesa    |
| 2026-04-27 | Uber                                   | Transporte       | 12,60      | Nubank Cartão | Despesa    |
| 2026-04-27 | Uber                                   | Transporte       | 3,26       | Nubank Cartão | Despesa    |
| 2026-04-28 | Mundo dos Sorvetes                     | Alimentação      | 7,00       | Nubank Cartão | Despesa    |
| 2026-04-28 | Mundo dos Sorvetes                     | Alimentação      | 7,90       | Nubank Cartão | Despesa    |
| 2026-04-29 | Arca Digital Marke (curso)             | Educação         | 103,11     | Nubank Cartão | Despesa    |
| 2026-04-30 | Mp *Teleracoes — pet                   | Compras pessoais | 20,00      | Nubank Cartão | Despesa    |
| 2026-04-30 | Amazon Prime                           | Assinaturas      | 19,90      | Nubank Cartão | Despesa    |
| 2026-04-30 | Pinheiros Restaurante                  | Alimentação      | 78,50      | Nubank Cartão | Despesa    |
| 2026-05-01 | Mp *Gelasdobairro                      | Alimentação      | 50,40      | Nubank Cartão | Despesa    |
| 2026-05-01 | Recarga de celular                     | Assinaturas      | 30,00      | Nubank Cartão | Despesa    |
