# Estudo baseado no artigo do Medium - Renato Groffe
 - [SQL Server + Docker Compose: criando rapidamente ambientes e populando bases para testes](https://renatogroffe.medium.com/sql-server-docker-compose-criando-rapidamente-ambientes-e-populando-bases-para-testes-13d108d8cdb2)

## Comandos Docker

### Rodar via docker compose

```sh 
docker-compose up -d
```

### Rodar via docker compose com a recriação dos containers

```sh 
docker-compose up -d --build
```

### Acessar o bash do container
```sh
docker exec -it 35a6811e5677 "bash"
```

