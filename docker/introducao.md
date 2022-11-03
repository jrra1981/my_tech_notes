# Docker

Docker é uma plataforma aberta, criada com o objetivo de facilitar o desenvolvimento, a implantação e a execução de aplicações em ambientes isolados. Foi desenhada especialmente para disponibilizar uma aplicação da forma mais rápida possível.

Usando o Docker, você pode facilmente gerenciar a infraestrutura da aplicação, isso agilizará o processo de criação, manutenção e modificação do seu serviço.

## O que é hypervisor?

Camada que isola o sistema operacional original, dos sistemas operacionais das máquinas virtuais. Faz uma interface entre a máquina física original com as diversas máquinas virtuais que possam existir dentro da máquina física original.

## O que é um container?

Será que sempre para haver aplicações separadas (máquinas virtuais) é necessário o uso de hypervisor? Hypervisor consome bastante recurso da máquina e fica restrito as implementações dos diversos SOs. Surge então um novo conceito, o container. Um container funciona como um processo dentro do sistema operacional, economizando recursos e não havendo a necessidade de uma instalação SO "dentro da máquina virual".

Os containers conseguem se isolar um do outro, utilizando um conceito chamado "Namespaces" existem diversos namespaces e cada um trabalha em um aspecto (camada) de isolamento dos containers, sendo eles:

	1. PID - Garante o isolamento a nível de processo dentro de cada um dos containers. Então um processo dentro de um container, que consequentemente é um processo dentro do nosso sistema operacional, vai estar isolado de todos os outros do nosso host, da nossa máquina original.

	2. NET - Namespace de rede, que vai garantir o isolamento entre uma interface de rede de cada um dos containers e também do nosso sistema operacional original.

	3. IPC - Atua na intercomunicação entre cada um dos processos da nossa máquina.

	4. MNT - Namespace voltado para o tratamento de files system, sistema de arquivos, montagem, volumes e afins. Também estará devidamente isolado.

	5. UTS - Faz um compartilhamento, um isolamento ao mesmo tempo também, de host do nosso Kernel da máquina que está escutando o container. Ou seja, além de compartilhar o kernel ele isola cada um dos "kernels" utilizados pelos containers.

Outro conceito importante relativo a containers, está voltado ao compartilhamento de recursos computacionais. Para tanto, existe um outro conceito que se chama “Cgroups”, que vai garantir que consigamos definir tanto de maneira automática quando de maneira manual como os consumos serão feitos para cada um desses containers dentro do nosso sistema operacional.	

Graças aos namespaces e aos Cgroups nós conseguimos garantir isolamento, conseguimos garantir que nosso container funcione sem instalar um sistema operacional dentro dele, e também conseguiremos ter um controle de gerenciamento de recursos, como memória de CPU.

[Próximo => Instalação do Docker ](instalacao.md)