# 第7章 Rubyコンテナでインライン実行をする

## 7.1　コンテナ起動時に任意の処理を実行する container run [command]

#### コンテナ起動時のコマンドはイメージによって決まっている

- ubuntuコンテナはbashが実行されるため、以下は同じ
    - docker run -it ubuntu bash
    - docker run -it ubuntu

- docker container run ubuntu whoami

- docker container run ubuntu head -n 4 /etc/os-release

#### Rubyコンテナでインライン実行をする

- docker container run ruby ruby -e 'print 40 + 2'

## 7.2 コンテナに名前をつける container run --name

#### コンテナの名前を自分で決める

- docker container run --name hello hello-world
- docker container ls --all
- docker container rm hello

## 7.3 コンテナ停止時に自動で削除する container run --rm

#### コンテナの名前重複と修了済コンテナの自動削除

- docker container run --name hello2 --rm hello-world
- docker container ls --all
