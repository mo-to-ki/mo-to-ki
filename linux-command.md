# linux-command
目次
- [linux-command](#linux-command)
  - [grep](#grep)
  - [find](#find)
  - [which](#which)
  - [alias](#alias)

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
**-l**  
ファイル名のみを出力
```shell
grep -r  -l 'search_string' /path/
```

**--color=auto**  
検索文字列を色付けして表示
```shell
grep --color=auto 'search_string'
```

<a id=find></a>
## find

特定の文字列を含むファイルやディレクトリの検索を行うコマンド  
このコマンドでは、`search_string`をファイル名に含んだファイルを検索している。
```shell
find /path/ -type f -name '*search_string*'
```

<a id=which></a>
## which

特定の文字列を含む実行ファイルの検索を行うコマンド  
このコマンドでは、　`python`の実行ファイルを検索している。
```shell
which pyhton
```

<a id=alias></a>
## alias

コマンドを省略して実行するためのエイリアスを設定するコマンド
```shell
alias gcm='git commit -m' // sample
alias ls='ls --color=auto' // sample2
```
