# VSCode Extensions

> [general](#general)  
    一般的に便利な機能

> [python](#python)  
    python を書くのに便利な機能
___
<a id=general></a>

## general

* Code Spell Checker  
スペルミスが無いか調べてくれる。

* Error Lens  
エラーが発生している行にエラー内容を表示してくれる。

* Github Copilot  
AIが自動で適切なコードを作成してくれる。

* indent rainbow  
インデントがわかりやすいようにカラフルに表示してくれる。

* trailing spaces  
空白がある部分を赤く表示してくれる。

* Github Lens  
コードの変更履歴を見ることができる。

* thunder client  
任意の url へ送る request を管理することはができる。

* SQLTools  
データベースを管理することが出来る。

___
<a id=python></a>

## python

* flake8  
pythonの書き方規約に準じない書き方をした場合にエラーを出す。  
```
--ignore = E226,E302,E41
--max-line-length = 120
--exclude = {path}/*
--max-complexity = 10
```
このように設定することで、以下の内容が適用されます。
| 設定項目          | 説明                             |
|-----------------|---------------------------------|
| ignore          | E226、E302、E41 のエラーを無視します。|
| max-line-length | 1行の最大長を設定します。|
| exclude         | {path}/*ディレクトリを除外します。|
| max-complexity  | コードの複雑さの最大値を10に設定します。|
