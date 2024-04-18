## 18.1

docker container run --name db --rm --detach --env MYSQL_ROOT_PASSWORD=secret --publish 3306:3306 mysql:8.2.0

mysql --host=127.0.0.1 --port=3306 --user=root --password=secret

select now();

show variables like '%time_zone%';

docker container exec db printenv TZ

docker image build --tag my-sql:tokyo ./study/chapter18

docker container run --name db --rm --detach --env MYSQL_ROOT_PASSWORD=secret --publish 3306:3306 my-sql:tokyo

mysql --host=127.0.0.1 --port=3306 --user=root --password=secret

select now();

show variables like '%time_zone%';

docker container exec db printenv TZ