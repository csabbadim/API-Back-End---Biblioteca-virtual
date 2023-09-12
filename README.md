## Minha API - Biblioteca virtual de livros


Este MVP foi realizado para a sprint **Arquitetura de software**, da pós-Graduação em Engenharia de Software pela PUC-Rio.

O objetivo dessa API é ser uma biblioteca virtual, onde nela, o leitor é capaz de inserir o nome do autor, livro, e se já leu ou pretende ler/reler o livro. O leitor pode também inserir a data de quando leu o livro inserido, ou a data de quando pretende ler.

Foi utilizada a tecnologia Flask, e foram criadas cinco colunas dentro do banco de dados no SQLite, com o nome do livro, do autor, se já leu o livro, se pretende ler/reler e data de leitura.

Essa API utiliza cinco rotas de requisição: /get/livros, /get/procuralivro, /post/livro, /put/alteralivro e /delete/livro.

O primeiro método GET realiza a consulta por todos os livros, o segundo GET realiza a consulta por um livro específico, o método POST realiza o cadastro do livro na base de dados, o método PUT realiza a alteração dos campos "quer ler", "já lido" e "data de leitura", e o método DELETE deleta o livro pra base de dados.

---
## Como executar 


Será necessário ter todas as libs python listadas no `requirements.txt` instaladas.
Após clonar o repositório, é necessário ir ao diretório raiz, pelo terminal, para poder executar os comandos descritos abaixo.

> É fortemente indicado o uso de ambientes virtuais do tipo [virtualenv](https://virtualenv.pypa.io/en/latest/installation.html).

```
(env)$ pip install -r requirements.txt
```

Este comando instala as dependências/bibliotecas, descritas no arquivo `requirements.txt`.

Para executar a API  basta executar:

```
(env)$ flask run --host 0.0.0.0 --port 5000
```

Em modo de desenvolvimento é recomendado executar utilizando o parâmetro reload, que reiniciará o servidor
automaticamente após uma mudança no código fonte. 

```
(env)$ flask run --host 0.0.0.0 --port 5000 --reload
```

Abra o [http://localhost:5000/#/](http://localhost:5000/#/) no navegador para verificar o status da API em execução.

---
## Como executar através do Docker

Certifique-se de ter o Docker instalado e em execução em sua máquina.

Navegue até o diretório que contém o Dockerfile e o requirements.txt no terminal. Execute como administrador o seguinte comando para construir a imagem Docker:

```
$ docker build -t rest-api .
```
Uma vez criada a imagem, para executar o container basta executar, como administrador, seguinte o comando:

```
$ docker run -p 5000:5000 rest-api
```
Uma vez executando, para acessar a API, basta abrir o http://localhost:5000/#/ no navegador.

## Alguns comandos úteis do Docker

Para verificar se a imagem foi criada você pode executar o seguinte comando:
```
$ docker images
```
Caso queira remover uma imagem, basta executar o comando:
```
$ docker rmi <IMAGE ID>
```
Subistituindo o IMAGE ID pelo código da imagem

Para verificar se o container está em exceução você pode executar o seguinte comando:
```
$ docker container ls --all
```
Caso queira parar um conatiner, basta executar o comando:

```
$ docker stop <CONTAINER ID>
```
Subistituindo o CONTAINER ID pelo ID do conatiner

Caso queira destruir um conatiner, basta executar o comando:
```
$ docker rm <CONTAINER ID>
```
Para mais comandos, veja a documentação do docker.