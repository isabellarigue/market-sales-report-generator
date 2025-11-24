# Gerador de relatórios de vendas

Este projeto lê uma planilha de vendas, processa os dados, gera gráficos e produz um relatório em Word usando um template como base. O relatório inclui análise qualitativa gerada por IA.

## Funcionalidades

- **Leitura de dados CSV** com informações de vendas
- **Geração automática de 3 gráficos**:
  - Faturamento por categoria
  - Evolução de vendas ao longo do tempo
  - Distribuição de receita por método de pagamento
- **Tabela de indicadores** agregados por loja
- **Análise qualitativa** gerada por IA via API OpenRouter
- **Substituição automática de placeholders** no template Word

## Como Executar

### Instalar dependências

```bash
pip install -r requirements.txt 
```

### Configurar variáveis de ambiente

Crie um arquivo `.env` na raiz do projeto:

```env
OPENROUTER_API_KEY=sua_chave_api_aqui
```

Obtenha sua API key em [OpenRouter](https://openrouter.ai/)

### Configurar settings no código

No arquivo `generate_report.py`, ajuste as configurações conforme necessário:

```python
# ---------- Settings ----------
CSV_PATH = "data/vendas_mercado.csv"             # Caminho do arquivo CSV
TEMPLATE_PATH = "input/template_relatorio.docx"  # Caminho do template do relatório
OUTPUT_DOCX = "output/relatorio_gerado.docx"     # Caminho do relatório final
NAME = "Isabella"                                # Nome do responsável pelo relatório
```

### Executar o script

```bash
python generate_report.py
```

## 📁 Estrutura do Projeto

```
market-sales-report-generator/
├── data/
│   └── vendas_mercado.csv           # Dados de entrada
├── input/
│   └── template_relatorio.docx      # Template do relatório
├── output/
│   ├── relatorio_gerado.docx        # Relatório final
│   ├── grafico_vendas.png           # Gráfico 1
│   ├── grafico_evolucao_vendas.png  # Gráfico 2
│   └── grafico_metodos_pagamento.png # Gráfico 3
├── generate_report.py               # Script principal
├── requirements.txt                 # Dependências
└── .env                             # Configurações (não versionado)
```
