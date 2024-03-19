# linux-command
目次
> [grep](#grep)  
    ファイル内の文字列検索

> [find](#find)  
    特定の文字列を含むファイルを検索

<a id=grep></a>
## grep
ファイル内の文字列検索を行うコマンド

このコマンドでは、`file_name.txt`から`search_string`を検索している。  
```shell
grep 'search_string' file-name.txt
```
その他のオプション

**-r**  
ディレクトリとそのサブディレクトリ内の全ファイルを再帰的に検索
```shell
grep -r 'search_string' /path/
```

**-i**  
大文字小文字を区別せずに検索
```shell
grep -i 'search_string' filename.txt
```

**-n**  
大文字小文字を区別せずに検索
```shell
grep -n 'search_string' filename.txt
```

**other**  
複数ファイルでの検索
```shell
grep 'search_string' file1.txt file2.txt
```

<a id=find></a>
## find

特定の文字列を含むファイルを検索を行うコマンド  
このコマンドでは、`search_string`をファイル名に含んだファイルを検索している。
```shell
find /path/ -type f -name '*search_string*'
```
