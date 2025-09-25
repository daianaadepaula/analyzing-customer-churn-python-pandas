# 🚀 Analisando Cancelamento de Clientes

Este projeto tem como objetivo analisar os motivos de cancelamento de clientes em uma empresa com mais de 800 mil clientes, utilizando Python, Pandas e Plotly.
A análise busca identificar padrões de comportamento que levam ao cancelamento e propor ações para reduzir a taxa de churn.
---

## 📋 Pré-requisitos

Antes de rodar o projeto, você precisa ter instalado no seu computador:

- [Python 3.10+](https://www.python.org/downloads/)

Além disso, instale as dependências do projeto:

```bash
pip install pandas openpyxl numpy nbformat plotly ipykernel
```

## 📂 Estrutura do Projeto
.
├── cancelamentos_sample.csv      
├── analise_cancelamentos.ipynb
└── README.md 

No terminal ou no Jupyter Notebook, execute o script ou células do notebook:

```bash
# Rodando o notebook
jupyter notebook analise_cancelamentos.ipynb
```

### 📚 O que eu aprendi com este projeto

* Manipular e limpar bases de dados grandes usando Pandas.
* Identificar problemas em dados (informações vazias, tipos errados).
* Criar gráficos dinâmicos para análise exploratória com Plotly.
* Filtrar dados e aplicar condições para simular cenários e reduzir cancelamentos.

### 📝 Observações

* O CSV de clientes pode ser atualizado para novos dados.
* Para análise detalhada, é importante filtrar os principais fatores de churn.
* A formatação de porcentagem ajuda a interpretar resultados rapidamente.

## ⚠️ Problemas Identificados e Soluções

1- Clientes que ligaram mais de 4 vezes para o callcenter
  * Ação: criar alerta quando o cliente ligar a 3ª vez.
2- Todos os clientes do contrato mensal cancelaram
  * Ação: oferecer descontos ou benefícios para contratos mensais.
3- Clientes com atraso de mais de 20 dias
  * Ação: alerta para o time de cobrança a partir de 10 dias de atraso.

```bash
tabela = tabela[tabela["ligacoes_callcenter"] <= 4]
tabela = tabela[tabela["dias_atraso"] <= 20]
tabela = tabela[tabela["duracao_contrato"] != "Monthly"]
display(tabela["cancelou"].value_counts(normalize=True))
```

## 🔮 Melhorias Futuras

Para evoluir o projeto, algumas ideias são:

* [ ] Automatizar relatórios com gráficos para diferentes segmentos de clientes.
* [ ] Criar dashboards interativos com Plotly Dash ou Streamlit.
* [ ] Implementar alertas automáticos para o time de callcenter ou cobrança.
* [ ] Explorar técnicas de machine learning para prever churn antes que aconteça.
* [ ] Criar uma interface gráfica simples para selecionar o CSV sem precisar editar o código.

