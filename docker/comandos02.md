## docker port

O comando "docker port" mostra o mapeamento de portas de um container em relação ao host. Este comando sempre deve ser seguido do ID do container. Veja o exemplo:

	:~$ docker port b327b96eac19

Uma outra possibilidade é na hora da criação do container, especificar uma porta que deve ser mapeada com relação ao host. Veja o exemplo: 	

	:~$ docker run -d -p 8080:80 dockersamples/static-site

O comando acima está mapeando a porta 8080 do meu host, associada a porta 80 do container. Para tanto é usada a diretiva "-d" para configurar tal mapeamento de portas.

> [Próximo => O que são imagens? ](imagem.md)

> [Anterior => Primeiros comandos ](comandos01.md)