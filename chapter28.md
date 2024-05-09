# 第28章 Docker Composeの利用

## 28.1 Docker Composeの基礎

## 28.2 dockerコマンドをcompose.yamlに移植する

## 28.3 Docker Composeの基本操作

#### コンテナの作成と起動 - compose up

- cd work
- docker compose up --detach --build

- http://localhost:8000
- http://localhost:8025

#### コンテナ一覧の確認 - compose ps

- docker container ls
- docker compose ps

#### 起動中のコンテナでコマンドを実行 - compose exec

- docker compose exec app bash

#### コンテナの停止と削除 - compose down

- docker compose down

- docker compose up --detach --build
- docker compose down --rmi all --volumes

