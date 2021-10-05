# Docker

## Anotações

- **Dockerfile**: arquivo de texto que contém todas as instruções para fazer o build da imagem. Ex.: "instale o php"
- **Build**: ação que cria uma imagem a partir do dockerfile.
- **conteiner Image**: pacote com todas as dependencias para criação do conteiner.
- **conteiner**: é uma instância da imagem, representa a execução de uma aplicação/processo/serviço
- **Volumes**: permite que conteiner armazene arquivos e disco - informações persistem após morte do conteiner.
- **Tag**: ajuda no versionamento das imagens
- **Multi-stage build**: estágios multiplos de build
- **Repository**: Coleção de imagens
- **Registry**: serviço que provê o acesso do docker ao repositório
- **Docker Hub**: repositorio público onde ficam armazenadas as imagens docker
- **Compose**: ferramenta que utiliza uma metadata para criar multiplos conteiners com um comando

### Questões importantes

- **O que é Docker?**
  - É uma plataforma que serve para criar e gerenciar conteiners.
  - A arquitetura do docker é composta por:
    - Uma docker engine: é uma aplicação cliente-servidor.
       - O cliente==docker cli, que faz chamadas a uma API Rest que irá delegar esse processo ao docker daemon (é quem processa as requisições e conversa com o Kernel Linux)

- **O que são conteiners?**
  - Cada conteiner agrupa/encapsula uma aplicação junto com as dependências de modo a torná-la autosuficiente.
  - Com isso é possível rodar a aplicação independente do SO, contanto que a máquina tenha o Docker instalado.
  - Empacotamos aplicações em pequenos processos que trazem as dependências para as mesmas rodarem.
  - Ele usa recursos do próprio linux de onde ele está instalado
  - Criamos um conteiner a partir de uma imagem Docker. A imagem contém todos os binários para rodarmos o conteiner
  - Damos um build em um Dockerfile e ele irá gerar uma imagem. Ao darmos um run na imagem teremos o conteiner rodando. 

- **O que é uma máquina virtual?** 
  - Uma máquina virtual é um computador emulado em forma de software.

- **O que é um hypervisor?**
  - É uma camada de software que fica entre o hardware e as máquinas virtuais, em um datacenter por exemplo. 
  - É responsável por fornecer recursos como armazenamento, cpu, memória etc da máquina física para a virtual.
  - Permite que vários SOs sejam executados no mesmo host.
  - O Docker aproveita os recursos de maneira mais eficiente do que o hypervisor.
  - Há 2 tipos:
    - O que é instalado diretamente no hardware e não depende de um SO para se comunicar com o hardware. 
    - O que é instalado diretamente no hardware e depende de um SO para se comunicar com o hardware. Ex.: virtualbox

- **Qual a diferença entre uma máquina virtual e um conteiner?**
  - Com máquinas virtuais temos um SO, uma infraestrutura inteira.
  - Com conteiners temos apenas o que uma aplicação precisa para rodar de forma independente.

- **Como o Docker lida com a persistência de dados em um conteiner?**
  - Utilizamos volumes para esse fim.
  - Conteners nao foram feitos para armazenar estados/dados, quando o conteiner morre os dados morrem junto.
  - Volumes são mapeamentos do filesystem do conteiner para o filesystem "físico" (em um computador ou na nuvem por exemplo)


- **Como o Docker gerencia a rede entre os conteiners?**
  - Ao criarmos um conteiner se não especificarmos uma rede por default ele irá definir como bridge (isola os conteiners porém se estiver no mesmo host é possível realizar a comunicação entre esses conteiners).
  - Outro tipo de rede (driver de rede) é o overlay que comunica diferentes hosts.
  - Outros tipos de rede: host, none e mac

- **O que é Docker Compose?**
  - É um arquivo onde se define uma estrutura com vários conteiners para rodar de uma vez só.

