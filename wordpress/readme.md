# Estudo baseado no vídeo do canal - Fabrício Veronez DevOps Pro
 - [Como usar corretamente o Docker Compose](https://youtu.be/hue967OT4gw)

## Comandos Docker

### Criar network
```sh 
docker network create wordpress_net
```

### Criar container de banco de dados
```sh 
docker container run --name wp-db -e MYSQL_ROOT_PASSWORD=rootpwd -e MYSQL_DATABASE=wordpress -e MYSQL_USER=wordpress -e MYSQL_PASSWORD=wordpress --network=wordpress_net -d mysql:8.0.30
```

### Criar container do wordpress
```sh 
docker container run --name wp-web -e WORDPRESS_DB_HOST=wp-db -e WORDPRESS_DB_USER=wordpress -e WORDPRESS_DB_NAME=wordpress -e WORDPRESS_DB_PASSWORD=wordpress --network=wordpress_net -p 8080:80 -d wordpress
```

### Criar container do phpmyadmin
```sh 
docker container run --name wp-phpmyadmin -e PMA_HOST=wp-db -e PMA_PORT=3306 -e PMA_USER=wordpress -e PMA_PASSWORD=wordpress --network=wordpress_net -p 8181:80 -d phpmyadmin
```

### Rodar via docker compose

```sh 
docker-compose up -d
```

### Rodar via docker compose com a recriação dos containers

```sh 
docker-compose up -d --build
```

### Rodar via docker compose com variáveis de ambiente

```sh 
docker-compose --env-file .env up -d
```

### Logs do docker compose

```sh 
docker-compose logs
```

### Lsta docker compose

```sh 
docker-compose ps
```

