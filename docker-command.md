# docker-command
目次
- [docker-command](#docker-command)
  - [image](#image)
    - [build](#build)
  - [container](#container)
    - [run](#run)
    - [exec](#exec)
  - [compose](#compose)
    - [up](#up)

<a id=image></a>
## image

### build
Dockerfile から image を作成する。  
```shell
# docker image build --tag {docker-image-name} {dockerfile-PATH}

docker image build --tag test_image .
```

<a id=container></a>
## container

### run
image から container を作成する。  
```shell
# docker container run -d -it --name {docker-container-name} {docker-image-name}

docker container run -d -it --name test_container test_image
```

### exec
起動中の container に入る。  
```shell
docker container exec -it test_container /bin/bash
```

<a id=compose></a>
## compose

### up
docker image と container を作成する。
```shell
docker compose up -d
```