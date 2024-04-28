# 第14章 異なるバージョンのMySQLサーバを起動する

## 14.1 Docker Hubでイメージを探す

## 14.2 コンテナ起動時にイメージのタグを指定する

#### MySQL8.0.35コンテナを起動する

- docker container run --name db1 --rm --detach --env MYSQL_ROOT_PASSWORD=secret --publish 3306:3306 mysql:8.0.35
- mysql --host=127.0.0.1 --port=3306 --user=root --password=secret
- select version();

#### MySQL8.2.0コンテナを起動する

- docker container run --name db2 --rm --detach --env MYSQL_ROOT_PASSWORD=secret --publish 3307:3306 mysql:8.2.0
0
- mysql --host=127.0.0.1 --port=3307 --user=root --password=secret
- select version();
