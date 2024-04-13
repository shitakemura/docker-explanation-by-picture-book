# Chapter14

## 14.2

docker container run --name db1 --rm --detach --env MYSQL_ROOT_PASSWORD=secret --publish 3306:3306 mysql:8.0.35

mysql --host=127.0.0.1 --port=3306 --user=root --password=secret

select version();

exit;

docker container run --name db2 --rm --detach --env MYSQL_ROOT_PASSWORD=secret --publish 3307:3307 mysql:8.2.0

mysql --host=127.0.0.1 --port=3307 --user=root --password=secret

select version();

exit;

docker container stop db1

docker container stop db2
