# sql-command
目次
> [database](#database)  
    データベース関連


<a id=database></a>
## database

データベースの一覧を表示する。  
```shell
SHOW DATABASES;
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
エラーハンドリング
```shell
DROP DATABASE IF EXIST database-name;
```
