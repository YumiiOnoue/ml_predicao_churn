# Previsão de Churn de Funcionários
## Descrição do Projeto
Este projeto consiste na construção e avaliação de modelos de Machine Learning para prever a probabilidade de um funcionário deixar a empresa Komorebi, um problema conhecido como **HR Churn**. O objetivo é identificar padrões nas características dos colaboradores que possam indicar uma alta chance de abandono, permitindo que a área de Recursos Humanos (RH) tome medidas preventivas.

## Objetivo
A Komorebi identificou uma alta taxa de saída de funcionários e busca entender:
1. Quais são as principais causas de demissão voluntária?
2. Podemos prever com precisão quem está em risco de sair?
3. Quais ações preventivas o RH pode tomar?

## Conjunto de Dados
O projeto utiliza o arquivo HR_Abandono.csv, que contém um conjunto de características sobre colaboradores de uma empresa, tais como:

* satisfaction_level - Nível de satisfação do colaborador com a empresa.
* last_evaluation - Nota da última avaliação de desempenho.
* average_montly_hours - Média de horas mensais trabalhadas.
* time_spend_company - Tempo de empresa em anos.
* Work_accident - Se sofreu acidente de trabalho (0 ou 1).
* **left** - **Variável alvo:** 1 se deixou a empresa, 0 se permaneceu.
* promotion_last_5years - Se recebeu promoção nos últimos 5 anos (0 ou 1).
* salary - Nível salarial (e.g., low, medium, high).
* num_project - Número de projetos em que o funcionário está envolvido.
* depto - Departamento do funcionário.

## Tecnologias e Ferramentas
* **Linguagem:** Python
* **Bibliotecas Principais:** Pandas, Seaborn, Scikit-Learn, SciPy, Imbalanced-Learn (SMOTE).
* **Modelos Utilizados:** Regressão Logística, Random Forest e Support Vector Machine (SVM).

## Etapas do Projeto
### 1. Análise Exploratória e Estatística
* **Testes de Hipótese:** Realização de Testes T e Qui-Quadrado para validar se variáveis como "Número de Projetos" e "Acidentes de Trabalho" tinham impacto estatisticamente relevante no abandono.
* **Visualização de Dados:** Gráficos de distribuição e matrizes de confusão para entender o comportamento das variáveis.

### 2. Engenharia de Variáveis (Feature Engineering)
Criação de novos indicadores para aumentar o poder preditivo:
* `hours_per_project`: Relação entre horas trabalhadas e número de projetos.
* `satisfaction_evaluation_ratio`: Equilíbrio entre a satisfação do funcionário e sua performance.

### 3. Pré-processamento e Modelagem
* Tratamento de outliers.
* **Balanceamento de Classe:** Utilização de **SMOTE** para lidar com o desbalanceamento (mais funcionários ficam do que saem).
* **Escalonamento:** Padronização de dados numéricos com `StandardScaler`.

## Resultados e Performance
A performance dos modelos foi comparada utilizando as seguintes métricas:

Modelo | Precision | Recall | F1 Score | Acurácia 
:----- | :-------: | :----: | :------: | :-------: 
Regressão Logística | 0.6093 | 0.8768 | 0.7189 | 0.8387 
**Random Forest** | **0.9899** | **0.9674** | **0.9785** | **0.9900** 
SVM | 0.6125 | 0.9292 | 0.7383 | 0.8450 

**Matriz de Confusão**

![imagem](/images/matriz_confusao.png)

**Gráfico ROC**

![images](/images/curva_roc.png)

**Ranking das 10 Variáveis que Impactam o Abandono**

![imagem](/images/importancia_permutacao.png)

## Principais Insights
* **Nível de Satisfação:** É o preditor mais forte. Quedas nesse índice são alertas imediatos.
* **Sobrecarga de Trabalho:** Colaboradores com mais de 5 projetos ou carga horária superior a 250h/mês apresentam risco crítico.
* **Tempo de Casa:** Existe um pico de churn entre o 3º e o 5º ano de empresa.

## Recomendações para o RH
1. **Entrevistas de Retenção:** Focar em colaboradores com alta performance, mas baixa satisfação.
2. **Revisão de Carga Horária:** Monitorar o KPI `hours_per_project` para evitar burnout no time técnico.
3. **Plano de Carreira:** Implementar revisões salariais ou de cargo nos marcos de 3 anos de empresa.

## Como executar o projeto
1. Clone o repositório: `git clone https://github.com/YumiiOnoue/ml_predicao_churn.git`
2. Instale as dependências: `pip install -r requirements.txt`
3. Abra o Jupyter Notebook: `jupyter notebook analise_abandono.ipynb`

---

Desafio do Módulo de Machine Learning Avançado - Fase 2. Pós Tech em Data Analytics (FIAP)
