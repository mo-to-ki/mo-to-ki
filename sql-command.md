# sql-command
目次
> [database](#database)  
    データベース関連
> [table](#table)  
    テーブル関連

<a id=database></a>
## database

データベースの一覧を表示する。  
```shell
SHOW databases;
```
データベースを作成する。  
```shell
CREATE DATABASE database-name;
```
データベースを選択する。  
```shell
USE database-name;
```
データベースを削除する。  
```shell
DROP DATABASE database-name;
```
```shell
DROP DATABASE IF EXIST database-name;
```

<a id=table></a>
## table

テーブルの一覧を表示する。  
```shell
SHOW tables;
```
テーブルを作成する。  
ここでは、`user`テーブルを作成している。`id`を`primary key`に指定し、`AUTO_INCREMENT`設定から、`INSERT`した際に`id`が割り当てられていなかった場合、自動的に値が挿入される。
```shell
CREATE TABLE users (
    id INT AUTO_INCREMENT,
    name TEXT,
    PRIMARY KEY (id)
) DEFAULT CHARSET=utf8;
```
