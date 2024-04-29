# 第17章 viの使えるubuntuイメージを作る

## 17.1 ベースイメージを指定する FROM

## 17.2 Dockerfileでイメージをビルドする image build

#### Dockerfileでイメージをビルドする

- docker image build --file Dockerfile17 --tag my-ubuntu:22.04 .

- docker image ls my-ubuntu
- docker container run my-ubuntu:22.04 echo 'hello'
- docker container run my-ubuntu:22.04 which vi
- docker image history my-ubuntu:22.04
