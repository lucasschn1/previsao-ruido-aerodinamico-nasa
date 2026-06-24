# Previsão de Ruído Aerodinâmico (NASA Airfoil Self-Noise) ✈️🔊

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange.svg)](https://scikit-learn.org/)

**Autor:** Lucas Schneider Cordeiro  
**Instituição:** Pontifícia Universidade Católica do Paraná (PUCPR) - Análise e Desenvolvimento de Sistemas

## 📋 Sobre o Projeto
Este repositório contém o desenvolvimento de um modelo de *Machine Learning* para a previsão do nível de pressão sonora (ruído aerodinâmico) gerado por perfis de asas de aeronaves. O projeto faz parte de um processo seletivo para estágio em consultoria de tecnologia e utiliza o dataset **NASA Airfoil Self-Noise**.

O objetivo é prever a variável contínua `scaled-sound-pressure` (em decibéis) a partir de atributos físicos e aerodinâmicos do túnel de vento, caracterizando um problema clássico de **Regressão**.

## Evolução da Arquitetura (Parte I vs. Parte II)

O projeto foi desenvolvido em duas etapas para demonstrar a evolução das boas práticas em Ciência de Dados:

* **Parte I (Abordagem Inicial):** Focada na exploração, seleção de atributos (tratamento de multicolinearidade) e estruturação básica de treinamento e predição.
* **Parte II (Pipeline e Prevenção de Data Leakage):** Reestruturação completa do fluxo de dados. A divisão entre treino e teste foi alocada para o início do processo, e as etapas de normalização (`StandardScaler`) e treinamento (`RandomForestRegressor`) foram encapsuladas em um **Pipeline** do `scikit-learn`. Isso garantiu total rigor metodológico e impediu o vazamento de dados (*data leakage*).

## Tecnologias e Técnicas Utilizadas
* **Linguagem:** Python
* **Bibliotecas:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`
* **Técnicas Empregadas:**
  * Feature Selection (Remoção de variáveis altamente correlacionadas)
  * Data Scaling (StandardScaler)
  * Construção de Pipelines de ML
  * Validação Cruzada e Otimização de Hiperparâmetros (`GridSearchCV`)
* **Algoritmo Preditivo:** Random Forest Regressor

## Resultados e Desempenho
O modelo otimizado com `GridSearchCV` (utilizando 200 árvores de decisão e profundidade máxima) apresentou um desempenho altamente satisfatório na base de teste isolada:
* **MAE (Erro Absoluto Médio):** ~1.33 dB
* **RMSE (Raiz do Erro Quadrático Médio):** ~1.84 dB

A baixa margem de erro confirma a robustez preditiva do modelo e a eficácia da reestruturação via Pipeline.

## 📂 Estrutura de Arquivos
* `nasa.csv` - Dataset original utilizado no treinamento.
* `Atividade Somativa 2.ipynb` - Código-fonte final (Jupyter Notebook).
* `index.html` - Exportação do Notebook da Parte II (Página principal).
* `previsao-ruido-aerodinamico-nasa (PARTE I).html` - Exportação do Notebook da Parte I para fins de comparação.

## Como visualizar o projeto
Você pode visualizar o notebook renderizado diretamente no navegador através do GitHub Pages:
👉 **[Acessar Portfólio do Projeto](https://lucasschn1.github.io/previsao-ruido-aerodinamico-nasa/)**

*(Nota: Para executar o `.ipynb` localmente, clone o repositório e certifique-se de ter o Python e as bibliotecas listadas instaladas no seu ambiente).*