- **O que são os EntryPoints em Docker?**
  - São uma entrada que colocamos no Dockefile para especificar um comando que será executado no momento em que o conteiner estiver pronto para ser executado.
  - O que for executado com o EntryPoint definirá o comportamento do conteiner.
  - Se o processo criado pelo EntryPoint parar o conteiner para.

- **O que são orquestradores?**
  - Ajudam na gerência dos conteiners. Podemos escalar os mesmos.

- Ao realizar um docker pull ou um docker run o docker verifica se temos a imagem localmente. Se nao tiver ele busca no dockerhub
- o Dockerhub é o registry default do docker.
- Podemos ter um registry diferente do dockerhub.
- Recomenda-se o uso de tags

- Cada configuração no dockerfile é uma nova camada no conteiner
- Criar instância: criar um servidor físico que tenha uma docker engine instalada

## Comandos

~~~shell
# comandos básicos
docker --help
docker version
docker info 
docker stats

# docker pull
docker pull hello-world # baixa do dockerhub a imagem hello-world para testarmos a instalação do docker
docker pull mysql # baixa do dockerhub img para mysql

# docker images
docker images # imagens usadas para criar os conteiners

# docker login
docker login # loga no dockerhub para fazer o push de uma imagem

# docker build
docker build -t rochamauricio/nomeImagemCriar . # apos logado, faz build a partir de dockerfile do diretorio atual
docker build -t nomeMinhaImagem:1.0 . # 1.0 == tag da imagem

# docker push
docker push rochamauricio/nomeImagemCriar # envia para o registry (dockerhub) a imagem criada

# docker run
## -d: rodar em background, -e: passar var de ambiente, -i: interatividade, -t: permite acesso ao terminal
## -v: passa nome/id volume, --rm: se conteiner ja existe sera removido para novo ser criado
## --name: nome conteiner. --mount: mesmo que -v
docker run -p 8080:8081 nomeMinhaImagem # gera conteiner com base na imagem
docker run -p 8080:8081 nomeMinhaImagem:1.0 # -p mapeia portas do conteiner, 1.0 == tag da imagem

docker run -d  --name mysql-vol -e MYSQL_ROOT_PASSWORD=root mysql
docker run -d --name mysql-vol -e MYSQL_ROOT_PASSWORD=root -v mysql-db:/tmp/aula-volume mysql # dir no conteiner
docker run -d --name mysql-vol -e MYSQL_ROOT_PASSWORD=root --mount source=mysql-db,destination=/tmp/teste mysql # outra forma mais descritiva com mount
docker run -d --name mysql-vol -e MYSQL_ROOT_PASSWORD=root --mount source=mysql-db,destination=/tmp/teste,readonly mysql # outra forma mais descritiva com mount, usando readonly para conteiner só poder ler o volume


docker run -d -e MYSQL_ROOT_PASSWORD=root mysql # gera conteiner de imagem mysql
docker run -it --entrypoint /bin/ls mysql # lista dir do workdir e para conteiner pois ls para
docker run -it --entrypoint /bin/bash mysql # cria terminal e segue rodando o mysql

# docker ps
docker ps # exibe conteiners em execução
docker ps -a # exibe conteiners rodando E parados
docker ps -q # exibe somente id dos conteiners
docker ps -aq # ids de conteiners rodando e parados

# docker stop
docker stop nomeconteiner # para o conteiner (aceita idConteiner)
docker stop nomecont1 nomecont2 # para os conteiners (aceita idConteiner)   
docker stop $(docker ps -q) # para todos os conteiners

# docker start
docker start nomeconteiner # inicializa o conteiner (aceita idConteiner)
docker start nomecont1 nomecont2 # inicializa os conteiners (aceita idConteiner)
docker start $(docker ps -qa) # inicializa todos os conteiners

# docker rm
docker rm nomeconteiner # remove conteiner (aceita idConteiner)
docker rm nomecont1 nomecont2 # remove lista conteiners (aceita idConteiner)
docker rm -f nomeConteiner # força remoção de conteiner em execução ou não (aceita idConteiner)
docker rm -f $(docker ps -qa) # forma remoção de todos conteiners em execução ou não 

