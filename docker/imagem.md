# Docker imagens

Estrutura de camadas que juntas formam uma "imagem" de uma máquina, ou seja, uma imagem é uma série de abstrações que atuam em camadas como SO, IO, network, etc, que juntas "formam" uma "receita" para um host/máquina virtual/container.

# docker images

O comando "docker images" lista as imagens baixadas em nosso host. 

    ~:$ docker images

Uma variação deste comando poderia ser "docker image ls".

    ~:$ docker images ls

# docker inspect

O comando "docker inspect" detalha a composição de uma imagem, este comando sempre deve ser seguido do ID da imagem. Veja o exemplo:

    ~:$ docker inspect 3a30f5e62a03

# docker history

O comando "docker history" detalha cada camada que compõem uma imagem Docker, este comando sempre deve ser seguido do ID da imagem. Veja o exemplo:

    ~:$ docker history 3a30f5e62a03

> [Próximo => Criando imagens ](imagem02.md)

> [Anterior => Comandos de networking ](comandos02.md)