# 第23章 PHPコンテナからMySQLコンテナに通信する

## 23.1 ネットワークの作成 network create

#### ネットワークの作成

- docker network create my-network

- docker network ls

#### PHPイメージにpingコマンドをインストールしておく

- docker image build --file Dockerfile23.1 --tag my-php:ping .

- docker container run my-php:ping ping -c 3 -t 1 localhost
