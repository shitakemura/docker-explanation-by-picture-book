# Chapter17

## 17.1

## 17.2

docker image build --tag my-ubuntu:22.04 .

docker image ls my-ubuntu

docker container run my-ubuntu:22.04 echo 'hello'

docker container run my-ubuntu:22.04 which vi

docker image history my-ubuntu:22.04

## 17.3

docker image build --tag my-ubuntu:22.04 .

docker container run my-ubuntu:22.04 which vi

docker container run --interactive --tty my-ubuntu:22.04 vi

docker image build --file Dockerfile-1layer --tag my-ubuntu:1layer .

docker image build --file Dockerfile-3layers --tag my-ubuntu:3layers .

docker image ls my-ubuntu
