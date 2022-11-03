# Docker imagens

Estrutura de camadas que juntas formam uma "imagem" de uma m�quina, ou seja, uma imagem � uma s�rie de abstra��es que atuam em camadas como SO, IO, network, etc, que juntas "formam" uma "receita" para um host/m�quina virtual/container.

# docker images

O comando "docker images" lista as imagens baixadas em nosso host. 

    ~:$ docker images

Uma varia��o deste comando poderia ser "docker image ls".

    ~:$ docker images ls

# docker inspect

O comando "docker inspect" detalha a composi��o de uma imagem, este comando sempre deve ser seguido do ID da imagem. Veja o exemplo:

    ~:$ docker inspect 3a30f5e62a03

# docker history

O comando "docker history" detalha cada camada que comp�em uma imagem Docker, este comando sempre deve ser seguido do ID da imagem. Veja o exemplo:

    ~:$ docker history 3a30f5e62a03

> [Pr�ximo => Criando imagens ](imagem02.md)

> [Anterior => Comandos de networking ](comandos02.md)