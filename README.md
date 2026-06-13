# 🏚️ O Sonho Americano Inacessível
### A Matemática da Exclusão Imobiliária

> *"O mercado não é imperfeito. Ele é projetado para excluir."*

**Hackathon de Análise de Dados e Machine Learning · Avaliação C3**

---

## O Problema

Olhamos para dados do mercado imobiliário americano e somos enganados por médias. A maior concentração de casas parece estar na faixa acessível — mas é uma armadilha. O "Sonho Americano" de morar com um mínimo de qualidade e conforto foi empurrado para a **zona vermelha da exclusão**.

Este projeto não apenas constrói modelos preditivos. Ele usa a Ciência de Dados para **nomear o sistema**.

---

## O que os algoritmos revelaram

| Técnica | Resultado | O que prova |
|---|---|---|
| Regressão Linear | R² = **87,61%** | A precificação da exclusão é matematicamente rígida |
| Classificação Logística | Acurácia = **93,15%** · Recall = **0,92** | O padrão de exclusão é tão estruturado que um algoritmo o prevê com quase total precisão |
| K-Means + PCA | 4 clusters isolados | A elite (média **US$ 312.933**) e o popular (média **US$ 126.213**) vivem em mundos separados por **US$ 186.000** de abismo |
| Apriori | Lift = **3,92x** | Qualidade, área e garagem funcionam como portões de entrada — atributos básicos viram luxo compulsório |
| LOF | **30 outliers** (2% do dataset) | Especulação e gentrificação têm endereço |

---

## Estrutura do Repositório

```
📦 ANALISE-DADOS-C3/
│
├── 📂 data/
│   ├── train.csv               # Dataset bruto (Kaggle)
│   ├── test.csv
│   ├── sample_submission.csv
│   └── data_description.txt
│
├── 📂 notebook/                # Bastidores técnicos
│   ├── House_Prices.ipynb      # EDA, Feature Engineering, Regressão e Classificação
│   ├── K_Means_PCA.ipynb       # Clusterização e redução de dimensionalidade
│   └── Apriori_LOF.ipynb       # Mineração de associação e detecção de anomalias
│
├── 📄 Storytelling.ipynb       # Apresentação final — narrativa, visualizações e conclusões
├── 📄 requirements.txt
└── 📄 .gitignore
```

---

## Pipeline Técnico

**1. EDA e Feature Engineering**
Limpeza de nulos, remoção de outliers extremos (`GrLivArea > 4000` com preço baixo), transformação logarítmica da variável alvo, one-hot encoding e normalização via `StandardScaler`. Feature selection com `SelectKBest` (top 50 features).

**2. Aprendizagem Supervisionada**
- *Regressão Linear Múltipla* — predição do preço real em dólares
- *Regressão Logística* — classificação binária: Preço Baixo (≤ mediana) vs. Preço Alto

**3. Aprendizagem Não Supervisionada**
- *K-Means (k=4) + PCA* — segmentação de perfis socioeconômicos e visualização 2D dos clusters
- *Algoritmo Apriori* — regras de associação entre atributos estruturais e faixa de preço elite (Top 25%)

**4. Detecção de Anomalias**
- *Local Outlier Factor (LOF)* — identificação de 30 imóveis com relação área/preço atípica (contaminação = 2%)

---

## Equipe

| Nome | 
|---|
| Anna Luiza Tamanini|
| Josué Espadarotte |
| Laisa Camilo |
| Mikaelly Cardoso |
| Victória Teixeira |

---

## Como executar o projeto

**Pré-requisitos:** Python 3.8+

```bash
# 1. Clone o repositório
git clone https://github.com/seu-usuario/ANALISE-DADOS-C3.git
cd ANALISE-DADOS-C3

# 2. Instale as dependências
pip install -r requirements.txt

# Se o mlxtend não for reconhecido pelo Jupyter mesmo após a instalação,
# rode isso diretamente em uma célula do notebook antes de executar:
# import sys
# !{sys.executable} -m pip install mlxtend

# 3. Baixe o dataset no Kaggle e coloque os arquivos em data/
#    → train.csv, test.csv, sample_submission.csv, data_description.txt

# 4. Execute na ordem recomendada:
#    notebook/House_Prices.ipynb      ← comece aqui (EDA e modelos supervisionados)
#    notebook/Apriori_LOF.ipynb       ← outliers e associação
#    notebook/K_Means_PCA.ipynb       ← clusterização
#    Storytelling.ipynb               ← apresentação final (rode por último)
```

> **Atenção:** o `Storytelling.ipynb` referencia os resultados dos outros notebooks. Execute-os antes para garantir que os dados e variáveis estejam disponíveis.

---

## Dataset

[House Prices: Advanced Regression Techniques](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques) · Kaggle
