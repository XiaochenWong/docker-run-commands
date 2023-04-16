#### Rabbit MQ

```shell
docker run -dit --restart=unless-stopped --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3-management
```

#### Emq X

```shell
docker run -dit --restart=unless-stopped --name emqx -p 1883:1883 -p 8081:8081 -p 8083:8083 -p 8883:8883 -p 8084:8084 -p 18083:18083 emqx/emqx:v4.0.0
```

#### HiveMQ

```bash
docker run -dit --restart=unless-stopped --name hivemq-ce -p 1883:1883 -v /home/shawn/docker-volumes/hivemq-ce:/mnt  hivemq/hivemq-ce
```

#### Redis

```shell 
docker run --name redis -dit -p 6379:6379 --restart=unless-stopped redis
```

#### Redis-alt
```shell
docker run -dit --name redis --restart=unless-stopped -p 6379:6379 -v /docker-volumes/redis:/usr/local/etc/redis  redis redis-server /usr/local/etc/redis/redis.conf
```

#### Timescaledb

```shell
docker run --restart=unless-stopped -dit --name  timescaledb -p 5432:5432 -v /root:/root -e POSTGRES_PASSWORD=password timescale/timescaledb:2.1.1-pg13
```

#### Springboot

```shell
docker run -dit  --restart=unless-stopped -p 8080:8080 -v /root/docker-volumes/gateway:/opt   --name searice-gateway  docker.io/openjdk:11  java -jar -Duser.timezone=GMT+8 -Dspring.profiles.active=prod  -Dspring.config.location=/opt/application-prod.yml /opt/gateway-0.0.1-SNAPSHOT.jar

```

#### Vertx

```shell
docker run -dit  --restart=unless-stopped -p 8080:8080 -v /root/docker-volumes/milkywayroot:/root   --name milkyway  docker.io/openjdk:11  java -jar -Duser.timezone=GMT+8 /root/milkyway-1.0.0-SNAPSHOT-fat.jar
```

#### Consul

```bash
docker run \
    -dit \
    --restart=unless-stopped \
    -p 8500:8500 \
    -p 8600:8600/udp \
    --name=consul \
    consul agent -server -ui -node=server-1 -bootstrap-expect=1 -client=0.0.0.0
```



#### Mysql

```bash
docker run -d -p 3306:3306 --restart='unless-stopped' --privileged=true  -e MYSQL_ROOT_PASSWORD=password --name mysql mysql:5.7 --character-set-server=utf8mb4 --collation-server=utf8mb4_general_ci
```

#### FTP

```bash
docker run -dit -p 21:21 --restart='unless-stopped' --name proftpd   -e PASV_ADDRESS=192.168.124.10 instantlinux/proftpd -e MAX_CLIENTS=100000
```

建完了以后要进去修改配置文件




