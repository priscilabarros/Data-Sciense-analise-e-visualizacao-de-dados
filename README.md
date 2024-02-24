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

* Agrupar os valores por uma coluna:
``` 
notas.groupby("filmeId")

``` 
Serádevolvido um objeto data frame do groupby do pandas que possibilita ser usado para alguma outra função, por exemplo tirar a média desse grupo:
``` 
notas.groupby("filmeId").mean()

``` 
Na visualização do groupby foi mostrado também a média de outras colunas. Para extração somente da coluna nota podemos fazer o seguinte:
``` 
notas.groupby("filmeId").mean()["nota"]

ou 

notas.groupby("filmeId").mean().nota

``` 

OBS: Para facilitar o retorno do agrupamento de uma coluna pode ser posto o resultado esperado em uma variavel aux, ex:
``` 
medias_por_filme = notas.groupby("filmeId").mean().nota
``` 

* Histograma da media de uma coluna - 
```
 medias_por_filme.plot(kind='hist')

``` 

## *Outra biblioteca gráfica: Seaborn*

* Como utilizar o Seaborn: 
``` 
sns.boxplot(media_por_filme)

``` 

* Gráfico de Histograma no seaborn:
``` 
sns.displot(medias_por_filme)
``` 

* Descrição das medias de uma coluna:
``` 
medias_por_filme.describe()

``` 

## *Biblioteca matematica:*

* Matplotlib - é uma biblioteca de baixo nível matemática utilizada pelo pandas

* importando a biblioteca matplotlib:
``` 
import matplotlib.pyplot as plt
``` 

* histograma da matplotlib
``` 
plt.hist(medias_por_filme)
``` 

* Titulo do histograma na matplotlib:
``` 
plt.title("Histograma das medias dos filmes")

## *Separando Categorias:*

* categoria nominal:
``` 
tmdb.original_language.unique()
``` 
* mostrar uma coluna: 
``` 
tmdb["original_language"]
``` 

## *Exemplo de leitura de um arquivo e a listagem de uma categoria:*

* Faça o upload do arquivo csv no notebook:
 
arquivo: tmdb_5000_movies.csv

* Faça o import da biblioteca pandas:
``` 
import pandas as pd
``` 

* Adicione a leitura do arquivo a uma variavel
``` 
tmdb = pd.read_csv("tmdb_5000_movies.csv")
``` 

* Liste uma categoria nominal do arquivo csv:
``` 
tmdb.original_language.unique()
```

## *Exemplo de Categorias de dados:*
* Categoria nominal: a mostragem dos dados não precisa ser de acordo com uma ordem. Não utiliza uma classificação de acordo com uma regra, no caso da categoria nominal os valores não são ordenaveis como: ordem alfabética, ordem crescente, ordem decrescente.. exemplo de categoria nominal: listagem de idiomas de filmes, nomes de pessoas ...


* Categoria por ordem: é organizada por uma classificação de acordo com uma regra, por exemplo: ordem alfabética, ordem crescente, ordem decrescente.. a mostragem dos dados deverá ser de acordo com uma ordem.

* Categoria quantitativa: é uma categoria onde o valor dos dados contabilizara um valor total. Exemplo: o número de votos em uma pessoa. Cada pessoa terá um número inteiro de votos por exemplo 1, 2, 3, 4, e não 3.5 

* Categoria quantitativa continua: reune valores que podem variar de x a y no entanto contabilizara os valores entre os intervalos menores de x a y por exemplo: a categoria budget de um filme. O orçamento pode ser de 0 a 500 reais mas os centavos também podem variar. 

  




Continuar: Aula 02 - Video 02 - 12:02.
Criar um novo repositorio privado
