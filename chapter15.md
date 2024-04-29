# 第15章 viの使えるubuntuイメージを作り持ち運ぶ

## 15.1 コンテナにviをインストールする

#### コンテナの準備

- docker container run --name myubuntu --interactive --tty ubuntu:22.04 bash
- apt update
- apt install vim
- which vi

## 15.2 コンテナをイメージにする container commit

#### コンテナからイメージを作る

- docker container commit myubuntu vi-ubuntu:commit
- docker image ls vi-ubuntu

- docker container run --rm vi-ubuntu:commit which vi

## 15.3 コンテナをtarにしてからイメージにする container export + image export

#### コンテナからtarを作る

docker container export --output export.tar myubuntu

#### tarからイメージを作る

- docker image import export.tar vi-ubuntu:import

- docker container run --rm vi-ubuntu:import which vi

## 15.4 イメージをtarにしてからイメージにする image save + image load

#### イメージからtarを作る

- docker image save --output save.tar ubuntu:22.04

#### tarからイメージを作る

- docker image rm ubuntu:22.04
- docker image ls ubuntu:22.04

- docker image load --input save.tar
