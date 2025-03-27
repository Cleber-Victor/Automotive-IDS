# Automotive-IDS

## Grupo

- **Cleber Victor (cvsj)**
- **Heitor Pereira (hmp)**
- **Hugo Medeiros (ham4)**
- **Paulo Filho (proj)**

## Professor

- **Paulo Freitas de Araujo Filho (pfreitas)**

---

Este projeto foi desenvolvido como parte da disciplina de **Detecção de Intrusão** do **Centro de Informática de Universidade Federal de Pernambuco (CIn - UFPE)**, com o objetivo de reproduzir o artigo:

[**Convolutional neural network-based intrusion detection system for AVTP streams in automotive Ethernet-based networks**](https://www.sciencedirect.com/science/article/abs/pii/S2214209621000073)

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

### **TOW-IDS**

Com X notebooks: 

## Requisitos

Para reproduzir os experimentos, é necessário ter instalado:

- Python 3.7 ou superior
- TensorFlow e/ou Keras
- scikit-learn
- scapy, pandas, numpy
- Matplotlib e/ou Seaborn

