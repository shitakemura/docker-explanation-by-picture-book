# MySQLコンテナのデータが消えないようにする

## 21.1 ボリュームの作成 volume create

#### ボリュームの作成

- docker volume create --name my-volume
- docker volume ls

## 21.2 コンテナ起動時にボリュームをマウントする container run --mount

#### 作成したボリュームをUbuntuコンテナにマウントする

- docker container run --name ubuntu1 --rm --interactive --tty --mount type=volume,source=my-volume,destination=/my-work ubuntu:22.04

- ls
- ls /my-work

- echo 'hello from container.' > /my-work/hello.txt
- cat /my-work/hello.txt

- docker container stop ubuntu1

- docker container run --name ubuntu2 --rm --interactive --tty --mount type=volume,source=my-volume,destination=/my-work ubuntu:22.04

- ls /my-work
- cat /my-work/hello.txt

- docker container stop ubuntu2
- docker volume rm my-volume

#### 新たなボリュームを作成しMySQLコンテナにマウントする

- docker volume create --name db-volume

- docker container run --name db1 --rm --detach --env MYSQL_ROOT_PASSWORD=secret --env MYSQL_DATABASE=sample --publish 3306:3306 --mount type=volume,source=db-volume,destination=/var/lib/mysql mysql:8.2.0

- mysql --host=127.0.0.1 --port=3306 --user=root --password=secret sample

- create table user ( id int, name varchar(32) );
- insert into user ( id, name ) values ( 1, 'John Doe' );
- insert into user ( id, name ) values ( 2, 'Jane Doe' );
- select * from user;
- exit

- docker container stop db1

- docker container run --name db2 --rm --detach --publish 3306:3306 --mount type=volume,source=db-volume,destination=/var/lib/mysql mysql:8.2.0

- mysql --host=127.0.0.1 --port=3306 --user=root --password=secret sample
- select * from user;
- exit
- docker container stop db2
