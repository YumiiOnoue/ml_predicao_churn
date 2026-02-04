# Análise de Churn de Funcionários
## Descrição do Projeto
Este projeto consiste na construção e avaliação de modelos de Machine Learning para prever a probabilidade de um funcionário deixar a empresa, um problema conhecido como **HR Churn**. O objetivo é identificar padrões nas características dos colaboradores que possam indicar uma alta chance de abandono, permitindo que a área de Recursos Humanos (RH) tome medidas preventivas.

## Objetivo
Construir um modelo preditivo que classifique um funcionário em duas classes:
* Classe '1': Abandono (o funcionário deixou a empresa).
* Classe '0': Permanência (o funcionário permaneceu na empresa).

## Conjunto de Dados
O projeto utiliza o arquivo HR_Abandono.csv, que contém um conjunto de características sobre colaboradores de uma empresa.

### Colunas Principais:
Característica | Descrição
-------------- | ------------
satisfaction_level | Nível de satisfação do colaborador com a empresa.
last_evaluation | Nota da última avaliação de desempenho.
average_montly_hours | Média de horas mensais trabalhadas.
time_spend_company | Tempo de empresa em anos.
Work_accident | Se sofreu acidente de trabalho (0 ou 1).
**left** | **Variável alvo:** 1 se deixou a empresa, 0 se permaneceu.
promotion_last_5years | Se recebeu promoção nos últimos 5 anos (0 ou 1).
salary | Nível salarial (e.g., low, medium, high).
num_project | Número de projetos em que o funcionário está envolvido.
depto | Departamento do funcionário.

## Metodologia
O processo de Machine Learning foi conduzido no notebook analise_abandono.ipynb e seguiu as seguintes etapas:
* **Carregamento e Análise Exploratória (EDA):** Carregamento do dataset e verificação de estrutura, tipos de dados, valores ausentes e estatísticas descritivas.
* **Pré-processamento de Dados:** 
    * Tratamento de variáveis categóricas (como salary e depto) via One-Hot Encoding.
    * Escalonamento de features numéricas para garantir que modelos baseados em distância tenham um bom desempenho
* **Treinamento e Avaliação de Modelos:** O conjunto de dados foi dividido em treino e teste, e diferentes algoritmos foram treinados.
* **Comparação de Resultados:** Os modelos foram avaliados e seus desempenhos comparados.

## Modelos Testados
Foram utilizados três modelos de Machine Learning para a tarefa de classificação:
* Regressão Logística (Logistic Regression)
* Random Forest
* Máquinas de Vetores de Suporte (Support Vector Machines - SVM)

## Métricas de Avaliação
A performance dos modelos foi comparada utilizando as seguintes métricas:

Modelo | Precision | Recall | F1 Score | Acurácia 
:----- | :-------: | :----: | :------: | :-------: 
Regressão Logística | 0.6093 | 0.8768 | 0.7189 | 0.8387 
Random Forest | 0.9899 | 0.9674 | 0.9785 | 0.9900 
SVM | 0.6125 | 0.9292 | 0.7383 | 0.8450 

**Matriz de Confusão**
![imagem](/images/matriz_confusao.png)

**Gráfico ROC**
![images](/images/curva_roc.png)

**Ranking das 10 Variáveis que Impactam o Abandono**
![imagem](/images/importancia_permutacao.png)


## Como executar o projeto
1. Clone o repositório: `git clone https://github.com/YumiiOnoue/ml_predicao_churn.git`
2. Instale as dependências: `pip install -r requirements.txt`
3. Abra o Jupyter Notebook: `jupyter notebook analise_abandono.ipynb`

---
Desafio do Módulo de Machine Learning Avançado - Fase 2. Pós Tech em Data Analytics (FIAP)