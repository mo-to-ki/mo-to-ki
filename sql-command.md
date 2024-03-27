# sql-command
目次
> [database](#database)  
    データベース関連

> [table](#table)  
    テーブル関連

>  [select](#select)  
    テーブルのデータを取得

## データ型

**整数型**  
| name          | detail                |
|---------------|-----------------------|
| `TINYINT`     | 非常に小さな整数      |
| `SMALLINT`    | 小さな整数            |
| `MEDIUMINT`   | 中程度の整数          |
| `INT` / `INTEGER` | 標準的な整数      |
| `BIGINT`      | 大きな整数            |
| `BIT`         | ビット値              |

**浮動小数点数型**  
| name                 | detail                  |
|----------------------|-------------------------|
| `FLOAT`              | 単精度浮動小数点数      |
| `DOUBLE`             | 倍精度浮動小数点数      |
| `DECIMAL` / `NUMERIC`| 固定小数点数            |

**日付と時間型**  
| name        | detail                           |
|-------------|----------------------------------|
| `DATE`      | 日付 ('YYYY-MM-DD')              |
| `TIME`      | 時間 ('HH:MM:SS')                |
| `DATETIME`  | 日付と時間の組み合わせ ('YYYY-MM-DD HH:MM:SS') |
| `TIMESTAMP` | タイムスタンプ ('YYYY-MM-DD HH:MM:SS')        |
| `YEAR`      | 年 (4桁の数字)                   |

**文字列型** 
| name        | detail                  |
|-------------|-------------------------|
| `CHAR`      | 固定長文字列            |
| `VARCHAR`   | 可変長文字列            |
| `BINARY`    | 固定長バイナリ文字列    |
| `VARBINARY` | 可変長バイナリ文字列    |
| `BLOB`      | バイナリ大オブジェクト  |
| `TEXT`      | テキストデータ          |
| `ENUM`      | 列挙型                  |
| `SET`       | セット型                |

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

ここでは、`id`を`primary key`に指定し、`user`テーブルを作成している。  
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

テーブルを削除する。  
```shell
DROP TABLE table-name;
```

<a id=select></a>
## select

テーブルのデータを取得する。  
```shell
SELECT * FROM table-name;
```

特定のデータを取得する。  

ここでは、`id = 3`を満たすデータを検索し、取得している。
```shell
SELECT * FROM users WHERE id = 3;
```

時間`datetime`を比較して、条件を満たすものを取得する。  

ここでは、`table-name`内で、  
`id < 100`の条件を満たすデータを`date`（日付）で降順に整列させ、3番目~4番目の物を取得している。
```shell
SELECT * FROM table-name
WHERE id < 100
ORDER BY date
DESC LIMIT 5 OFFSET 2;
```
