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
ここでは、`user`テーブルを作成している。  
`id`を`primary key`に指定している。  
`AUTO_INCREMENT`設定から、`INSERT`した際に`id`の値が割り当てられていなかった場合、自動的に値が挿入される。
```shell
CREATE TABLE users (
    id INT AUTO_INCREMENT,
    name TEXT,
    PRIMARY KEY (id)
) DEFAULT CHARSET=utf8;
```

テーブルの構造を表示する。 
```shell
DESCRIBE table-name;
```

テーブルにデータを挿入する。  
ここでは、`users`テーブルに、`name="motoki omamiuda"`のデータを挿入している。
```shell
INSERT INTO user(name) VALUES ("motoki omamiuda");
```

テーブルのデータを取得する。  
```shell
SELECT * FROM table-name;
```

テーブルを削除する。  
```shell
DROP TABLE table-name;
```
