# github-command
目次
> [git merge](#merge)  
    ブランチの統合

> [git fetch](#fetch)  
    ダウンロード

> [git checkout](#checkout)  
    ブランチの管理

> [git rebase](#rebase)  
    コミットの編集

> [git config](#config)  
    configファイルの編集

<a id=merge></a>
## git merge

`dev branch`にいる場合、以下で`dev branch`にリモートの`merge-branch`を統合する。
```shell
git merge origin/merge-branch
```

<a id=fetch></a>
## git fetch

これでリモートの`origin`がダウンロードされ、`merge`することでローカルに統合できるようになります。
```shell
git fetch origin
```

<a id=checkout></a>
## git checkout

これでリモートの`old-branch`を元に`new-branch`を作成する。
```shell
git checkout -b new-branch origin/old-branch
```

<a id=rebase></a>
## git rebase

コミットを編集する。  
`{n}`には編集したいコミットの数を入れる。
```shell
git rebase -i HEAD~{n}
```

<a id=config></a>
## git config

`github`の`config`ファイルを設定するためのコマンド  
このコマンドでは、`viエディタ`でローカルの`config`ファイルを設定することができる。
```shell
git config --local -e
```
