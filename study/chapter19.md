# Chapter19

## 19.1

docker container run --name web --rm --detach --publish 8000:8000 python:3.12.0 python3 -m http.server

docker container run python:3.12.0 which python3

docker image build --file ./study/chapter19/Dockerfile19-1 --tag my-python:web ./study/chapter19

docker container run --name web --rm --detach --publish 8000:8000 my-python:web
