# docker-command
目次
> [image](#image)  
  `Docker image`を作成するためのコマンド

> [container](#container)  
  `Docker container`を作成するためのコマンド

> [exec](#exec)  
  `Docker exec`を作成するためのコマンド


<a id=image></a>
## image
`Dockerfile`から`image`を作成する。  
```
# docker image build --tag {docker-image-name} {dockerfile-PATH}
docker image build --tag docker-test-image .
```

<a id=container></a>
## container
`image`から`container`を作成する。  
```
# docker container run -it --name {docker-container-name} {docker-image-name}
docker container run -it --name docker-test-container docker-test-image
```

<a id=exec></a>
## exec
起動中の`container`に入る。  
```
<a id=container></a>
## container
起動中の`container`に入る。  
```
docker container exec -it docker-test-container bash
```
