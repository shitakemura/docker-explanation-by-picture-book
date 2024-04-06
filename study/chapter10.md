# Chapter10

## 10.1

docker container run --name db --rm mysql

docker container run --name db --rm --env MYSQL_ROOT_PASSWORD=secret --publish 3307:3306 mysql

mysql --host=127.0.0.1 --port=3307 --user=root --password=secret

select version();

docker container stop db

docker container run --name db --rm --env MYSQL_ROOT_PASSWORD=secret --env MYSQL_USER=app --env MYSQL_PASSWORD=pass1234 --env MYSQL_DATABASE=sample --publish 3307:3306 mysql

mysql --host=127.0.0.1 --port=3307 --user=app --password=pass1234 sample

select current_user();

docker container stop db

## 10.2

docker container run --name db --rm --detach --env MYSQL_ROOT_PASSWORD=secret --env MYSQL_USER=app --env MYSQL_PASSWORD=pass1234 --env MYSQL_DATABASE=sample --publish 3307:3306 mysql

docker container stop db
