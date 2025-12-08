# 📘 README — Predição e Classificação de Atrasos em Voos

# 🛫 Projeto — Modelagem Estatística (2º Bimestre)
**Curso:** Ciência da Computação  
**Disciplina:** Modelagem Estatística  
**Alunos:** *Tiago Ferreira da Silva e João Dário Pamplona Arruda*  
**Professor:** *Pedro Henrique Sales Girotto*  

---

# 📌 Sobre o Projeto

Este projeto aplica métodos estatísticos e de Machine Learning para analisar e prever atrasos de voos nos EUA, explorando tanto modelos de **regressão** quanto de **classificação**. A análise segue integralmente a metodologia da disciplina: EDA completa, preparação dos dados, modelagem, avaliação, otimização e conclusões.

---

# 🎯 Objetivos

## Regressão
- Prever o atraso de chegada (`ARRIVAL_DELAY`) em minutos.

## Classificação
- Determinar se um voo irá se atrasar mais de 15 minutos (`IS_DELAYED`).

## Objetivos específicos
- Identificar padrões que influenciam atrasos.
- Comparar diferentes abordagens de modelagem.
- Aplicar métodos estatísticos para suporte à interpretação.
- Avaliar desempenho com métricas adequadas.
- Otimizar modelos e justificar escolhas metodológicas.

---

# 📂 Descrição do Dataset

Os dados utilizados neste projeto foram obtidos através da plataforma **Kaggle** (https://www.kaggle.com/datasets/usdot/flight-delays), que disponibiliza uma versão organizada do dataset oficial do **Bureau of Transportation Statistics (BTS)**. O **BTS** é a fonte primária dos dados originais, disponibilizados sob domínio público pelo **U.S. Department of Transportation**. O **Kaggle** atua apenas como repositório secundário para facilitar acesso e manipulação.

- **Origem:** Bureau of Transportation Statistics (BTS)  
- **Base:** On-Time Performance Dataset  
- **Fonte Oficial:** https://www.transtats.bts.gov  
- **Link do Kaggle:** https://www.kaggle.com/datasets/usdot/flight-delays
- **Licença:** Public Domain — 17 U.S.C. § 105

## Principais variáveis
- `ARRIVAL_DELAY`
- `IS_DELAYED`
- `AIRLINE`
- `DISTANCE`
- `AIR_TIME`
- `SCHEDULED_DEPARTURE`
- `DEP_HOUR`

---

# 🔍 Metodologia

## 1. EDA
- Estatísticas descritivas  
- Tratamento de valores ausentes  
- Detecção e remoção de outliers via IQR  
- Visualizações (histogramas, boxplots, pairplot, heatmap)  
- Testes estatísticos:
  - ANOVA  
  - Teste t  
  - Qui-Quadrado  
  - Shapiro–Wilk  

## 2. Modelagem

### Regressão
- Linear simples  
- Linear múltipla  
- Polinomial  
- Statsmodels para interpretação  
- Diagnósticos: resíduos, normalidade, homocedasticidade (Breusch–Pagan), VIF  

### Classificação
- Naive Bayes  
- Regressão Logística  

## 3. Avaliação dos Modelos

### Regressão
- MAE, RMSE, R²  
- QQ-plot  
- Homocedasticidade  
- Análise dos resíduos  

### Classificação
- Accuracy  
- Precision  
- Recall  
- F1  
- AUC-ROC  
- Matriz de confusão  
- Precision–Recall  

---

# 🔧 Otimização e Comparação

Devido à incompatibilidade do **PyCaret** com Python 3.13.7, toda a otimização foi realizada com **scikit-learn**, incluindo:

- Comparação entre múltiplos modelos  
- Validação cruzada k-fold  
- Ranking por F1-score  
- Tuning de hiperparâmetros via GridSearchCV  

---

# 🧠 Principais Insights

- Atrasos de chegada têm distribuição assimétrica com outliers.  
- Companhias aéreas apresentam diferenças estatisticamente significativas.  
- Variáveis operacionais influenciam atrasos, mas não de maneira linear simples.  
- Regressão múltipla supera a simples, mas ainda viola algumas suposições estatísticas.  
- Regressão Logística tem melhor desempenho geral na classificação.  
- Tuning melhora substancialmente o F1-score.  

---

# ⚠️ Limitações

- Ausência de dados climáticos.  
- Possível viés temporal no dataset.  
- Classe atrasada (`IS_DELAYED = 1`) é desbalanceada.  
- Alguns modelos lineares não atendem completamente os pressupostos estatísticos.

---

# 🛠️ Requisitos e Execução

## Requisitos
```
Python 3.13.7
pandas
numpy
scikit-learn
statsmodels
seaborn
matplotlib
```

## Como executar
1. Clone o repositório  
2. Coloque `flights.csv` na pasta principal
  - Link do dataset `flights.csv`:
https://drive.google.com/drive/u/0/folders/1c1PR_rxQpwD0uSyXFV0c8Xv6pA-ustQU
3. Abra o arquivo `Projeto_Modelagem.ipynb`  
4. Execute as células na ordem  

---

# 📚 Referências

- 2015 Flight Delays and Cancellations (Kaggle). https://www.kaggle.com/datasets/usdot/flight-delays
- Bureau of Transportation Statistics (BTS). https://www.transtats.bts.gov  
- U.S. Department of Transportation — Public Domain (17 U.S.C. § 105)  
- Scikit-learn documentation — https://scikit-learn.org  
- Statsmodels documentation — https://www.statsmodels.org  
- Seaborn Documentation — https://seaborn.pydata.org  
- Montgomery et al. *Introduction to Linear Regression Analysis*  
- Agresti, A. *Foundations of Linear and Generalized Linear Models*  
- Field, A. *Discovering Statistics Using Python*  
