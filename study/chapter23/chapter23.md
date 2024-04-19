# Chapter23

## 23.1

docker network create my-network

docker network ls

docker image build --file ./Dockerfile23 --tag my-php:ping .

docker container run my-php:ping ping -c 3 -t 1 localhost

## 23.2

docker container run --name db --rm --detach --env MYSQL_ROOT_PASSWORD=secret --env MYSQL_DATABASE=sample --publish 3306:3306 --network my-network mysql:8.2.0

mysql --host=127.0.0.1 --port=3306 --user=root --password=secret sample

create table user ( id int, name varchar(32) );

insert into user ( id, name ) values ( 1, 'John Doe' );

insert into user ( id, name ) values ( 2, 'Jane Doe' );

select * from user;

docker container run --network my-network my-php:ping ping -c 3 -t 1 db

docker image build --file ./Dockerfile23 --tag my-php:pdo_mysql .

---

docker container run --rm --mount type=bind,source="$(pwd)",target=/my-work --network my-network my-php:pdo_mysql php /my-work/main.php

