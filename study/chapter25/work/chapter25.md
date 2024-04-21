# Chapter25

## 25.1

## 25.2

## 25.3

## 25.4

docker run --rm --publish 8000:8000 php:8.2.12 php --server 0.0.0.0:8000

docker run --rm php:8.2.12 which php

docker image build --file docker/app/Dockerfile --tag work-app:0.1.0 docker/app

## 25.5

docker container run --name app --rm --detach --publish 8000:8000 work-app:0.1.0 /usr/local/bin/php --server 0.0.0.0:8000 --docroot /

docker container run --name db --rm --detach --env MYSQL_ROOT_PASSWORD=secret --env MYSQL_USER=app --env MYSQL_PASSWORD=pass1234 --env MYSQL_DATABASE=sample --env TZ=Asia/Tokyo --publish 3306:3306 mysql:8.2.0

mysql --host=127.0.0.1 --port=3306 --user=app --password=pass1234 sample

docker container run --name mail --rm --detach --env TZ=Asia/Tokyo --publish 8025:8025 axllent/mailpit:v1.10.1
