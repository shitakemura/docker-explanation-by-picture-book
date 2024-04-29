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

