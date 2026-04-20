# 🗽 New York City Airbnb Open Data

Projeto de análise e tratamento de dados do Airbnb em Nova York com foco em limpeza, preparação e geração de dataset final para exploração e visualizações.

# 👥 Participantes

- Nome 1: João Pedro Balduino Leitão
- Nome 2: Caio Palcio
- Nome 3: Samuel de Sousa
- Nome 4: José Alves
- Nome 5: Enzo Santos

## 📌 Objetivo

Transformar os dados brutos do Airbnb (`AB_NYC_2019.csv`) em uma base tratada e pronta para análise, seguindo um pipeline em notebooks.

## 🧰 Tecnologias

- Python
- Pandas
- NumPy
- SciPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## 📂 Estrutura do projeto

```text
├── data/
│   ├── raw/
│   │   └── AB_NYC_2019.csv
│   ├── data_tratado_01/
│   │   └── AB_NYC_2019_20260416.csv
│   └── data_tratado_02_completo/
│       └── AB_NYC_2019_final_20260420.csv
├── notebooks/
│   ├── 01pipeline_AB_NYC.ipynb
│   └── 02pipeline_AB_NYC.ipynb
└── requirements.txt
```

## ▶️ Como executar

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

Depois, abra os notebooks na pasta `notebooks/` e execute na ordem:

1. `01pipeline_AB_NYC.ipynb`
2. `02pipeline_AB_NYC.ipynb`

## 🔄 Pipeline

1. Leitura dos dados brutos
2. Limpeza e tratamento de inconsistências
3. Transformações e padronizações
4. Geração de datasets tratados
5. Preparação para análise e visualização

## 📊 Dataset final

Arquivo final gerado:

`data/data_tratado_02_completo/AB_NYC_2019_final_20260420.csv`