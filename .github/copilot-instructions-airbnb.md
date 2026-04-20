# Copilot Instructions — Investigação Estatística, Probabilística e Visual
## NYC Airbnb Open Data (AB_NYC_2019)

## Contexto acadêmico
- **Instituição:** Centro Universitário Santo Agostinho — UNIFSA
- **Disciplina:** Análise Avançada de Dados
- **Professora:** Ma. Heloisa Guimarães
- **Curso:** Engenharia de Software

## Quem sou eu
Estudante brasileiro, nível iniciante-intermediário em Python e análise de dados.
Trabalho em português. Prefiro aprender fazendo — me dá estrutura com TODOs, não solução pronta.

## O projeto
Análise completa do dataset NYC Airbnb 2019 cobrindo limpeza, estatística,
probabilidade e visualização de dados.

- **Dataset:** AB_NYC_2019.csv — 48.895 listagens do Airbnb em Nova York (2019)
- **Linguagem:** Python 3
- **Stack:** pandas, numpy, matplotlib, seaborn
- **Estilo de gráfico:** ggplot + seaborn whitegrid

## Estrutura do projeto
```
New York City Airbnb Open Data/
├── .github/
│   └── copilot-instructions.md     ← você está aqui
├── data/
│   ├── raw/
│   │   └── AB_NYC_2019.csv         ← dataset original
│   └── data_tratado_01/
│       └── AB_NYC_2019_20260416.csv ← dataset limpo (saída da Parte 1)
├── notebooks/
│   ├── 01pipeline_AB_NYC.ipynb     ← CONCLUÍDO (Parte 1)
│   └── 02pipeline_AB_NYC.ipynb     ← EM ANDAMENTO (Parte 2)
└── requirements.txt
```

## Colunas do dataset (após limpeza)
| Coluna | Tipo | Descrição |
|---|---|---|
| id | int64 | ID único do anúncio |
| name | str | Nome do anúncio |
| host_id | int64 | ID do anfitrião |
| host_name | str | Nome do anfitrião |
| neighbourhood_group | category | Região (Brooklyn, Manhattan, etc.) |
| neighbourhood | category | Bairro específico |
| latitude / longitude | float64 | Coordenadas geográficas |
| room_type | category | Entire home / Private room / Shared room |
| price | float64 | Preço por noite (outliers removidos) |
| minimum_nights | int64 | Mínimo de noites (outliers > 365 removidos) |
| number_of_reviews | int64 | Total de avaliações |
| last_review | datetime64 | Data da última avaliação |
| reviews_per_month | float64 | Avaliações por mês (outliers > 15 removidos) |
| calculated_host_listings_count | int64 | Qtd de imóveis do anfitrião |
| availability_365 | int64 | Dias disponíveis no ano |

## O que já foi feito

### Parte 1 — Limpeza e Estruturação ✅ (entregue)
- Exploração inicial e tipologia de dados
- Mudança de tipos: category, datetime64, float64
- Tratamento de nulos: `reviews_per_month` → fillna(0); `name`/`host_name` → dropna
- Sem duplicatas encontradas
- Tratamento de outliers com IQR e contexto de negócio:
  - `price`: removidos zeros e acima do limite IQR (limite ≈ $310)
  - `minimum_nights`: removidos > 365 dias
  - `reviews_per_month`: removidos > 15 (limite teórico contextual)
  - `number_of_reviews` e `calculated_host_listings_count`: outliers mantidos (contexto justificou)
- Dataset limpo exportado: `AB_NYC_2019_20260416.csv` com 45.852 linhas × 16 colunas

### Parte 2 — Análise Estatística, Probabilística e Visual 🔄
- Seção 0 (carga do dataset tratado): ✅ feita
- Seção 04 (Análise Univariada): 🔄 em andamento

## O que falta fazer (Parte 2)

### 04 Análise Univariada
- [ ] Tendência central: média, mediana, moda — e qual representa melhor cada variável
- [ ] Dispersão: variância, desvio padrão, amplitude
- [ ] Forma: assimetria (skewness) e curtose (kurtosis)
- [ ] Visualização: histogramas e boxplots por variável

### 05 Probabilidade
- [ ] Probabilidade simples: ex. P(preço > X), P(room_type == 'Entire home')
- [ ] Probabilidade condicional: ex. P(preço alto | neighbourhood_group == 'Manhattan')

### 06 Análise Bivariada
- [ ] Correlação de Pearson (variáveis numéricas lineares)
- [ ] Correlação de Spearman (ordinais / não lineares)
- [ ] Associação: como variável categórica influencia numérica (ex: preço por bairro)

### 07 Visualização com princípios
- [ ] Gráfico correto para cada tipo de análise (comparação, distribuição, relação)
- [ ] Aplicar princípios de Tufte (Data-Ink Ratio), Gestalt, Cleveland & McGill

### 08 Relatório Final de Insights
- [ ] Interpretação de negócio para cada resultado — não apenas números

## Como me ajudar — IMPORTANTE

### ✅ Faça isso
- Me dá estrutura com `# TODO` e hints nos comentários
- Explica um conceito estatístico por vez, de forma simples
- Usa exemplos concretos com as colunas do dataset (price, room_type, neighbourhood_group)
- Código minimalista — só o necessário

### ❌ Evite isso
- Entregar análise completa sem espaço pra eu implementar
- Código verbose ou over-engineered
- Vários conceitos estatísticos novos de uma vez

### Exemplo do formato ideal
```python
# TODO: calcule média, mediana e moda da coluna 'price'
# Hint: .mean(), .median(), .mode()[0]
media = df_tratado['price']...   # complete aqui
```

## Próximo passo atual
Implementar a Análise Univariada (seção 04) — começar pela coluna `price`
