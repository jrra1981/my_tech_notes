# Subindo imagens no Docker Hub

Afim de não depender somente do trabalho de terceiros e aprofundar tanto o aprendizado, como a "personalização" de suas imagens. Subir as imagens que você cria para dentro do Docker hub é uma excelente opção. 

## Como subir a imagem que você criou no Docker Hub

É possível guardar a imagens que você cria no repositório oficial do Docker que é o Docker hub. Para tanto acesse este [link](https://hub.docker.com/) para criar seu perfil no Docker hub e/ou acessar seu espaço.

Assim como acontece com o uso do GitHub para projetos, o Docker Hub é um lugar onde é possível guardar uma cópia e versionar as suas imagens Docker. Abaixo será apresentado alguns comandos para que você possa utilizar esta funcionalidade.

## Autenticação de sua conta na linha de comando

Para se autenticar a sua conta via shell de comando use o seguinte comando:

    docker login -u <preencha com seu usuario>

## Subindo uma imagem no Docker Hub

Para subir sua imagem no Docker Hub, use o seguinte comando:

    docker push <usuario no docker Hub>/<nome da imagem>

    /*** Um exemplo real abaixo ***/
    docker push joaoricardo/app-node:1.1

Só é possível subir imagens que estão associadas ao seu usuário no Docker Hub. Caso você queira subir em seu espaço a imagem que seja de outro usuário, será preciso mudar a tag desta imagem com o comando:

    docker tag <nome da imagem>:<tag da imagem>

    /*** Um exemplo real ***/

    docker tag dockersamples/node:1.0 joaoricardo/app-node:1.0

O comando acima vai a partir da imagem passada como primeiro parâmetro uma nova tag com o segundo parâmetro. Quando você rodar o comando "docker images" você verá as duas entradas para a mesma imagem (inclusive com mesmo ID).

> [Próximo =>  ](dockerhub.md)

> [Anterior => Aprofundando um pouco o conhecimento sobre imagens ](imagem03.md)