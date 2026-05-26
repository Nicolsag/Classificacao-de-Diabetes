Detecção de Diabetes com Machine Learning
Objetivo

Desenvolver um modelo para identificar casos de dengue com base em dados clínicos, priorizando a redução de falsos negativos.
Abordagem

    Modelos testados: LogisticRegression, RandomForestClassifier, KNeighborsClassifier, LGBMClassifier, XGBClassifier;
    Otimização com Optuna;
    Curva Roc e Matrix de Confusão para visualizaçao do problema.

Resultados AUC

    LogisticRegression: 0.81;
    RandomForestClassifier: 0.81;
    KNeighborsClassifier: 0.76;
    LGBMClassifier: 0.79;
    XGBClassifier: 0.79.

Tecnologias

    Python: Linguagem de programação base;

NumPy: Responsável pela computação numérica e manipulação de tensores e arrays multidimensionais. É o motor de execução utilizado internamente pelo Scikit-learn e XGBoost para realizar os cálculos matemáticos dos algoritmos;

Pandas: Utilizada para a ingestão, limpeza e estruturação dos dados em DataFrames. É a ferramenta que permite o particionamento dos dados e a organização tabular necessária antes da entrada no pipeline de pré-processamento;

Scikit-learn: Biblioteca para modelagem preditiva, métricas de avaliação (Recall, ROC-AUC, Confusion Matrix) e transformações de dados;

XGBoost: Algoritmo de Gradient Boosting otimizado para eficiência computacional;

LightGBM: Framework de Gradient Boosting baseado em árvores de decisão, focado em performance e memória;

Imbalanced-learn: Utilização de ImbPipeline e SMOTE-NC para balanceamento sintético de classes com dados mistos (numéricos e categóricos);

Matplotlib & Seaborn: Bibliotecas para visualização estatística e análise de performance dos modelos;

Optuna: Framework de otimização de hiperparâmetros via Busca Bayesiana (Tree-structured Parzen Estimator);

Joblib: Ferramenta para a serialização e persistência de modelos de Machine Learning, otimizada para manipular grandes arrays NumPy e exportar o classificador para uso em predições futuras.


Link do Google Colab:

https://colab.research.google.com/drive/1V5_scElgR9ReoHiPwzVCMTZLINxCaMOh?usp=sharing
Foi utilizado o dataset de detecção de dengue disponível no Kaggle, contendo dados clínicos e laboratoriais de pacientes:

[https://www.kaggle.com/datasets/aravind3505/dengue-detection-dataset-clinical-data](https://colab.research.google.com/drive/1H69BimJ-gORygj-h97OHO6RHwIHfEh_1#scrollTo=wW3MM3c4U5ns)
Features

    Diabetes_012 |  0 = Sem Diabetes, 1 = Pre Diabetes, 2 = Tem Diabetes|
| HighBP | Pressão alta |
| HighChol | Colesterol alto |
| CholCheck | Fez exame de colesterol nos últimos 5 anos |
| BMI | Índice de Massa Corporal |
| Smoker | Fumou ≥100 cigarros na vida |
| Stroke | Já teve AVC |
| HeartDiseaseorAttack | Doença cardíaca ou infarto |
| PhysActivity | Atividade física nos últimos 30 dias |
| Fruits | Consome frutas ≥1x/dia |
| Veggies | Consome vegetais ≥1x/dia |
| HvyAlcoholConsump | Consumo elevado de álcool |
| AnyHealthcare | Possui acesso a plano de saúde |
| NoDocbcCost | Não foi ao médico por custo |
| GenHlth | Saúde geral (1–5) |
| MentHlth | Dias com saúde mental ruim (0–30) |
| PhysHlth | Dias com saúde física ruim (0–30) |
| DiffWalk | Dificuldade para andar/subir escadas |
| Sex | Sexo: 0 = Feminino, 1 = Masculino |
| Age | Faixa etária (1–13) |
| Education | Nível educacional (1–6) |
| Income | Nível de renda (1–8) |

Pré-processamento de dados

Foram realizadas etapas básicas de limpeza e preparação dos dados:

    remoção de valores ausentes
    remoção de registros duplicados
    padronização dos nomes das variáveis para manter consistência na análise
