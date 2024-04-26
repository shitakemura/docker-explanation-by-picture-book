# 第10章 MySQLサーバをバックグラウンドで起動する

## 10.1 コンテナの環境変数を設定する container run --env

#### MySQLサーバを起動する

- docker container run --name db --rm --env MYSQL_ROOT_PASSWORD=secret --publish 3306:3306 mysql

#### MySQLサーバに接続する

- mysql --host=127.0.0.1 --port=3306 --user=root --password=secret
- select version();

- docker container stop db

#### MySQLサーバを起動しユーザとデータベースを作成する

- docker container run --name db --rm --env MYSQL_ROOT_PASSWORD=secret --env MYSQL_USER=app --env MYSQL_PASSWORD=pass1234 --env MYSQL_DATABASE=sample --publish 3306:3306 mysql

- mysql --host=127.0.0.1 --port=3306 --user=app --password=pass1234 sample
- select current_user();

- docker container stop db

## 10.2 コンテナをバックグラウンドで実行する container run --detach

#### コンテナを起動するたびにターミナルを切り替えたくない

- docker container run --name db --rm --detach --env MYSQL_ROOT_PASSWORD=secret --env MYSQL_USER=app --env MYSQL_PASSWORD=pass1234 --env MYSQL_DATABASE=sample --publish 3306:3306 mysql

- docker container ls
- docker container stop db
