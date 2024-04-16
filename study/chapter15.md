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

