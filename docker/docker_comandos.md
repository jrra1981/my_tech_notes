# Docker primeiros comandos

## Docker hub

Portal onde estão listadas as imagens para se criar containers, para ver mais sobre acesse o [portal Docker hub](https://hub.docker.com/)

## docker pull <nome imagem>

	O comando "docker pull" serve para se fazer o download de uma imagem, como obrigatório você sempre deve passar um nome da imagem, por exemplo, o comando :~$ docker pull php irá baixar uma imagem do PHP.

## docker run

O comando "docker run" é responsável por executar um container em nosso host.

## docker ps

	O comando "docker ps" lista os containers que estão executando no nosso host. Uma variação do comando pode ser :~$ docker container ls

## docker stop

	O comando "docker stop" encerra a execução (desce) de um container no nosso host. Para tanto é preciso passar para o comando o ID do container, ou o "Name" do container veja um exemplo  :~$ docker stop nice_wozniak

## docker start

	O comando "docker start" inicia a execução (sobe) um container no nosso host. Para tanto é preciso passar para o comando o ID do container, ou o "Name" do container veja um exemplo  :~$ docker start b327b96eac19

## docker exec

	O comando "docker exec" executa um comando no container. Para que ele execute o comando de modo interativo, é preciso passar além do exec as diretivas -it, logo, um exemplo do comando poderia ser => :~$ docker exec b327b96eac19 -it bash (no exemplo estamos rodando o comando bash no container ID b327...)

## docker pause

	O comando "docker pause" pausa a execução (pára) um container no nosso host. Para tanto é preciso passar para o comando o ID do container, ou o "Name" do container veja um exemplo  :~$ docker pause nice_wozniak

	Para despausar um conteiner usamos o comando "docker unpause". Um exemplo poderia ser :~$ docker unpause nice_wozniak

## docker rm

	O comando "docker rm" remove um container no nosso host. Para tanto é preciso passar para o comando o ID do container, ou o "Name" do container veja um exemplo  :~$ docker rm nice_wozniak


