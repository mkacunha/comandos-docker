# Comandos Docker

### Comandos relacionados à informações

`docker version`   exibe a versão do docker que está instalada.  
`docker inspect ID_CONTAINER`    retorna diversas informações sobre o container.  
`docker ps`   exibe todos os containers em execução no momento.  
`docker ps -a`   exibe todos os containers, independente de estarem em execução ou não.  

### Comandos relacionados à execução

`docker run NOME_DA_IMAGEM`   cria um container com a respectiva imagem passada como parâmetro.  
`docker run -it NOME_DA_IMAGEM`   conecta o terminal que estamos utilizando com o do container.  
`docker run -d -P --name NOME dockersamples/static-site`   ao executar, dá um nome ao container.  
`docker run -d -p 12345:80 dockersamples/static-site`   define uma porta específica para ser atribuída à porta 80 do container, neste caso 12345.  
`docker run -v "CAMINHO_VOLUME" NOME_DA_IMAGEM`   cria um volume no respectivo caminho do container.  
`docker run -it --name NOME_CONTAINER --network NOME_DA_REDE NOME_IMAGEM`   cria um container especificando seu nome e qual rede deverá ser usada.  

*O parâmetro `-d` utilizado juntamente com `run` significa que irá rodar em background e não vai travar o terminal até que o container morra.*  

### Comandos relacionados à inicialização/interrupção

`docker start ID_CONTAINER`   inicia o container com id em questão.  
`docker start -a -i ID_CONTAINER`   inicia o container com id em questão e integra os terminais, além de permitir interação entre ambos.  
`docker stop ID_CONTAINER`   interrompe o container com id em questão.  


### Comandos relacionados à remoção

`docker rm ID_CONTAINER`   remove o container com id em questão.  
`docker container prune`   remove todos os containers que estão parados.  
`docker rmi NOME_DA_IMAGEM`   remove a imagem passada como parâmetro.  

### Comandos relacionados à construção de Dockerfile

`docker build -f Dockerfile`   cria uma imagem a partir de um Dockerfile.  
`docker build -f Dockerfile -t NOME_USUARIO/NOME_IMAGEM`   constrói e nomeia uma imagem não-oficial.  
`docker build -f Dockerfile -t NOME_USUARIO/NOME_IMAGEM CAMINHO_DOCKERFILE`   constrói e nomeia uma imagem não-oficial informando o caminho para o Dockerfile.  

### Comandos relacionados ao Docker Hub

`docker login`   inicia o processo de login no Docker Hub.  
`docker push NOME_USUARIO/NOME_IMAGEM`   envia a imagem criada para o Docker Hub.  
`docker pull NOME_USUARIO/NOME_IMAGEM`   baixa a imagem desejada do Docker Hub.  


### Comandos relacionados à rede

`hostname -i`   mostra o ip atribuído ao container pelo docker (funciona apenas dentro do container).  
`docker network create --driver bridge NOME_DA_REDE`   cria uma rede especificando o driver desejado

### Comandos relacionados à docker-compose

`docker-compose build -d`   Cria as imagens de acordo com o arquivo docker-compose.yaml  
`docker-compose up -d`   Cria os serviços configurados no docker-compose.yaml  
`docker-compose ps`   Mostras os serviços que estão rodando  
`docker-compose down`   Para todos os serviços e removem os containers  
`docker-compose restart` Reinicia os containers, é como se tivesse executado os comandos `docker-compose down` e `docker-compose up`  

