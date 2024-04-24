# 第6章 コンテナの基本操作

## 6.1 コンテナを起動する container run

- docker container run hello-world

- docker container run -it ubuntu bash
- whoami
- head -n 4 /etc/os-release

## 6.2 コンテナ一覧を確認する container ls

- docker container ls

- docker container ls --all

## 6.3 コンテナを停止する docker container stop

- docker container ls
- docker container stop [container id / name]
- docker container ls --all

## 6.4 コンテナを削除する docker container rm

- docker container ls --all
- docker container rm [container id / name]
- docker container ls --all
