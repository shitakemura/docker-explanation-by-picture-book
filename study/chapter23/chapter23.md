# Chapter23

## 23.1

docker network create my-network

docker network ls

docker image build --file ./Dockerfile23 --tag my-php:png .

docker container run my-php:png ping -c 3 -t 1 localhost
