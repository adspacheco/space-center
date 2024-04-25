# Introdução ao Machine Learning

Machine Learning (ML) é um campo da Inteligência Artificial (IA) focado em desenvolver sistemas capazes de aprender e fazer previsões baseadas em dados, sem ser explicitamente programado para isso. A seguir, uma estrutura concisa sobre os conceitos fundamentais de ML, seus tipos, algoritmos e aplicações.

### Conceitos Básicos

* **IA:** Procura imitar comportamentos humanos.
* **ML:** Faz previsões ou toma decisões com base em dados históricos.
* **Deep Learning (DL):** Trata problemas complexos utilizando algoritmos avançados (ex.: Processamento de Linguagem Natural, dados não estruturados).
* **DS:** Aplica técnicas de IA, ML, e DL, juntamente com métodos científicos para extrair insights valiosos para negócios.

### Objetivos do Machine Learning

* **Generalização:** Busca por modelos que se generalizem bem para dados não vistos, ao invés de memorizar os dados de treinamento.
  * Há um foco em trazer clareza sobre como as variáveis explicam o modelo. Isso com ajuda do aprendizado estatístico, uma vez que ML está preocupado em prever!

### Tipos de Aprendizado

* **Supervisionado:** Os dados de treinamento incluem a resposta desejada, chamada de etiqueta (label).
  * **Classificação:** Resposta discreta (ex.: 0/1).
  * **Regressão:** Resposta contínua (ex.: valores monetários).
* **Não Supervisionado:** Não utiliza etiquetas no treinamento. Focado em agrupamento e redução de dimensionalidade.
* **Semi-Supervisionado e Reforço:** Combinações e extensões dos tipos anteriores.

### Algoritmos e Modelos

* **Supervisionados:** Regressão Linear, Regressão Logística, SVM, Árvores de Decisão e Ensembles (Random Forest, AdaBoost, XGBoost, CatBoost), KNN, LightGBM.
* **Não Supervisionados:** Clustering (K-Means, DBSCAN), Redução de Dimensionalidade (PCA, t-SNE), Busca de Padrões (Apriori, FP-Growth).

Modelos simples como o Support Vector Classifier podem oferecer menos acurácia, enquanto modelos mais complexos, como árvores de decisão e redes neurais, exigem cuidado maior com viés/variância.

<figure><img src="../.gitbook/assets/image (1).png" alt="" width="543"><figcaption></figcaption></figure>

### Ferramentas e Técnicas

* **Scikit-Learn:** Biblioteca para análise preditiva de dados.
* **Analytics Base Table (ABT):** Estrutura de dados preparada para análise.
* **Avaliação de Modelos:** Importante para testar a performance dos modelos em dados não vistos.

### Exemplo Aplicação Scikit-Learn

```python
from sklearn.datasets import load_iris
from sklearn.linear_model import LogisticRegression

X, y = load_iris(return_X_y=True)

# Modelo e seus parâmetros
clf = LogisticRegression(random_state=0).fit(X, y)

# Predição 
predictions = clf.predict(X[:2, :])
probabilities = clf.predict_proba(X[:2, :])

# Avaliação
score = clf.score(X, y)
```
