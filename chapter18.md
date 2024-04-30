# 第18章 タイムゾーンとログ出力が設定されたMySQLイメージを作る

## 18.1 イメージの環境変数を指定する ENV

#### MYSQLコンテナのタイムゾーンを確認する

- docker container run --name db --rm --detach --env MYSQL_ROOT_PASSWORD=secret --publish 3306:3306 mysql:8.2.0
- mysql --host=127.0.0.1 --port=3306 --user=root --password=secret

- select now();
- show variables like '%time_zone%';

- docker container exec db printenv TZ

#### ENV命令で環境変数を設定しタイムゾーンを変更する

- docker image build --file Dockerfile18.1 --tag my-mysql:tokyo .

- docker container run --name db --rm --detach --env MYSQL_ROOT_PASSWORD=secret --publish 3306:3306 my-mysql:tokyo
- mysql --host=127.0.0.1 --port=3306 --user=root --password=secret

- select now();
- show variables like '%time_zone%';

- docker container exec db printenv TZ

## 18.2 ホストマシンのファイルをイメージに追加する COPY

#### COPY命令で設定ファイルを設置しログ出力先を有効化する

- docker image build --file Dockerfile18.2 --tag my-mysql:log .

- docker container run --name db --rm --detach --env MYSQL_ROOT_PASSWORD=secret --publish 3306:3306 my-mysql:log
- mysql --host=127.0.0.1 --port=3306 --user=root --password=secret

- select now();
- exit;

- docker container exec db ls /var/log
- docker container exec db tail -n 5 /var/log/query.log
