# docker_project
- A kernel manages applications and hardware resources.

# Docker Tutorial for Beginners

https://docker-curriculum.com/


https://docker-curriculum.com/#docker-images

- Tutorial
  - Docker Tutorial for Beginners
    - https://youtu.be/pTFZFxd4hOI

  - 생활코딩 https://www.youtube.com/watch?v=Ps8HDIAyPD0&list=PLuHgQVnccGMDeMJsGq2O-55Ymtx0IdKWf&index=1
    - https://opentutorials.org/course/4781

<hr>

<br>

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

# 명령어 정리

- Deploy https://github.com/docker/awesome-compose/tree/master/react-rust-postgres

- Deploy with docker compose

```
$ docker compose up -d
Creating network "react-rust-postgres_default" with the default driver
Building backend
...
Successfully tagged react-rust-postgres_frontend:latest
WARNING: Image for service frontend was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.
Creating react-rust-postgres_frontend_1 ... done
Creating react-rust-postgres_db_1       ... done
Creating react-rust-postgres_backend_1  ... done
```

- Expected result
  - Listing containers must show three containers running and the port mapping as below:

```
$ docker ps
CONTAINER ID        IMAGE                          COMMAND                  CREATED             STATUS              PORTS                    NAMES
30b7d9dc4898        react-rust-postgres_backend    "cargo run --offline"    37 seconds ago      Up 35 seconds       8000/tcp                 react-rust-postgres_backend_1
0bca0cb682b8        react-rust-postgres_frontend   "docker-entrypoint.s…"   42 seconds ago      Up 41 seconds       0.0.0.0:3000->3000/tcp   react-rust-postgres_frontend_1
1611961bf3d1        postgres:12-alpine             "docker-entrypoint.s…"   42 seconds ago      Up 36 seconds       0.0.0.0:5432->5432/tcp   react-rust-postgres_db_1
```

- After the application starts, navigate to http://localhost:3000 in your web browser to get a colorful message.

- Stop and remove the containers

```
$ docker compose down
Stopping react-rust-postgres_backend_1  ... done
Stopping react-rust-postgres_frontend_1 ... done
Stopping react-rust-postgres_db_1       ... done
Removing react-rust-postgres_backend_1  ... done
Removing react-rust-postgres_frontend_1 ... done
Removing react-rust-postgres_db_1       ... done
Removing network react-rust-postgres_default
```


