# github-command
目次

> [git pull](#pull)  
    ダウンロードと統合

> [git fetch](#fetch)  
    ダウンロード

> [git merge](#merge)  
    ブランチの統合

> [git checkout](#checkout)  
    ブランチの管理

> [git clone](#clone)  
    リポジトリのダウンロード

> [git reset](#reset)  
    コミットを削除

> [git show](#show)  
    コミットの変更内容を表示

> [git reset](#reset)  
    コミットのリセット

> [git rebase](#rebase)  
    コミットの編集

> [git config](#config)  
    configファイルの編集

<a id=pull></a>
## git pull

これでリモートの`remote-branch`が`local-branch`に統合される。
```shell
git pull origin remote-branch:local-branch
```

<a id=fetch></a>
## git fetch

これでリモートの`origin`がダウンロードされ、`merge`することでローカルに統合できるようになる。
```shell
git fetch origin
```

<a id=merge></a>
## git merge

`dev branch`にいる場合、以下で`dev branch`にリモートの`merge-branch`を統合する。
```shell
git merge origin/merge-branch
```

<a id=checkout></a>
## git checkout

これでリモートの`old-branch`を元に`new-branch`を作成する。
```shell
git checkout -b new-branch origin/old-branch
```

<a id=clone></a>
## git clone

リモートリポジトリをダウンロードする。  
```shell
git clone https://user-name:token@github.com/username/repo.git
```

<a id=reset></a>
## git reset

`n`個のコミットを削除する。 

ただし、   
`--soft`を使った場合、ワーキングエリアとステージングエリアには情報を保持する。 
`--mixed`を使った場合、ワーキングエリアには情報を保持する。 
```shell
git reset --soft HEAD~{n}
```

<a id=show></a>
## git show

コミットの変更内容を表示する。
```shell
git show
```

<a id=rebase></a>
## git rebase

コミットを編集する。  
`{n}`には編集したいコミットの数を入れる。
```shell
git rebase -i HEAD~{n}
```

<a id=reset></a>
## git reset

ステージングエリアの情報を保持したままコミットを削除する。  
`{n}`には削除したいコミットの数を入れる。
```shell
git reset --soft HEAD~{n}
```

作業ディレクトリの情報を保持したままステージングエリアとコミットを削除する。    
`{n}`には削除したいコミットの数を入れる。
```shell
git reset --mixed HEAD~{n}
```

<a id=config></a>
## git config

`github`の`config`ファイルを設定するためのコマンド  
このコマンドでは、`viエディタ`でローカルの`config`ファイルを設定することができる。
```shell
git config --local -e
```
