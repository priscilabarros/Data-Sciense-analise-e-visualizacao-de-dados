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
´´´
notas.head()

´´´




Continuar: Aula 01 - Video 04 - 09:40.
Criar um novo repositorio privado
