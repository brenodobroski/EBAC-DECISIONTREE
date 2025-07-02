# Projeto de Classificação de Score de Crédito com Árvore de Decisão

## Visão Geral do Projeto

Este projeto é uma continuação do estudo de modelos de classificação para predição de score de crédito. Desta vez, foi utilizado o algoritmo de **Árvore de Decisão**, um modelo supervisionado para classificar clientes em três categorias de score: Baixo, Médio e Alto.

O objetivo foi construir um modelo preciso, avaliar sua performance através de métricas detalhadas e, adicionalmente, explorar a importância das features para entender quais variáveis mais influenciam na determinação do score de crédito.

## Metodologia

Uma Árvore de Decisão funciona criando uma estrutura semelhante a um fluxograma, onde cada nó interno representa um teste em uma feature (ex: "Renda > X?"), cada ramo representa o resultado do teste, e cada folha representa uma classe final (score Baixo, Médio ou Alto).

Para este projeto, foram seguidas as seguintes etapas:
1.  **Preparação dos Dados**: Carregamento dos dados de treino (`X_train`, `y_train`) e teste (`X_test`, `y_test`), garantindo a consistência e o balanceamento das classes no conjunto de treino.
2.  **Treinamento do Modelo Completo**: Um primeiro modelo de `DecisionTreeClassifier` (com critério 'gini' e `random_state=0`) foi treinado utilizando todas as features disponíveis.
3.  **Avaliação e Análise de Features**: O modelo completo foi avaliado no conjunto de teste, e suas features mais importantes foram identificadas. A árvore também foi visualizada para entender sua estrutura e profundidade (5 níveis).
4.  **Treinamento do Modelo Reduzido**: Um segundo modelo foi treinado apenas com as duas features mais relevantes (`Income` e `HomeOwnership_Encoded`) para avaliar se um modelo mais simples poderia manter uma performance competitiva.
5.  **Comparação de Resultados**: Os resultados dos dois modelos de árvore foram analisados e comparados, tanto entre si quanto com o modelo Naive Bayes do projeto anterior.

## Ferramentas e Bibliotecas

* **Python 3**
* **Pandas**: Para manipulação de dados.
* **Scikit-learn**: Para implementação do `DecisionTreeClassifier` e métricas (`accuracy_score`, `classification_report`, `confusion_matrix`).
* **Matplotlib** e **Plotly**: Para visualização da árvore de decisão, importância de features e matriz de confusão.
* **Jupyter Notebook**: Como ambiente de desenvolvimento.

## Resultados

Ambos os modelos de Árvore de Decisão apresentaram excelente performance, superando os resultados do modelo Naive Bayes anterior e demonstrando alta capacidade de generalização.

### Modelo 1: Todas as Features
* **Acurácia (Teste)**: 97.56%
* **Métricas Detalhadas**: O modelo demonstrou altíssima precisão e recall para todas as classes, cometendo apenas um erro de classificação na base de teste.
* **Features Mais Importantes**: `Income` (Renda) e `HomeOwnership_Encoded` (Posse de Imóvel) foram identificadas como as variáveis de maior impacto na decisão do modelo.

### Modelo 2: Apenas com as 2 Principais Features
* **Acurácia (Teste)**: 95.12%
* **Análise**: Embora a acurácia tenha sido ligeiramente inferior à do modelo completo (com um erro a mais), a performance ainda é excepcionalmente alta. Isso demonstra que um modelo mais simples e computacionalmente mais leve, focado nas features mais importantes, pode oferecer resultados muito robustos.

## Conclusão

A Árvore de Decisão se mostrou um algoritmo muito eficaz para este problema de classificação de crédito, superando o desempenho do Naive Bayes. A capacidade do modelo de identificar e hierarquizar a importância das features é uma vantagem significativa, permitindo a criação de modelos mais simples e interpretáveis sem uma perda substancial de performance.

O resultado sugere que, para este conjunto de dados, a correlação entre as features (algo que a Árvore de Decisão captura, ao contrário da premissa "ingênua" do Naive Bayes) é fundamental para alcançar uma maior precisão.
