## twitter-sample-docker

```	
$ git clone git@github.com:narutyo/twitter-sample-docker.git
$ cd twitter-sample-docker
$ git submodule update --init --recursive
$ git submodule foreach git checkout master
$ cd submodules/ideabox-api && git checkout feature/IDEABOX_API_300 && cd ../../
$ cd submodules/twitter-frontend && npm install && cd ../../
$ docker-compose up -d --build

# コンテナが立ち上がってから...
$ docker-compose exec twitter-sample-api php composer.phar install
$ sudo find submodules/ideabox-api/storage -type d -exec chmod 777 {} +
$ sudo find submodules/ideabox-api/storage -type f -exec chmod 666 {} +

# ２回目以降は --build 無しでOKです
$ cd twitter-sample-docker
$ docker-compose up -d
```
