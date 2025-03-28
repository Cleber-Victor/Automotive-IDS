# Geração de Features com o Framework Automotive IDS Evaluation

Para a geração das features, utilizamos o repositório [Automotive IDS Evaluation Framework](https://github.com/luigiluz/automotive-ids-evaluation-framework).

## Processamento das Features

O processamento das features é realizado por meio do script `execute_feature_generator.py`. A execução pode ser feita da seguinte maneira:

```bash
python3 execute_feature_generator.py --feat_gen_config feat_gen_config.json
```

### Arquivos de Configuração

Utilizamos dois arquivos de configuração para o processamento: um para treino e outro para teste.

#### Configuração para Treino

```json
{
    "feature_generator": "CNNIDSFeatureGenerator",
    "config": {
        "window_size": 44,
        "window_slide": 1,
        "number_of_bytes": 58,
        "multiclass": false,
        "labeling_schema": "TOW_IDS_dataset_one_class",
        "dataset": "TOW_IDS_dataset",
        "suffix": "train",
        "sum_x": false
    },
    "paths": {
        "training_packets_path": "Automotive_Ethernet_with_Attack_original_10_17_19_50_training.pcap",
        "y_train_path": "y_train.csv",
        "output_path": "processed_tow/one_class/"
    }
}
```

#### Configuração para Teste

```json
{
    "config": {
        "dataset": "TOW_IDS_dataset",
        "labeling_schema": "TOW_IDS_dataset_one_class",
        "multiclass": false,
        "number_of_bytes": 58,
        "suffix": "test",
        "sum_x": false,
        "window_size": 44,
        "window_slide": 1
    },
    "feature_generator": "CNNIDSFeatureGenerator",
    "paths": {
        "output_path": "processed_tow/one_class/",
        "training_packets_path": "Automotive_Ethernet_with_Attack_original_10_17_20_04_test.pcap",
        "y_train_path": "y_test.csv"
    }
}
```

> **Nota:** Lembre-se de personalizar os caminhos dos arquivos conforme necessário.

## Problemas e Soluções

### Problema 1: Erro na Função `__calculate_difference_module`

O primeiro problema ocorreu na função `__calculate_difference_module(self, selected_packets)`, localizada na linha **227** do arquivo original:

```
automotive-ids-evaluation-framework/feature_generator/cnn_ids_feature_generator.py
```

A linha problemática era:

```python
difference_module = np.mod(difference_array, 256)
```

O erro ocorreu porque `difference_array` era do tipo `uint8`, e o valor `256` não pôde ser interpretado corretamente. Para resolver esse problema, alteramos a linha para:

```python
difference_module = np.mod(difference_array.astype(np.int16), 256).astype(np.uint8)
```

### Problema 2: Limitação de Memória no Google Colab

O segundo problema foi devido às limitações de memória RAM do Google Colab ao executar o script. Na linha **320** do mesmo arquivo, encontramos o seguinte trecho:

```python
x_array = np.array(X, dtype='uint8')
```

Essa linha converte uma lista de arrays do NumPy em um único array. Durante essa conversão, era necessário alocar uma grande quantidade de memória, e o processo falhava devido à insuficiência de RAM, resultando em um erro `^C`.

#### Solução

Para contornar essa limitação, modificamos a função para que ela retornasse uma lista de arrays, em vez de um único grande array. Durante o salvamento dos dados, dividimos essa lista em **sub-listas**, realizando o processo de conversão e salvamento para cada uma delas separadamente.

Essa alteração se encontra na linha **90** do arquivo modificado.

Como resultado, geramos **oito arrays**, que juntos representam o conjunto de treino do **TOW-IDS** processado.

> **Observação:** Computadores com mais capacidade de memória, como notebooks do Kaggle com **30 GB de RAM** (em comparação aos **12 GB do Colab**), não necessitam dessa solução alternativa.

---

### Arquivo Modificado

O arquivo contendo nossas alterações está disponível em:

```
Automotive-IDS/TOW/cnn_ids_feature_generator.py

```

