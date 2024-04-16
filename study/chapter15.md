# Chapter15

## 15.1

docker container run --name myubuntu --interactive --tty ubuntu:22.04 bash

apt update

apt install vim

which vi

# 15.2

docker container commit myubuntu vi-ubuntu:commit

docker image ls vi-ubuntu

docker container run --rm vi-ubuntu:commit which vi

# 15.3

docker container ls --all

docker container export --output export.tar myubuntu

docker image import export.tar vi-ubuntu:import

docker image ls vi-ubuntu

docker container run --rm vi-ubuntu:import which vi

## 15.4

docker image save --output save.tar ubuntu:22.04

docker image rm ubuntu:22.04

docker image ls ubuntu:22.04

docker image load --input save.tar
