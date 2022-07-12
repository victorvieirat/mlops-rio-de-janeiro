# mlops-rio-de-janeiro
[Youtube Link](https://www.youtube.com/watch?v=GRWEFZwzmSc)
 Trabalho realizado por:
- EMANUEL COSTA BETCEL 
- VICTOR VIEIRA TARGINO

## AMBIENTE
No arquivo environment.yml encontra-se todos o ambiente necessário para exectuar as ferramentas utilizadas.

## ETL
Nesse passo foram coletados dadso do AIRBNB do Rio da Janeiro e realizado o tratamento dos dados, remoção de colunas desnecessárias, transformando todas em númerico, realizand One Hot Enconding nas variáveis categóricas nominais. Além disso o [Coeficiente de correlação ponto-bisserial](https://pt.wikipedia.org/wiki/Coeficiente_de_correla%C3%A7%C3%A3o_ponto-bisserial), que é utilizado para comparar variáveis numéricas de binárias (dicotômicas) foi utilizado para realziar a seleção de alguns atributos. Além disso foi realizado um tratamento na variável preço para deixar sua distribuição mais próxima de uma curva normal. É possível ver uma descrição dos dados antes do tratamento no arquivo ETL/report.html

## Chekcing

Para rodar os testes execute

```bash
pytest . -
```

## Segregation

Para realizar a segregação dos dados execute

```bash
mlflow run . -P input_artifact="mlops-rio-de-janeiro/preprocessed_data.csv:latest" -P artifact_root="data" -P artifact_type="trainvaltest_data" -P test_size=0.3
```
Essa execução está em uma linha só diferente do que foi apresentado nas aulas pois pelo menos no computador dos usuários que utilizaram o uso da \ com a quebra de linha para executar o código apresentava problemas
