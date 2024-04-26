# 第9章 Nginxサーバを起動してブラウザからアクセスする

## 9.1 コンテナのポートを公開する container run --publish

#### Nginxコンテナを起動してポートを公開する

- docker container run --rm --publish 8080:80 nginx

#### 起動しているコンテナのポート情報を確認する

- docker container ls
