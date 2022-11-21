# Subindo imagens no Docker Hub

Afim de n�o depender somente do trabalho de terceiros e aprofundar tanto o aprendizado, como a "personaliza��o" de suas imagens. Subir as imagens que voc� cria para dentro do Docker hub � uma excelente op��o. 

## Como subir a imagem que voc� criou no Docker Hub

� poss�vel guardar a imagens que voc� cria no reposit�rio oficial do Docker que � o Docker hub. Para tanto acesse este [link](https://hub.docker.com/) para criar seu perfil no Docker hub e/ou acessar seu espa�o.

Assim como acontece com o uso do GitHub para projetos, o Docker Hub � um lugar onde � poss�vel guardar uma c�pia e versionar as suas imagens Docker. Abaixo ser� apresentado alguns comandos para que voc� possa utilizar esta funcionalidade.

## Autentica��o de sua conta na linha de comando

Para se autenticar a sua conta via shell de comando use o seguinte comando:

    docker login -u <preencha com seu usuario>

## Subindo uma imagem no Docker Hub

Para subir sua imagem no Docker Hub, use o seguinte comando:

    docker push <usuario no docker Hub>/<nome da imagem>

    /*** Um exemplo real abaixo ***/
    docker push joaoricardo/app-node:1.1

S� � poss�vel subir imagens que est�o associadas ao seu usu�rio no Docker Hub. Caso voc� queira subir em seu espa�o a imagem que seja de outro usu�rio, ser� preciso mudar a tag desta imagem com o comando:

    docker tag <nome da imagem>:<tag da imagem>

    /*** Um exemplo real ***/

    docker tag dockersamples/node:1.0 joaoricardo/app-node:1.0

O comando acima vai a partir da imagem passada como primeiro par�metro uma nova tag com o segundo par�metro. Quando voc� rodar o comando "docker images" voc� ver� as duas entradas para a mesma imagem (inclusive com mesmo ID).

> [Pr�ximo =>  ](dockerhub.md)

> [Anterior => Aprofundando um pouco o conhecimento sobre imagens ](imagem03.md)