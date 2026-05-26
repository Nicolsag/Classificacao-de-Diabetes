#  Detecção de Diabetes com Machine Learning

##  Objetivo

Desenvolver um modelo de Machine Learning capaz de identificar a presença de diabetes com base em dados clínicos e comportamentais, com foco na **redução de falsos negativos**, priorizando a detecção correta de pacientes doentes.

---

## 🔍 Abordagem

Foram avaliados diferentes algoritmos de classificação supervisionada:

- Logistic Regression  
- Random Forest Classifier  
- K-Nearest Neighbors (KNN)  
- LightGBM  
- XGBoost  

A otimização de hiperparâmetros foi realizada utilizando **Optuna**, com abordagem bayesiana (*Tree-structured Parzen Estimator - TPE*).

A avaliação dos modelos foi baseada em:

- ROC-AUC  
- Recall  
- Matriz de Confusão  

---

##  Resultados (ROC-AUC)

| Modelo               | ROC-AUC |
|---------------------|--------|
| Logistic Regression | 0.81   |
| Random Forest       | 0.81   |
| KNN                 | 0.76   |
| LightGBM            | 0.79   |
| XGBoost             | 0.79   |

---

##  Interpretação dos Resultados

Os modelos apresentaram desempenho semelhante, com destaque para:

- **Logistic Regression** e **Random Forest**, que atingiram o melhor desempenho geral;
- Modelos de boosting (LightGBM e XGBoost) com resultados competitivos.

Como o objetivo do projeto é minimizar erros críticos, a análise vai além do ROC-AUC, considerando principalmente a capacidade do modelo de identificar corretamente casos positivos.

---

##  Matriz de Confusão

A matriz de confusão permite avaliar o desempenho do modelo em termos de acertos e erros:

- **Verdadeiros Positivos (TP):** casos de diabetes corretamente identificados  
- **Falsos Negativos (FN):** casos de diabetes classificados como saudáveis (**erro crítico**)  
- **Falsos Positivos (FP):** indivíduos saudáveis classificados como doentes  
- **Verdadeiros Negativos (TN):** indivíduos saudáveis corretamente classificados  

Dado o contexto, o modelo ideal deve:

- Maximizar **Recall**
- Minimizar **Falsos Negativos (FN)**, mesmo com aumento controlado de falsos positivos  

---

##  Tecnologias Utilizadas

- **Python** — linguagem principal  
- **NumPy** — computação numérica  
- **Pandas** — manipulação e estruturação de dados  
- **Scikit-learn** — modelagem e métricas  
- **XGBoost** — gradient boosting otimizado  
- **LightGBM** — boosting eficiente em memória e performance  
- **Imbalanced-learn** — balanceamento com SMOTE-NC  
- **Matplotlib & Seaborn** — visualização de dados  
- **Optuna** — otimização de hiperparâmetros  
- **Joblib** — persistência do modelo  

---

##  Pré-processamento de Dados

- Remoção de valores ausentes  
- Remoção de registros duplicados  
- Padronização dos nomes das variáveis  

---

##  Dataset

Dataset utilizado:

- [Dengue Detection Dataset (Kaggle)](https://www.kaggle.com/datasets/aravind3505/dengue-detection-dataset-clinical-data)

> *Obs.: Dataset reaproveitado e adaptado para análise de classificação.*

---

##  Acesso ao Projeto

- [Google Colab](https://colab.research.google.com/drive/1V5_scElgR9ReoHiPwzVCMTZLINxCaMOh?usp=sharing)
