# Projeto Atual

## O que estamos construindo

Uma solução pessoal para gerenciar finanças — começando simples e evoluindo conforme a necessidade.

O objetivo é ter clareza sobre onde o dinheiro vai: o que entra, o que sai, quanto sobra, e se estou no caminho certo para os meus objetivos. A solução pode começar como uma planilha bem estruturada e migrar para um app se fizer sentido.

## Funcionalidades principais

- **Registro de transações** — receitas e despesas com data, categoria, conta e descrição
- **Histórico de gastos** — acompanhar o padrão ao longo do tempo
- **Orçamento por categoria** — definir limites e comparar com o realizado
- **Metas financeiras** — acompanhar progresso em relação a objetivos
- **Saldo por conta** — visão do que tenho disponível em cada conta agora
- **Visão consolidada** — resumo geral de despesas e situação financeira

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

### Fase 1 — Planilha estruturada
Testar a hipótese sem escrever código. Google Sheets com abas:
- **Transações** — data, descrição, categoria, valor, conta, tipo (receita/despesa)
- **Orçamento** — limite por categoria vs. realizado no mês
- **Contas** — saldo atual por conta
- **Metas** — objetivo, prazo, progresso atual

### Fase 2 — Web app simples (se a planilha validar o conceito)
- Next.js com Tailwind, deploy na Vercel
- Dados em JSON ou SQLite — sem banco externo
- Import/export CSV para migrar da planilha
