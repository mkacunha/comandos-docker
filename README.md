# Comandos Docker

## Lista com os principais comandos Docker:

### Comandos relacionados à informações

__docker version:__ exibe a versão do docker que está instalada.  
__docker inspect ID_CONTAINER:__  retorna diversas informações sobre o container.  
__docker ps:__ exibe todos os containers em execução no momento.  
__docker ps -a:__ exibe todos os containers, independente de estarem em execução ou não.  

### Comandos relacionados à execução

__docker run NOME_DA_IMAGEM:__ cria um container com a respectiva imagem passada como parâmetro.  
__docker run -it NOME_DA_IMAGEM:__ conecta o terminal que estamos utilizando com o do container.  
__docker run -d -P --name NOME dockersamples/static-site:__ ao executar, dá um nome ao container.  
__docker run -d -p 12345:80 dockersamples/static-site:__ define uma porta específica para ser atribuída à porta 80 do container, neste caso 12345.  
__docker run -v "CAMINHO_VOLUME" NOME_DA_IMAGEM:__ cria um volume no respectivo caminho do container.  
__docker run -it --name NOME_CONTAINER --network NOME_DA_REDE NOME_IMAGEM:__ cria um container especificando seu nome e qual rede deverá ser usada.  

*O parâmetro __-d__ utilizado juntamente com __run__ significa que irá rodar em background e não vai travar o terminal até que o container morra.*  

### Comandos relacionados à inicialização/interrupção

__docker start ID_CONTAINER:__ inicia o container com id em questão.  
__docker start -a -i ID_CONTAINER:__ inicia o container com id em questão e integra os terminais, além de permitir interação entre ambos.  
__docker stop ID_CONTAINER:__ interrompe o container com id em questão.  


### Comandos relacionados à remoção

__docker rm ID_CONTAINER:__ remove o container com id em questão.  
__docker container prune:__ remove todos os containers que estão parados.  
__docker rmi NOME_DA_IMAGEM:__ remove a imagem passada como parâmetro.  

### Comandos relacionados à construção de Dockerfile

__docker build -f Dockerfile:__ cria uma imagem a partir de um Dockerfile.  
__docker build -f Dockerfile -t NOME_USUARIO/NOME_IMAGEM:__ constrói e nomeia uma imagem não-oficial.  
__docker build -f Dockerfile -t NOME_USUARIO/NOME_IMAGEM CAMINHO_DOCKERFILE:__ constrói e nomeia uma imagem não-oficial informando o caminho para o Dockerfile.  

### Comandos relacionados ao Docker Hub

__docker login:__ inicia o processo de login no Docker Hub.  
__docker push NOME_USUARIO/NOME_IMAGEM:__ envia a imagem criada para o Docker Hub.  
__docker pull NOME_USUARIO/NOME_IMAGEM:__ baixa a imagem desejada do Docker Hub.  


### Comandos relacionados à rede

__hostname -i:__ mostra o ip atribuído ao container pelo docker (funciona apenas dentro do container).  
__docker network create --driver bridge NOME_DA_REDE:__ cria uma rede especificando o driver desejado.  
