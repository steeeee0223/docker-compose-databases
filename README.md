# Docker Compose with all Databases

### Containers

-   MySQL (with PhpMyAdmin)
-   PostgreSQL (with PGAdmin)
-   MongoDB (with Mongo-Express management)
-   Redis
-   RabbitMQ
-   Neo4j
-   Memcached (Currently not working)

### To create

-   Run the following command:

```shell
$ cd all-db
# 容器重新編譯後啟動
$ docker-compose up -d --build
# 容器停止 + 消除（containers + networks + images）
$ docker-compose down --rmi all
```

### To verify the databases in command line

1. `PostgreSQL`

```shell
% psql <db> <user>
db> \l   # shows the list of databases
```

2. `MySQL`

```shell
% mysql (-u <user>) -p <password>
mysql> SHOW databases; # shows the list of databases
mysql> use <db>;
```

3. `MongoDB`

```shell
% mongosh -u <user> -p <password>
test> use dev
```

4. `Redis`

```shell
% redis-cli
127.0.0.1:6379> PING
PONG
127.0.0.1:6379> SET foo "100"
OK
127.0.0.1:6379> GET foo
"100"
```

5. `RabbitMQ`

```shell
% rabbitmqctl list_users
Listing users ...
user	tags
steveyu	[administrator]
```

6. `Neo4j`

```shell
% cypher-shell -u neo4j -p neo4j123
neo4j@neo4j> MATCH (n) RETURN n LIMIT 5;
```

### To use GUI in the browser

| Database | url                      |
| -------- | ------------------------ |
| Postgres | `http://localhost:5050`  |
| MySQL    | `http://localhost:8080`  |
| MongoDB  | `http://localhost:8081`  |
| RabbitMQ | `http://localhost:15672` |
| Neo4j    | `http://localhost:7474`  |
