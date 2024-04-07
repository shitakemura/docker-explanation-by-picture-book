# Chapter11

## 11.1

docker container run --name db --detach --publish 5432:5432 postgres

docker container logs db

docker container rm db

docker container run --name db --detach --env POSTGRES_PASSWORD=secret --publish 5432:5432 postgres

docker container logs db

psql --host=127.0.0.1 --port=5432 --username=postgres

docker container logs --follow db

## 11.2

docker container exec db head -n 4 /etc/os-release

docker container exec --interactive --tty db bash

# 11.3

docker container exec --interactive --tty db psql --host=127.0.0.1 --port=5432 --username=postgres

docker container exec -it db bash

psql --host 127.0.0.1 --port=5432 --username-postgres
