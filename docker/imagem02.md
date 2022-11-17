# Criando a primeira imagem com Docker

Para se criar uma imagem no docker, é preciso descrever a sua "receita" em um Dockerfile. Ou seja, sempre que for criar uma nova imagem há a necessidade de se criar um arquivo chamado Dockerfile na raíz do seu projeto.

Esse arquivo é composto de uma série de instruções que irão descrever o que vai compôr a nossa imagem. Abaixo segue um descritivo de algumas instruções importantes.

## Instrução "FROM"

A instrução "FROM" define de onde vai "partir" a nossa "receita de imagem" (Dockerfile), tal instrução pode conter um sistema operacional (SO), ou ainda, uma imagem mais completa que podemos encontrar no Docker Hub, veja o exemplo abaixo de algumas possibilidades:

    /**** instrução FROM pegando um SO ****/
    FROM ubuntu:20.04

    /**** instrução FROM pegando uma imagem "mais completa" ****/
    FROM node:14

Uma das maiores vantagens de se usar Docker é não precisar sempre instalar um SO do zero. Ou ter que configurar desde o "início" uma máquina nova. Note que, podemos pegar uma aplicação "já mais adiantada" como o caso do segundo exemplo acima, que já iniciamos nossa "receita" de imagem a partir de uma versão do NodeJS (versão 14) sem nos preocuparmos em abstrações de SO, dependências, etc.

## Instrução WORKDIR

A instrução WORKDIR determina qual será o nosso diretório de trabalho, ou seja, onde seráo copiados/instalados as dependências e onde de fato (quando estiver instanciado um container) vai estar rodando nossa aplicação, veja o exemplo:

    WORKDIR /app

Na instrução acima, estamos definindo como nosso diretório de trabalho o diretório "app".

## Instrução COPY

A instrução COPY copia arquivos e ou diretórios para uma localização. Veja o exemplo:

    COPY . /app

O primeiro "." significa o diretório de nosso host onde estão os arquivos/diretórios que devem ser copiados para dentro da imagem. O path "/app" é o destino de onde devem ser copiados os arquivos/diretórios.

Caso você tenha definido um WORKDIR anteriormente, a instrução pode ser assim:

    COPY . .

Sendo que o primeiro "." é o diretório de nosso host e o segundo "." o destino de onde será copiado o arquivo (nosso WORKDIR).

## Instrução RUN

A instrução RUN como o próprio nome diz, executa (roda) uma determinada instrução/comando, veja o exemplo:

    /**** Instalando o NodeJS ****/
    RUN npm install 

## Instrução ENTRYPOINT

A instrução ENTRYPOINT determina o ponto de entrada de nossa aplicação dentro da imagem. Veja o exemplo:

    /**********************************************
    *  O ponto de entrada é a inicialização do Node 
    *********************************************/
    ENTRYPOINT npm start

## Primeira imagem Docker

Abaixo segue um exemplo de Dockerfile de uma primeira imagem que criamos. Essa imagem é baseada na tecnologia [node.js](https://nodejs.org/en/) e tal "receita" (Dockerfile) utiliza as intruções que foram abordadas acima:

    FROM node:14
    WORKDIR /app-node
    COPY . .
    RUN npm install
    ENTRYPOINT npm start


## Referências

- [Documentacao Oficial Docker](https://docs.docker.com/engine/reference/builder/)


> [Próximo => ??? ](imagem02.md)

> [Anterior => O que são imagens? ](imagem.md)