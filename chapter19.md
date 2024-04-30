# 第19章 起動時にウェブサーバが起動するPythonイメージを作る

## コンテナ起動時のコマンドを指定する CMD

#### PythonコンテナをWebサーバにする

- docker container run --name web --rm --detach --publish 8000:8000 python:3.12.0 python3 -m http.server

#### CMD命令でPythonコンテナをWebサーバにする

- docker container run python:3.12.0 which python3

- docker image build --file Dockerfile19 --tag my-python:web .

- docker container run --name web --rm --detach --publish 8000:8000 my-python:web
