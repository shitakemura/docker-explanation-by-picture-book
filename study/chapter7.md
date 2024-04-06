# Chapter7

## 7.1

docker container run ubuntu whoami

docker container run ubuntu head -n 4 /etc/os-release

docker container run ruby ruby -e 'print 40 + 2'

## 7.2

docker container run --name hello hello-world

docker container rm hello

## 7.3

docker container run --name hello2 --rm hello-world
