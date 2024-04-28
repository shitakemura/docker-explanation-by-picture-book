# 第13章 イメージの基本操作

## 13.1 イメージの一覧を確認する image ls

#### ホストマシンに存在するイメージの一覧を確認する

- docker image ls

## 13.2 イメージを取得する image pull

#### いろいろなUbuntuイメージを取得する

- docker image pull ubuntu:23.10
- docker image pull ubuntu:24.04
- docker image pull ubuntu:latest
- docker image ls ubuntu

## 13.3 イメージの詳細を確認する image inspect

#### イメージのコンテナ起動時コマンドを調べる

- docker image pull ruby:3.2.2
- docker image inspect ruby:3.2.2

- docker container run --rm ruby:3.2.2 printenv RUBY_VERSION

- docker container run --rm --interactive --tty ruby:3.2.2
- [3, 1, 2].sort
- exit
