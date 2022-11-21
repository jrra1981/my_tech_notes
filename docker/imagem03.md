# Aprofundando um pouco o conhecimento sobre imagens no Docker

Na página anterior fizemos a criação de nossa primeira imagem no Docker, escrevendo um arquivo Dockerfile do zero. Contudo, no exemplo criado anteriormente há pontos de melhoria e iremos abordar tais pontos, abaixo segue novos comandos que complementam e melhoram a imagem criada anteriormente afim de termos uma imagem mais robusta e alinhada com boas práticas de mercado.

## Instrução EXPOSE

O mapeamento de portas é fundamental para o bom funcionamento dos containers. Nos permite acessar o container por exemplo via browser ou através de alguma outra interface em nosso host. 

A primeira instrução de mapeamento de portas é a instrução "EXPOSE" tal instrução determina em qual porta a nossa aplicação será exposta. Veja o exemplo:

    /*** Estamos expondo nossa aplicação na porta 3000 ***/
    EXPOSE 3000

Dessa forma podemos expôr nossa aplicação na porta mais adequada.

## Instrução ARG

Uma forma mais parametrizada de se expôr a porta é através do uso de variáveis de ambiente. A instrução ARG cria uma variável para o ambiente, contudo ela só pode ser acessada no momento da criação (build) da **imagem** (para acessar no container será preciso outra instrução que será descrita abaixo). Veja o Exemplo:

    /*** Criando o argumento no momento de build para parametrizar a porta que iremos expôr nossa aplicação ***/
    ARG PORT_BUILD=6000

Com isso criamos uma variável de ambiente chamada "PORT_BUILD" e podemos passar essa varíavel para a instrução "EXPOSE", veja o exemplo abaixo:

    /**** Passando a variável de ambiente para a instrução EXPOSE ****/

    EXPOSE $PORT_BUILD

Note que para passar o valor da váriável usamos o operador "$".

## Instrução ENV

Complementando a intrução anterior. A instrução ENV cria uma variável que pode ser lida dentro do container. Veja o exemplo:

    /*** Criando variável de ambiente para ser lida dentro do container ***/
    ENV PORT=$PORT_BUILD

Ou seja dessa forma de dentro do container é feita a leitura da porta que será exposta em nossa aplicação.

## Versão melhorada na nossa primeira imagem Docker

A partir do exemplo da página anterior, fizemos algumas melhorias para tornar mas fácil o mapeamento de portas em nossa imagem. Abaixo segue exemplo de Dockerfile após essa melhoria no mapeamento de portas.

    FROM node:14
    WORKDIR /app-node    
    COPY . .
    ARG PORT_BUILD=6000
    ENV PORT=$PORT_BUILD
    EXPOSE $PORT_BUILD
    RUN npm install
    ENTRYPOINT npm start

## Referências

- [Documentacao Oficial Docker](https://docs.docker.com/engine/reference/builder/)


> [Próximo => Subindo imagens no Docker Hub ](dockerhub.md)

> [Anterior => Criando a primeira imagem com Docker ](imagem02.md)