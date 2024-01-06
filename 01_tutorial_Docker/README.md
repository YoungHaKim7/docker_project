# 처음에 도커Docker ubuntu 이미지 만들기

- https://lucas-owner.tistory.com/61
- https://www.daleseo.com/docker-run/

```
$ docker run -i -t --name first-ubuntu ubuntu /bin/bash
```

- 만든 이미지 리스트 확인
- ```docker ps -a```

- 내가 만든 이미지 들어가기(일단 멈춘 이미지 돌려주고)
- ```docker start first-ubuntu```

- 내가 만든 이미지 들어가기
- ```docker exec -it first-ubuntu /bin/bash```

- 다 끝나고 내 도커 실행 중지 하기
- ```docker stop first-ubuntu```


```bash
 docker ps -a
CONTAINER ID   IMAGE     COMMAND       CREATED       STATUS                      PORTS     NAMES
35695dc6a08d   ubuntu    "/bin/bash"   2 hours ago   Exited (0) 18 minutes ago             first-ubuntu

$ docker run -it --name first-ubuntu /bin/bash
docker: invalid reference format.
See 'docker run --help'.

$ docker run -it --name first-ubuntu ubuntu /bin/bash
docker: Error response from daemon: Conflict. The container name "/first-ubuntu" is already in use by container "35695dc6a08d74e47f0463f920582e0c4a266f7ddb13c1f265d016f96640281c". You have to remove (or rename) that container to be able to reuse that name.
See 'docker run --help'.

$ docker start first-ubuntu
first-ubuntu

$ docker run -it --name first-ubuntu ubuntu /bin/bash
docker: Error response from daemon: Conflict. The container name "/first-ubuntu" is already in use by container "35695dc6a08d74e47f0463f920582e0c4a266f7ddb13c1f265d016f96640281c". You have to remove (or rename) that container to be able to reuse that name.
See 'docker run --help'.

$ docker run -it --name first-ubuntu /bin/bash
docker: invalid reference format.
See 'docker run --help'.

$ docker run -it first-ubuntu /bin/bash
Unable to find image 'first-ubuntu:latest' locally
docker: Error response from daemon: pull access denied for first-ubuntu, repository does not exist or may require 'docker login': denied: requested access to the resource is denied.
See 'docker run --help'.

$ docker exec -it first-ubuntu /bin/bash
root@35695dc6a08d:/# exit
exit

$ docker stop first-ubuntu
first-ubuntu
```

- https://mungiyo.tistory.com/4

# docker image 용량 체크

```
docker image ls
```

- https://gist.github.com/MichaelSimons/fb588539dcefd9b5fdf45ba04c302db6

<hr>


# Docker Containers and Kubernetes Fundamentals – Full Hands-On Course | freeCodeCamp.org

https://youtu.be/kTp5xUtcalw?si=dJS0wshYZPAfLmoK


# 가장 쉽게 배우는 도커 | 얄팍한 코딩사전

https://youtu.be/hWPv9LMlme8?si=-gdrfTFsJc1WRSbt

# Linux에서 Docker run설치해서 Ubuntu가상환경 설치하기

https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-22-04

# Dockerfile Tutorial | Dockerfile Tutorial With Example | Dockerfile Explained | Simplilearn

- https://youtu.be/tb4eDxdJscg?si=DZdZk42IRf55J1F6

```
Example of Docker

FROM ubuntu:18.04
PULL ./file
RUN make /file
CMD python /file/file.py
```

- FROM - Creates a layer from the ubuntu:18.04
- PULL - Adds files from your Docker repository
- RUN - BUilds your container


# doccker help

```bash
$ docker help

Usage:  docker [OPTIONS] COMMAND

A self-sufficient runtime for containers

Common Commands:
  run         Create and run a new container from an image
  exec        Execute a command in a running container
  ps          List containers
  build       Build an image from a Dockerfile
  pull        Download an image from a registry
  push        Upload an image to a registry
  images      List images
  login       Log in to a registry
  logout      Log out from a registry
  search      Search Docker Hub for images
  version     Show the Docker version information
  info        Display system-wide information

Management Commands:
  builder     Manage builds
  buildx*     Docker Buildx (Docker Inc., v0.11.2-desktop.5)
  checkpoint  Manage checkpoints
  compose*    Docker Compose (Docker Inc., v2.22.0-desktop.2)
  container   Manage containers
  context     Manage contexts
  dev*        Docker Dev Environments (Docker Inc., v0.1.0)
  extension*  Manages Docker extensions (Docker Inc., v0.2.20)
  image       Manage images
  init*       Creates Docker-related starter files for your project (Docker Inc., v0.1.0-beta.8)
  manifest    Manage Docker image manifests and manifest lists
  network     Manage networks
  plugin      Manage plugins
  sbom*       View the packaged-based Software Bill Of Materials (SBOM) for an image (Anchore Inc., 0.6.0)
  scan*       Docker Scan (Docker Inc., v0.26.0)
  scout*      Docker Scout (Docker Inc., v1.0.7)
  system      Manage Docker
  trust       Manage trust on Docker images
  volume      Manage volumes

Swarm Commands:
  config      Manage Swarm configs
  node        Manage Swarm nodes
  secret      Manage Swarm secrets
  service     Manage Swarm services
  stack       Manage Swarm stacks
  swarm       Manage Swarm

Commands:
  attach      Attach local standard input, output, and error streams to a running container
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  events      Get real time events from the server
  export      Export a container's filesystem as a tar archive
  history     Show the history of an image
  import      Import the contents from a tarball to create a filesystem image
  inspect     Return low-level information on Docker objects
  kill        Kill one or more running containers
  load        Load an image from a tar archive or STDIN
  logs        Fetch the logs of a container
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  rmi         Remove one or more images
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  wait        Block until one or more containers stop, then print their exit codes

Global Options:
      --config string      Location of client config files
                           (default
                           "/Users/globalyoung/.docker")
  -c, --context string     Name of the context to use to
                           connect to the daemon
                           (overrides DOCKER_HOST env var
                           and default context set with
                           "docker context use")
  -D, --debug              Enable debug mode
  -H, --host list          Daemon socket to connect to
  -l, --log-level string   Set the logging level ("debug",
                           "info", "warn", "error",
                           "fatal") (default "info")
      --tls                Use TLS; implied by --tlsverify
      --tlscacert string   Trust certs signed only by this
                           CA (default
                           "/Users/globalyoung/.docker/ca.pem")
      --tlscert string     Path to TLS certificate file
                           (default
                           "/Users/globalyoung/.docker/cert.pem")
      --tlskey string      Path to TLS key file (default
                           "/Users/globalyoung/.docker/key.pem")
      --tlsverify          Use TLS and verify the remote
  -v, --version            Print version information and quit

Run 'docker COMMAND --help' for more information on a command.

For more help on how to use Docker, head to https://docs.docker.com/go/guides/
```

# docker help cp

```bash
docker help cp

Usage:  docker cp [OPTIONS] CONTAINER:SRC_PATH DEST_PATH|-
	docker cp [OPTIONS] SRC_PATH|- CONTAINER:DEST_PATH

Copy files/folders between a container and the local filesystem

Use '-' as the source to read a tar archive from stdin
and extract it to a directory destination in a container.
Use '-' as the destination to stream a tar archive of a
container source to stdout.

Aliases:
  docker container cp, docker cp

Options:
  -a, --archive       Archive mode (copy all uid/gid
                      information)
  -L, --follow-link   Always follow symbol link in SRC_PATH
  -q, --quiet         Suppress progress output during
                      copy. Progress output is
                      automatically suppressed if no
                      terminal is attached
```
