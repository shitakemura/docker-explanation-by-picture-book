# 第25章 必要なイメージを準備する

## 25.1 ディレクトリの作成

## 25.2 DBイメージを整理する

## 25.3 Mailイメージを整理する

## 25.4 Appイメージを準備する

#### コンテナで起動するコマンドの整理

- docker run --rm --publish 8000:8000 php:8.2.12 php --server 0.0.0.0:8000

#### Dockerfileの作成とイメージのビルド

- docker image build --tag work-app:0.1.0 docker/app
