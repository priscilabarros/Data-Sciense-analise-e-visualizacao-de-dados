# Data-Sciense-analise-e-visualizacao-de-dados
Como analisar uma base de dados


## *Preparação do ambiente:*

* Colaboratory: https://colab.research.google.com/drive/1ih47GTjBWveck-FBRsghVzRRMkMuMyXX#scrollTo=I8RRLZwf5zdi

* é uma ferramenta para usar notebooks na nuvem, esta ferramenta é associada à uma conta gmail.

* O notebook criado executa os códigos desejados em uma máquina virtual dedicada a sua conta.

* Restaurar seu notebook:
faça o upload do arquivo .csv e executar as opções "Runtime" e "Restart and run all..."

* Existe um site https://grouplens.org/datasets/movielens/ chamado Movielens que  
disponibiliza avaliações de filmes. Pode ser usado como base de dados para testes.

* CSV - significa (Comma Separator Value) extensão de arquivos muito utilizados para salvar informações a ser trabalhadas para extrair dados. Possui uma extrutura bem simples, somente as informações das colunas separadas por virgulas.

## *Iniciando um projeto:*

* Pandas - biblioteca do python com um módulo que lê arquivos csv. Muito utilizada paratrabalhar com dados.

* Importar a biblioteca pandas usa-se o comando:

´´´
import pandas as pd

´´´
* Para ler um arquivo csv usa-se o comando:

´´´
pd.read_csv("ratings.csv")

´´´

* Para que o Jupiter encontre o arquivo que deseja ler, o arquivo deve estar no mesmmo diretório da onde estiver sendo rodado ou deve ser descrito o path de onde o arquivo se encontra.

* Para subir um arquivo no Jupiter o usuário deve clicar no menu lateral, escolher a seção Files, depois fazer o upload do arquivo.

* atribuir as linhas e resultados de dados de um arquivo csv a uma variável com o intuito de não mostrar visualmente o resultado total de linhas do arquivo e facilitar o manejo de dados:

´´´
notas = pd.read_csv("ratings.csv")

´´´ 

* Mostrar as 5 primeiras linhas de um arquivo csv:

```
notas.head()

```

* Mostrar o formato da tabela 

```
notas.shape

```

* Alterar nome de Colunas:
```
notas.columns = ["usuarioId","filmeId","nota","momento"]
``` 
* Valores de uma coluna:
``` 
notas['nota']
``` 

* Saber quais são os valores unicos dentre uma coluna

``` 
notas['nota'].unique()
``` 

* Quantas repetições de um valor em uma coluna 
``` 
notas['nota'].value_counts()
``` 

* Media das notas em uma coluna
``` 
notas['nota'].mean()
``` 

* Acessar uma coluna:
``` 
notas.nota
``` 

* Plotar - imprimir na tela visualmente

``` 
notas.nota.plot() 

``` 

* histograma - distribuição dos valores em um gráfico
``` 
notas.nota.plot(kind='hist')
``` 

* imprimir a mediana:
``` 
print(notas['nota'].mean())

print(notas['nota'].median())
``` 

* Describe - dá diversas medidas de descrição de forma automatica
``` 
notas.nota.describe()

``` 

* Seaborn - biblioteca de visualizações do panda
``` 
import seaborn as sns
``` 

* Boxplot - mostra visualmente as informações do describe
``` 
sns.boxplot(notas.nota)
``` 

* Query - para cruzar informações entre colunas é necessário fazer uma query. Por exemplo saber a nota de um determinado filme:
``` 
notas.query("filmeId==1").nota
notas.query("filmeId==1").nota.mean()
``` 

* Comentários - podem ser feitos nos notebooks virtuais também. Para adicionar um comentário é necessário escolher a opção TEXT.. No botão Move cell up o comentário é movido para cima e no Move cell down é movido para baixo.






Continuar: Aula 02 - Video 02 - 05:22.
Criar um novo repositorio privado
