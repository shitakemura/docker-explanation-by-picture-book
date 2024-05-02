# 第22章 ホストマシンで編集したファイルをRubyコンテナで実行する

## 22.1 バインドマウントの利用 container run --mount

#### バインドマウントとは

- ボリューム: コンテナのデータをコンテナ外に保存するための仕組み
- バインドマウント: ホストマシンの任意のディレクトリをコンテナにマウントする仕組み

#### コンテナにバインドマウントする

- docker container run --name ruby --rm --interactive --tty --mount type=bind,source="$(pwd)",target=/my-work ruby:3.2.2 bash

- ls /my-work/
- ruby /my-work/hello.rb

- rm /my-work/hello.rb
- exit
- ls
