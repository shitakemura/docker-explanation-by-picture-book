# 第27章 コンテナの起動

## 27.1 App、DB、Mailコンテナの起動

#### Appコンテナの起動

- docker container run --name app --rm --detach --publish 8000:8000 --mount type=bind,source="$(pwd)"/src,target=/my-work --network work-network work-app:0.1.0 /usr/local/bin/php --server 0.0.0.0:8000 --docroot /my-work

#### DBコンテナの起動

- docker container run --name db --rm --detach --env MYSQL_ROOT_PASSWORD=secret --env MYSQL_USER=app --env MYSQL_PASSWORD=pass1234 --env MYSQL_DATABASE=sample --env TZ=Asia/Tokyo --publish 3306:3306 --mount type=volume,source=work-db-volume,target=/var/lib/mysql --mount type=bind,source="$(pwd)"/docker/db/init,target=/docker-entrypoint-initdb.d --network work-network mysql:8.2.0

#### Mailコンテナの起動

- docker container run --name mail --rm --detach --env TZ=Asia/Tokyo --env MP_DATA_FILE=/data/mailpit.db --publish 8025:8025 --mount type=volume,source=work-mail-volume,target=/data --network work-network axllent/mailpit:v1.10.1

## 27.2 ブラウザを確認

- http://localhost:8000
- http://localhost:8025

- docker container stop app db mail
