# 第11章 PostgresSQLサーバを起動していろいろ確認する

## 11.1 コンテナの出力を確認する container logs

#### バックグラウンドで起動したコンテナの出力を確認する

- docker container run --name db --detach --publish 5432:5432 postgres
- docker container logs db

- docker container rm db

- docker container run --name db --detach --env POSTGRES_PASSWORD=secret --publish 5432:5432 postgres
- docker container logs db

#### 増える出力をリアルタイムで確認する

- psql --host=127.0.0.1 --port=5432 --username=postgres
- select * from users;
- docker container logs db

- docker container logs --follow db

## 11.2 起動中のコンテナに命令する container exec

#### 起動中コンテナでコマンドを実行する

- docker container exec db head -n 4 /etc/os-release

#### 起動中コンテナでbashを実行する

- docker container exec --interactive --tty db bash
- cd /etc
- head -n 4 os-release

## 11.3 PostgreSQLサーバへの接続方法を整理する

- docker container exec --interactive --tty db psql --host=127.0.0.1 --port=5432 --username=postgres

- docker container exec --interactive --tty db bash
- psql --host=127.0.0.1 --port=5432 --username=postgres
