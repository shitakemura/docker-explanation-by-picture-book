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
