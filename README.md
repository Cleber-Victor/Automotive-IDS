# Automotive-IDS

## Grupo

- **Cleber Victor (cvsj)**
- **Heitor Pereira (hmp)**
- **Hugo Medeiros (ham4)**
- **Paulo Filho (prof)**

## Professor

- **Paulo Freitas de Araujo Filho (pfreitas)**

---

Este projeto foi desenvolvido como parte da disciplina de **Detecção de Intrusão** do **Centro de Informática da Universidade Federal de Pernambuco (CIn - UFPE)**, com o objetivo de reproduzir o artigo:  

[**Convolutional neural network-based intrusion detection system for AVTP streams in automotive Ethernet-based networks**](https://www.sciencedirect.com/science/article/abs/pii/S2214209621000073) [1].  

Além disso, utilizamos o framework disponibilizado no seguinte repositório:  [**Automotive IDS Evaluation Framework**](https://github.com/luigiluz/automotive-ids-evaluation-framework/tree/main) [2].  


## Introdução

Este repositório contém a reprodução do método de detecção de intrusão para fluxos AVTP em redes Ethernet automotivas, conforme apresentado no artigo pioneiro na área de segurança de IVNs automotivas. O artigo utiliza datasets próprios, especificamente os conjuntos **Dindoors** e **Ddriving**. Ademais, visando expandir os experimentos, utilizaremos também o dataset **Tow-IDS** para investigar o desempenho do modelo em diferentes cenários.

## Notebooks

O repositório está organizado em duas pastas principais:

### **Replica Artigo**

Contém 5 notebooks:

- **Tratando-dados-indoor.ipynb**: Importação e tratamento dos dados utilizados para o treino e validação do modelo.
- **Tratando-dados-outdoor.ipynb**: Importação e tratamento dos dados utilizados para o teste do modelo.
- **Treinamento_modelo.ipynb**: Definição da arquitetura e treinamento do modelo.
- **Resultados_validacao.ipynb**: Resultados obtidos a partir do treinamento (conjunto de validação).
- **Resultados-teste.ipynb**: Resultados obtidos a partir do conjunto de testes (dados outdoor).

### **TOW**

Com 2 notebooks:

- **ids-projeto-tow-test.ipynb**: Métricas obtidas a partir das avaliações no conjunto de teste.
- **ids-projeto-tow-train.ipynb**: Métricas obtidas a partir das avaliações no conjunto de treino.
- **cnn_ids_feature_generator.py**: Importação e tratamento dos dados utilizados para o treinamento e teste do modelo.
- **data_processing.md**: Explicação do framework utilizado para extração de features. 

## Requisitos

Para reproduzir os experimentos, é necessário ter instalado:

- Python 3.7 ou superior
- TensorFlow e/ou Keras
- scikit-learn
- scapy, pandas, numpy
- Matplotlib e/ou Seaborn

## Referências  

[1] Jeong, S., Jeon, B., Chung, B. and Kim, H.K., 2021. Convolutional neural network-based intrusion detection system for AVTP streams in automotive Ethernet-based networks. Vehicular Communications, 29, p.100338.

[2] L. Luz, “Automotive IDS Evaluation Framework,” GitHub repository, disponível em: https://github.com/luigiluz/automotive-ids-evaluation-framework/tree/main.  

