# Projeto Edilson #
## Preparação da Infraestrutura #

### Instalando o docker no Debian ###
```
su
apt install docker
```

### Configurando o container do Mysql ###
```
docker run --name mongo-db -d mongo
docker start mongo-db
```

### Configurando o container do Elastic Search ###
```
docker network create my-network
docker run -d --name elasticsearch --net my-network -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" elasticsearch:8.5.3
docker start elasticsearch
```

### Configurando o container do Redis ###
```
docker run --name redis -d -p 6379:6379 redis:latest
docker start redis
```
### Configurando o container do MongoDB ###
```
docker run --name mongo-db -d mongo
docker start mongo-db
```


### Acesso ao Servidor via linux SSH ###
```
ssh edilson@192.168.15.10 -p 22
```
## Tarefas a resolver ##
###### Lista de tarefas: ###### 
- [ ] Persistir os dados nos containners (Está apresentando erro de permissão de gravação na criação do repositório)
- [ ] Instalar tela de acesso no Redis
