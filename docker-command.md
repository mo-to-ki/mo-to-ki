# docker-command
目次
> [docker](#image)


<a id=image></a>
## docker

`python`の`docker`を`pull`して起動するコマンド
```shell
docker container run --name python_container -it python:3.9-slim /bin/bash
```

これを分割して実行すると以下のようになる  

`docker`の`image`を`docker lab`から取得（今回は`python:3.9-slim`）
```shell
docker image pull python:3.9-slim
```

名前（今回は`python_container`）を指定して`container`の作成
```shell
docker create -it --name python_container /bin/bash
```

`container`の起動
```shell
docker start python_container
```
