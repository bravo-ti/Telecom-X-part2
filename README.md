# 📊 Telecom-X-parte2

Desafio do curso de **Data Science com Python** da Alura — Parte 2: Machine Learning.

Este projeto analisa os dados da empresa de telecomunicações **TelecomX**, que está enfrentando uma alta taxa de cancelamento de clientes. O objetivo é identificar os fatores que influenciam a evasão e propor soluções com base em modelos de aprendizado de máquina.

---

## 📁 Estrutura do Projeto

- 🔍 Análise exploratória dos dados
- 🧹 Limpeza e tratamento de dados
- 📊 Visualizações
- 🤖 Modelagem com Machine Learning
- ⚖️ Técnicas de balanceamento de dados
- 📈 Avaliação de desempenho dos modelos

---

## 🧪 Instruções de Uso

1. Clone o repositório:
   ```bash
   git clone [https://github.com/seu-usuario/TelecomX_Lparte2.git](https://github.com/bravo-ti/Telecom-X-part2)
   ```

2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```

3. Execute o notebook no [Google Colab](https://colab.research.google.com/) e clique em **"Executar tudo"**.

4. Bibliotecas utilizadas:
   ```python
   import pandas as pd
   import matplotlib.pyplot as plt
   import seaborn as sns
   import numpy as np
   ```

---

## 🧹 Limpeza e Tratamento de Dados

- Os dados foram importados de uma API em formato JSON.
- O DataFrame original possui 7267 linhas e 6 colunas.
- As colunas com dicionários foram normalizadas e concatenadas, resultando em um DataFrame final com 21 colunas.
- A coluna `'Charges.Total'` foi convertida para o tipo `float64`.

---

## 🔍 Análise Exploratória

- Foram criados dois grupos: clientes que cancelaram e clientes que permaneceram.
- A maioria dos cancelamentos ocorre no primeiro mês de uso (`tenure`).
- Visualizações foram geradas para entender padrões de evasão.

---

## 🤖 Modelos de Machine Learning

### 📚 Bibliotecas utilizadas

```python
from sklearn.tree import DecisionTreeClassifier, plot_tree
from sklearn.neighbors import KNeighborsClassifier
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import train_test_split, cross_validate, StratifiedKFold
from sklearn.metrics import accuracy_score, precision_score, recall_score, f1_score, confusion_matrix
from sklearn.preprocessing import MinMaxScaler, OneHotEncoder
from sklearn.compose import ColumnTransformer, make_column_transformer
from imblearn.over_sampling import SMOTE
from imblearn.under_sampling import NearMiss
from imblearn.pipeline import Pipeline as imbpipeline
import pickle
```

---

## 📈 Resultados dos Modelos

| Modelo           | Acurácia | Precisão | Recall | F1-Score |
|------------------|----------|----------|--------|----------|
| Árvore de Decisão| 0.8017   | 0.6749   | 0.4884 | 0.5667   |
| KNN              | 0.7345   | 0.0000   | 0.0000 | 0.0000   |
| Random Forest    | 0.7747   | 0.8058   | 0.1996 | 0.3200   |

> ⚠️ O modelo KNN não conseguiu generalizar bem os dados de treinamento.

---

## ⚖️ Balanceamento de Dados

Foi utilizado o método **NearMiss** para lidar com o desbalanceamento entre classes.

### 📊 Métricas após Undersampling

| Classe | Precisão | Recall | F1-Score | Suporte |
|--------|----------|--------|----------|---------|
| 0      | 0.90     | 0.78   | 0.84     | 1552    |
| 1      | 0.56     | 0.76   | 0.64     | 561     |

- **Acurácia geral**: 0.77  
- **Intervalo de confiança**: [0.4861, 0.9298]  
- **F1-Score médio ponderado**: 0.78

---

## 🤝 Contribuições

Contribuições são bem-vindas!  
Sinta-se à vontade para abrir uma issue ou enviar um pull request.

---