# docker rmi
docker rmi nomeImg # remove imagem
docker rmi -f nomeImg # força remoção

# docker inspect
docker inspect nomeConteiner # em mounts pode-se ver o dir do volume criado pelo conteiner, destination: local no conteiner para onde sera mapeado o volume

# docker volume 
## dir dos volumes: /var/lib/docker/volumes
docker volume create nomeVolume
docker volume inspect
docker volume prune # remove nao utilizados
docker volume rm nomeVolume
docker volume ls # lista volumes

# docker exec
## executa comando em conteiner que ja esta em execução
docker exec -it mysql-vol /bin/bash # acessa o terminal do conteiner

# docker commit 
docker commit --author="Mauricio Rocha" --message="Imagem com commit" nomeconteiner nomeImagem 

# docker logs e inspect
docker logs nomeConteiner # logs do conteiner
docker inspect nomeConteiner # configuracoes usadas no conteiner

docker tag # versionar, link simbolico da img
docker logout
docker search
docker export # exporta conteiner
docker import # importa conteiner
docker save
docker load
~~~

## Dockerfile

- É um arquivo/script que dita como o conteiner irá se comportar após rodarmos uma imagem.
- Após o Dockerfile estar pronto damos o build para gerar a imagem, que pode ser colocada em um repositório.
- Ao darmos um docker run geramos um conteiner a partir da imagem.

- Cada comando cria uma camada na imagem. Quanto mais comandos mais camadas.

- O nome do arquivo deve ser: Dockerfile sem extensão
- FROM, pega imagem base - deve estar na primeira linha 
- COPY: busca no dir do Dockerfile um arquivo e copia dentro do conteiner que será criado ao rodarmos a imagem
- ADD: mesmo que copy porem pode pegar tambem de uma URL o arquivo, descompactar um .tar
- RUN: executa um comando no conteiner
- CMD: executa algo quando o conteiner for inicializado, aceita array OU funciona como parametro para o ENTRYPOINT
- WORKDIR: define dir raiz do conteiner
- ENV: cria var de ambiente, pode ser referenciada dentro do conteiner. Podemos usar a var de amb dentro do próprio Dockerfile
- EXPOSE: expoe uma porta dentro do conteiner quando o mesmo for iniciado, permite acessarmos a porta de fora do conteiner

~~~Dockerfile
# Um exemplo da aplicação da lista de comandos em um arquivo Dockerfile
FROM openjdk 

COPY aula.txt /app/aula.txt

ADD aula.tar.gz /app/aula/

RUN mkdir /aula

CMD ["/app"]

ENTRYPOINT ["ls"]

WORKDIR /app

ENV MINHA_APLICACAO=app.jar

COPY $MINHA_APLICACAO /app

EXPOSE 8080



# exemplo 2: em outro arquivo Dockerfile!
## obs.: é uma aplicacao java e temos um produto.jar no mesmo dir do Dockerfile
## ele usa a porta 8081 por fins didáticos
FROM openjdk

RUN mkdir -p /app/aula

ENV APP_NAME=produto.jar

COPY ${APP_NAME} /app/aula/

EXPOSE 8081

ENTRYPOINT [ "java", "-jar", "/app/aula/", "produtos.jar" ]

### depois, no terminal voce deve no mesmo dir do Dockerfile:
  # docker build -t nomeMinhaImagem:1.0 . # 1.0 == tag da imagem
  # docker images
  # docker run -p 8080:8081 nomeMinhaImagem:1.0 # -p mapeia portas do conteiner
  
~~~

## Exemplos

~~~shell
# Exemplo basico
docker pull hello-world 
docker images 
docker run hello-world


################################

# Exemplo volumes
## lista conteiners e volumes
docker ps -a
docker volume ls

