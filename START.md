
# Pré-requisitos

- Docker installed - https://docs.docker.com/v17.12/install


# Build image zookeeper
```
docker build -t flinox/zookeeper ./zookeeper/.
```

# Executar um container individualmente
```
export ID=1
docker run --rm \
--name zookeeper${ID} --hostname zookeeper${ID} \
--network bridge \
-u zookeeper -e ID=${ID} \
-v $(pwd)/zookeeper/data/zookeeper${ID}/:/data/zookeeper \
-v $(pwd)/zookeeper/log/zookeeper${ID}/:/opt/zookeeper/log \
-v $(pwd)/zookeeper/conf/:/opt/zookeeper/conf \
flinox/zookeeper
```

- Informe o ID para identificacao unica do nó do cluster
