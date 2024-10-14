# Análise de Cancelamentos de Clientes

Este projeto é uma análise de dados em Python, utilizando um arquivo Jupyter Notebook (`.ipynb`), para investigar as causas de cancelamento de clientes com base em uma base de dados no formato CSV.

## Tecnologias Utilizadas

- **Python**
- **Pandas**: Para manipulação e análise de dados.
- **Plotly Express**: Para visualização de dados.

## Base de Dados

A base de dados utilizada é um arquivo `.csv` que contém informações sobre os clientes e seus cancelamentos.

## Análise Realizada

Inicialmente, tratamos todos os dados, obtendo as seguintes proporções de cancelamento:

### Cancelou 1.0 56.8% ❌
### Não cancelou 0.0 43.2% ✔️

## Causas de Cancelamento

A análise revelou os seguintes problemas que levaram ao cancelamento:

- Todos os clientes que adquiriram o contrato mensal cancelaram.
- Todos os clientes com mais de 20 dias de atraso cancelaram.
- Todos os clientes que ligaram mais de 4 vezes no call center cancelaram.
- Todos os clientes com mais de 50 anos cancelaram.
- Todos os clientes que gastaram um valor abaixo de R$500 cancelaram.

## Filtragem dos Dados

Após identificar esses padrões, aplicamos os seguintes filtros à tabela:

```python
tabela = tabela[tabela["duracao_contrato"] != "Monthly"]
tabela = tabela[tabela["dias_atraso"] <= 20]
tabela = tabela[tabela["ligacoes_callcenter"] <= 4]
tabela = tabela[tabela["idade"] <= 50]
tabela = tabela[tabela["total_gasto"] >= 500]

```
Após esses filtros, a proporção de cancelamentos foi:

### Não cancelou |0.0| 95.2% ✔️
### Cancelou |1.0| 4.8% ❌

## Soluções solicitadas à administração da empresa:
- **Contratos Mensais:** Criar Pacotes Atraentes: Desenvolver novas ofertas e promoções para contratos anuais ou semestrais, com benefícios que incentivem a adesão a esses planos em vez do contrato mensal.
- **Atrasos nos Pagamentos:** Implementar Sistema de Lembretes: Estabelecer um sistema de notificações por e-mail ou SMS para lembrar os clientes sobre as datas de vencimento, evitando que os pagamentos ultrapassem 20 dias de atraso.
- **Atendimento ao Cliente:** Priorizar Chamadas Repetidas: Criar um protocolo que priorize as solicitações de clientes que ligam mais de 2 vezes, assegurando que seus problemas sejam resolvidos rapidamente.
- **Clientes Acima de 50 Anos:** Desenvolver Programas de Fidelidade: Criar um programa de recompensas que ofereça benefícios e descontos exclusivos para clientes com mais de 50 anos.
- **Aumentar a Confiança do Cliente:** Oferecer uma Plataforma Interativa: Criar um portal online onde os clientes possam gerenciar seus serviços de forma intuitiva e personalizada, aumentando a transparência nas interações.