# cria volume
docker volume create mysql-db # cria volume
docker volume ls # mostra volumes
sudo ls /var/lib/docker/volumes # mostra dir no host que contem o volume

# cria conteiner e acessa seu terminal
docker run -d --name mysql-vol -e MYSQL_ROOT_PASSWORD=root -v mysql-db:/tmp/aula-volume mysql # gera conteiner mysql-vol
docker inspect mysql-vol # em mounts name teremos o nome do volume criado
docker exec -it mysql-vol /bin/bash # acessa o terminal do conteiner

# no terminal do conteiner
cd tmp/aula-volume
echo "Testando volumes" >> teste.txt
exit # sai do terminal do conteiner

sudo ls /var/lib/docker/volumes/mysql-db/_data # o arquivo criado estará aqui
sudo cat /var/lib/docker/volumes/mysql-db/_data

# removendo o conteiner e o volume 
docker rm -f mysql-vol
docker volume prune


################################

# Exemplo mysql em conteiner

# baixa imagem do mysql
docker pull mysql:5.7 # baixa v5.7 da img, se imagem nao existir na maquina ira baixar do dockerhub

# rodando
## -p porta do host:porta conteiner, com isso podemos criar conexão local como se mysql estivesse instalado na nossa maquina
## /var/lib/mysql é o local padrão no conteiner para inserir bds mysql
docker run -d -e MYSQL_ROOT_PASSWORD=root --name meu-mysql -p 3306:3306 -v mysql-volume:/var/lib/mysql mysql:5.7 

# descobrindo ip do conteiner
docker inspect meu-mysql | grep IPAddress

# acessar o servidor
## é possível, com esse ip, se conectar com esse servidor mysql que está no conteiner
## acessaremos esse ip na porta 3306

# acessando o terminal do conteiner
docker exec -it meu-mysql /bin/bash

# no terminal do conteiner - acessar o mysql
mysql -u root -p # forneça a senha criada no docker run na var de ambiente MYSQL_ROOT_PASSWORD

# no mysql
show databases;

create database bancoteste1;

use bancoteste1;

create table if not exists fruit (
  fruit_id int(10) unsigned not null auto_increment,
  name varchar(50) not null,
  variety varchar(50) not null,
  primary key (fruit_id)
);

insert into fruit (fruit_id, name, variety) values
(1, 'Apple', 'Red Delicious'),
(2, 'Pear', 'Comice'),
(3, 'Orange', 'Nvel');

select * from fruit; # exibe os dados

exit # sai do prompt do mysql

exit # sai do terminal do conteiner

# removendo o conteiner
## ao sair do conteiner os dados irão persistir em disco!!!
docker rm -f meu-mysql

# o volume existe, veja as tabelas criadas:
sudo ls /var/lib/docker/volumes/mysql-volume/_data/bancoteste1

# subindo um novo conteiner
docker run -d -e MYSQL_ROOT_PASSWORD=root --name meu-mysql -p 3306:3306 -v mysql-volume:/var/lib/mysql mysql:5.7 

docker exec -it meu-mysql /bin/bash
mysql -u root
show databases; # vai mostrar o bd criado, comprovando a persistencia de dados

# removendo o conteiner e o volume 
docker rm -f meu-mysql
docker volume prune
~~~

## Links

- [Documentação Oficial](https://docs.docker.com/get-started/)
- [Docker oficial - post install](https://docs.docker.com/engine/install/linux-postinstall/)
- [Play with Docker](https://labs.play-with-docker.com/)

- [AlgaWorks - playlist youtube](https://www.youtube.com/playlist?list=PLZTjHbp2Y78013IcGa-vCAcqQUwGt_MW6)
- [Programador a bordo - 22min youtube](https://www.youtube.com/watch?v=Kzcz-EVKBEQ)

## Continua

- Ler https://flexa.cloud/o-que-e-docker-hub/

DOCKERFILE
https://www.youtube.com/playlist?list=PLZTjHbp2Y78013IcGa-vCAcqQUwGt_MW6