# docker_project

# Docker Tutorial for Beginners

https://docker-curriculum.com/


https://docker-curriculum.com/#docker-images


- 버젼 확인
```
docker -v
```

- 설치 기초(MySQL 도커 컨테이너 생성 및 실행

https://docs.docker.com/engine/reference/run/

```
docker run [OPTIONS] IMAGE[:TAG|@DIGEST] [COMMAND] [ARG...]


```

- Downloading a MySQL Server Docker Image

https://hub.docker.com/r/mysql/mysql-server/

```
shell> docker pull mysql/mysql-server:tag
```

- Starting a MySQL Server Instance

```
shell> docker run --name=mysql1 -d mysql/mysql-server:tag
```


- After download completes, initialization for the container begins, and the container appears in the list of running containers when you run the ```docker ps``` command; for example:

```
shell> docker ps
CONTAINER ID   IMAGE                COMMAND                  CREATED             STATUS                              PORTS                NAMES
a24888f0d6f4   mysql/mysql-server   "/entrypoint.sh my..."   14 seconds ago      Up 13 seconds (health: starting)    3306/tcp, 33060/tcp  mysql1
```
