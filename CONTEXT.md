# Projeto Atual

## O que estamos construindo

Uma solução pessoal para gerenciar finanças — começando simples e evoluindo conforme a necessidade.

O objetivo é ter clareza sobre onde o dinheiro vai: o que entra, o que sai, quanto sobra, e se estou no caminho certo para os meus objetivos. A solução começa como arquivos markdown no repositório (lidos/editados pelo Claude) e pode migrar para um app se fizer sentido.

## Funcionalidades principais

Escopo inicial (Fase 1):

- **Registro de transações** — receitas e despesas com data, categoria, conta e descrição
- **Histórico de gastos** — acompanhar o padrão ao longo do tempo
- **Saldo por conta** — visão do que tenho disponível em cada conta agora
- **Visão consolidada** — resumo geral de despesas e situação financeira

Fora do escopo inicial (entram quando tiver 1-2 meses de histórico ou quando fizer falta):

- **Orçamento por categoria** — definir limites e comparar com o realizado
- **Metas financeiras** — acompanhar progresso em relação a objetivos

## Contas monitoradas

Saldos iniciais em `contas.md`. Agrupadas por papel:

**Conta corrente / liquidez**
- **Nubank CC** — fonte da verdade, uso diário
- **Bradesco** — recebe salário, paga contas fixas (baixo volume)
- **Mercado Pago** — conta (baixo volume)

**Cartões de crédito** (saldo geralmente negativo = fatura em aberto)
- **Nubank Cartão** — exporta fatura em CSV (único canal automatizável hoje)
- **Mercado Pago Cartão**
- **Cartão Amazon** — final 1017

**Empréstimos** (saldo negativo = dívida em aberto)
- **Nubank Empréstimo 1**
- **Nubank Empréstimo 2**
- **Naassom** — dívida pessoal

**Investimentos** (saldo positivo, atualização periódica manual)
- **Nubank Renda Fixa**
- **Nubank Bolsa**

Cartões de crédito e empréstimos são tratados como **contas separadas** com saldo negativo. Pagamento da fatura/parcela é modelado como transferência da conta corrente pra conta da dívida, aproximando o saldo de zero. Isso evita contar a mesma despesa duas vezes (na compra e no pagamento).

## O que é um bom resultado

- Saber exatamente onde o dinheiro foi no mês
- Conseguir identificar padrões e oportunidades de ajuste
- Dados confiáveis o suficiente para tomar decisões
- Solução que eu consiga usar de forma consistente (não abandonar depois de duas semanas)

## O que evitar

- Complexidade prematura — não construir o que não precisa existir ainda
- Integrações desnecessárias — sem Open Banking ou conexões com bancos por enquanto
- Duplicar o que os bancos já fazem — o objetivo é análise e contexto, não extrato
- Soluções bonitas no protótipo mas inviáveis de manter no dia a dia

## Arquitetura por fase

### Fase 1 — Arquivos markdown
Testar a hipótese sem escrever código e sem depender de Sheets/Excel (conectar planilha ao Claude no iPad estava inviável). Dois arquivos de dados na raiz:
- **`transacoes.md`** — tabela corrida com data, descrição, categoria, valor, conta, tipo (receita/despesa/transferência)
- **`contas.md`** — saldo inicial e data de referência por conta

Categorias em `docs/CATEGORIAS.md`. Visão consolidada (saldo por conta, receitas/despesas do mês, gasto por categoria) é calculada **sob demanda** pelo Claude a partir dos dois arquivos — não existe arquivo de dashboard fixo.

Detalhes da estrutura e do workflow estão em `docs/`.

### Fase 1.5 — Orçamento e metas
Depois de 1-2 meses de dados confiáveis, adicionar **Orçamento** (limite por categoria vs. realizado) e **Metas** (objetivo, prazo, progresso) como novos arquivos markdown.

### Fase 2 — Web app simples (se os markdowns validarem o conceito)
- Next.js com Tailwind, deploy na Vercel
- Dados em JSON ou SQLite — sem banco externo
- Import dos `.md` existentes para migrar
