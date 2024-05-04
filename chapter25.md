# 第25章 必要なイメージを準備する

## 25.1 ディレクトリの作成

## 25.2 DBイメージを整理する

## 25.3 Mailイメージを整理する

## 25.4 Appイメージを準備する

#### コンテナで起動するコマンドの整理

- docker run --rm --publish 8000:8000 php:8.2.12 php --server 0.0.0.0:8000

#### Dockerfileの作成とイメージのビルド

- docker image build --tag work-app:0.1.0 docker/app

## 25.5 この章のまとめ

#### Appコンテナのパラメータの整理と起動確認

- docker container run --name app --rm --detach --publish 8000:8000 work-app:0.1.0 /usr/local/bin/php --server 0.0.0.0:8000 --docroot /

#### DBコンテナのパラメータの整理と起動確認

- docker container run --name db --rm --detach --env MYSQL_ROOT_PASSWORD=secret --env MYSQL_USER=app --env MYSQL_PASSWORD=pass1234 --env MYSQL_DATABASE=sample --env TZ=Asia/Tokyo --publish 3306:3306 mysql:8.2.0

- mysql --host=127.0.0.1 --port=3306 --user=app --password=pass1234 sample

#### Mailコンテナのパラメータの整理と起動確認

- docker container run --name mail --rm --detach --env TZ=Asia/Tokyo --publish 8025:8025 axllent/mailpit:v1.10.1
 