# Docker Tutorial for Beginners

https://docker-curriculum.com/


https://docker-curriculum.com/#docker-images

- Tutorial
  - Docker Tutorial for Beginners
    - https://youtu.be/pTFZFxd4hOI

  - 생활코딩 https://www.youtube.com/watch?v=Ps8HDIAyPD0&list=PLuHgQVnccGMDeMJsGq2O-55Ymtx0IdKWf&index=1
    - https://opentutorials.org/course/4781

  - Complete Docker Course - From BEGINNER to PRO! (Learn Containers)
    - https://youtu.be/RqTEHSBrYFw

<hr>

# Rust로 만든 docker & podman 관리
- https://github.com/reenigneEsrever92/contain-rs

<hr>

# docker_project
- A kernel manages applications and hardware resources.

<hr>


<hr>

# GN⁺: Kubernetes(쿠버네티스)를 싫어하는 이들을 위한 안내서 

https://news.hada.io/topic?id=13637&utm_source=discord&utm_medium=bot&utm_campaign=1480

- https://paulbutler.org/2024/the-haters-guide-to-kubernetes/

#  Docker 명령어 정리된 사이트

https://www.yalco.kr/36_docker/

<hr>

- MySQL 도커 컨테이너 생성 및 실행
```
docker run --name mysql-sample-container -e MYSQL_ROOT_PASSWORD=<password> -d -p 3306:3306 mysql:{version}
```

- 현재 실행중인 도커 컨테이너 목록 출력
```
docker ps -a
```

- 도커 실행된거 확인

```
sudo docker ps   
```

- 도커 실행된 이름으로 bash 진입하기

```
sudo docker exec -it 3f9fab bash
```

- postgrsql 진입
- ```
  psql -U postgres
  ```

- ```psql -U postgres```

```
root@3f9fab127ca1:/# psql -U postgres
psql (11.16 (Debian 11.16-1.pgdg90+1))
Type "help" for help.

postgres=# \l

```
- ```\l``` DB list 확인

https://browndwarf.tistory.com/51


-postgresql 여기에 명령어 정리
  -https://github.com/YoungHaKim7/postgresql_gy

<hr>


# linux에서 관리자 권한 없이 docker실행시키기
https://www.44bits.io/ko/post/easy-deploy-with-docker#:~:text=%EA%B4%80%EB%A6%AC%EC%9E%90%20%EA%B6%8C%ED%95%9C%EC%9D%B4%20%EC%9E%88%EB%8A%94%20%EA%B2%BD%EC%9A%B0,%EB%B6%99%EC%9D%B4%EB%A9%B4%20%EC%A0%95%EC%83%81%EC%A0%81%EC%9C%BC%EB%A1%9C%20%EC%8B%A4%ED%96%89%EB%90%A0%20%EA%B2%83%EC%9E%85%EB%8B%88%EB%8B%A4.&text=%EC%82%AC%EC%9A%A9%EC%9E%90%20%EA%B3%84%EC%A0%95%EC%97%90%EC%84%9C%EB%8F%84%20%EB%8F%84%EC%BB%A4%EB%A5%BC,%EA%B4%80%EB%A6%AC%EC%9E%90%20%EA%B6%8C%ED%95%9C%EC%9D%B4%20%ED%95%84%EC%9A%94%ED%95%A9%EB%8B%88%EB%8B%A4.&text=%EC%9D%B4%EC%A0%9C%20sudo%20%EB%AA%85%EB%A0%B9%EC%96%B4%20%EC%97%86%EC%9D%B4%EB%8F%84%20%EB%8F%84%EC%BB%A4%20%EB%AA%85%EB%A0%B9%EC%96%B4%EB%A5%BC%20%EB%B0%94%EB%A1%9C%20%EC%82%AC%EC%9A%A9%ED%95%A0%20%EC%88%98%20%EC%9E%88%EC%8A%B5%EB%8B%88%EB%8B%A4.


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

- 도커 이미지 삭제하기

```
// images list 쭉 보기
docker images

// 지우고자하는 id 적으로면 강제 삭제됨.
docker rmi fd484f19954f
```

https://docs.docker.com/engine/reference/commandline/rmi/

