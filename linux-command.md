# linux-command
目次
> [grep](#grep)  
    ファイル内の文字列検索

> [find](#find)  
    特定の文字列を含むファイルを検索

<a id=grep></a>
## grep
ファイル内の文字列検索を行うコマンド
```shell
grep 'search_string' file-name.txt
```
このコマンドでは、`file_name.txt`から`search_string`を検索している。  
その他のオプション

**-r**
```shell
grep -r 'search_string' /path/
```
ディレクトリとそのサブディレクトリ内の全ファイルを再帰的に検索

**-i**
```shell
grep -i 'search_string' filename.txt
```
大文字小文字を区別せずに検索

**-n**
```shell
grep -n 'search_string' filename.txt
```
大文字小文字を区別せずに検索

**other**
```shell
grep 'search_string' file1.txt file2.txt
```
複数ファイルでの検索

<a id=find></a>
## find
特定の文字列を含むファイルを検索を行うコマンド
```shell
find /path/ -type f -name '*search_string*'
```
このコマンドでは、`search_string`をファイル名に含んだファイルを検索している。  
