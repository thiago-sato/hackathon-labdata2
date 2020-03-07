# Desafio Programação PySpark

## Descrição da Tarefa:
   - Dado um dataframe com duas dimensões [id_cliente, categorias]. 
   - Fazer um dataframe resultado, com uma coluna pra cada tipo de categoria, com valor 1 caso aquela categoria exista e 0 caso não exista, isso para cada cliente (one-hot-encoded).

- Regras:
    - Usar pyspark.
    - Pode usar qualquer biblioteca auxiliar.
    - O número de categorias é dinamico e não conhecido de antemão.
    - O script tem que funcionar para os dois dataframes exemplos.
    - Os seus dataframes resposta têm que ser exatamente iguais aos apresentados abaixo.
    - O script deve executar com o menor tempo possível, este tempo de execução será comparado entre os grupos participantes. 
    - Os tempos de execução devem ser medidos e apresentados utilizando o time library do python.

- Bibliotecas necessárias:
```python
from pyspark.sql.types import *
from pyspark.sql.functions import *
import time
start = time.time()
```

- Dataframe de exemplo 1:
```python
df = spark.createDataFrame([
    ('client-uuid-1',  'cat-1, cat-2, cat-3'),
    ('client-uuid-2',  'cat-1, cat-4, cat-5'),
    ('client-uuid-3',  'cat-6, cat-7'),
    ('client-uuid-4',  'cat-1, cat-2, cat-7, cat-10'),
    ('client-uuid-5',  'cat-8, cat-10'),
    ('client-uuid-6',  'cat-1, cat-9, cat-10'),
    ('client-uuid-7',  'cat-1, cat-4, cat-5, cat-10'),
    ('client-uuid-8',  'cat-7, cat-9'),
    ('client-uuid-9',  'cat-1'),
    ('client-uuid-10', 'cat-1, cat-2, cat-3, cat-4, cat-5, cat-6, cat-7, cat-8, cat-10')
], ['id_cliente', 'categorias'])
```

- Dataframe de exemplo 2:
```python
df2 = spark.createDataFrame([
    ('client-uuid-1',  'cat-1, cat-2, cat-3, cat-15'),
    ('client-uuid-2',  'cat-1, cat-4, cat-5, cat-11, cat-14'),
    ('client-uuid-3',  'cat-4, cat-14, cat-15'),
    ('client-uuid-4',  'cat-1, cat-2, cat-7, cat-10'),
    ('client-uuid-5',  'cat-8, cat-10, cat-11'),
    ('client-uuid-6',  'cat-1, cat-9, cat-10, cat-11, cat-13'),
    ('client-uuid-7',  'cat-1, cat-4, cat-5, cat-10'),
    ('client-uuid-8',  'cat-7, cat-9, cat-12, cat-13, cat-14'),
    ('client-uuid-9',  'cat-2'),
    ('client-uuid-10', 'cat-1, cat-2, cat-3, cat-4, cat-5, cat-6, cat-7, cat-8, cat-10')
], ['id_cliente', 'categorias'])
```

- Calcular tempo:
```python
# Seu script
print(time.time() - start)
```

- Dataframe de saída 1 (df1):

![alt text](https://github.com/schmidt-samuel/fia_batalha_de_dados1/blob/master/desafio_programacao/imagens/dataframe_saida1.png)

- Dataframe de saída 2 (df2):

![alt text](https://github.com/schmidt-samuel/fia_batalha_de_dados1/blob/master/desafio_programacao/imagens/dataframe_saida2.png)

