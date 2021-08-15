## 概要

MySQLをローカルにダウンロードせずに、dockerでMySQL立ち上げる。
`initdb/`配下に配置したSQLを読み込み初期データを投入できる。

## 前提

- [Docker Desktop](https://docs.docker.com/docker-for-mac/install/) などを利用していること

## 環境に合わせた変更

- MySql バージョン
  - `./docker-compose.yml`の`image`のバージョンを変更する
- 接続情報
  - `./docker-compose.yml`の内容を変更する
- 初期投入データ
  - `./initdb`配下に sql,zip などファイルを配置する

## コマンドヘルプ

ビルド＆起動

```
$ docker-compose up -d --build
```

初期投入データの変更時

```
$ docker-compose down  --rmi all
$ docker-compose up -d --build
```

## DB 接続

#### CUI での接続

```
$ docker exec -it db-container bash
root@f1706d333800:/# mysql -uroot -p
Enter password:
```

#### GUI クライアントでの接続

- host: 127.0.0.1
- port: 3306
- user: root
- password: 設定値
