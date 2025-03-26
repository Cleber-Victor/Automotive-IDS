# Automotive-IDS
Projeto da Disciplina de Detecção de Intrusão, focado da reprodução do artigo : [Convolutional neural network-based intrusion detection system for AVTP streams in automotive Ethernet-based networks](https://www.sciencedirect.com/science/article/abs/pii/S2214209621000073).

## Introdução

Este repositório contém a reprodução do método de detecção de intrusão para fluxos AVTP em redes Ethernet automotivas, conforme apresentado no artigo pioneiro na área de segurança de IVNs automotivas. O artigo utiliza datasets próprios, especificamente os conjuntos **Dindoors** e **Ddriving**. Ademais, visando expandir os experimentos, utilizaremos também o dataset **Tow-IDS** para investigar o desempenho do modelo em diferentes cenários.

## Notebooks

O repositório está organizado em três notebooks principais:
- Preprocessamento.ipynb:
  Responsável pela extração, limpeza e preparação dos dados a partir dos datasets (Dindoors, Ddriving e Tow-IDS). Nesta etapa, também é realizada a extração de features conforme descrito no artigo, preparando os dados para alimentar o modelo de CNN.
- Treinamento.ipynb:
  Contém o código para a definição da arquitetura da rede neural convolucional (CNN), configuração dos hiperparâmetros e o treinamento do modelo.
  
- Resultados.ipynb: Apresenta a avaliação do modelo, métricas de desempenho, análise de erros e visualizações dos resultados obtidos.

## Requisitos

Para reproduzir os experimentos, é necessário ter instalado:

- Python 3.7 ou superior
- TensorFlow e/ou Keras
- scikit-learn
- pandas, numpy
- Matplotlib e/ou Seaborn

