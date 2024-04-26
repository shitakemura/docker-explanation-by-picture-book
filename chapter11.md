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
