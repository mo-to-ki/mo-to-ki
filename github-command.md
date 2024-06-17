# github-command

参考  
[ATLASSIAN](#https://www.atlassian.com/ja/git/tutorials)

目次
- [github-command](#github-command)
  - [git pull](#git-pull)
  - [git fetch](#git-fetch)
  - [git merge](#git-merge)
  - [git checkout](#git-checkout)
  - [git clone](#git-clone)
  - [git reset](#git-reset)
  - [git show](#git-show)
  - [git rebase](#git-rebase)
  - [git reset](#git-reset-1)
  - [git config](#git-config)
  - [git reflog](#git-reflog)

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
git config --local --edit
```

<a id=reflog></a>
## git reflog
reflog コマンドを用いると、以下のように表示されます。
```shell
git reflog
# 99698e4 (HEAD -> main, origin/main, origin/HEAD) HEAD@{0}: commit: update: user
# 7c53a64 HEAD@{1}: merge origin/main: Fast-forward
# 46bde33 HEAD@{2}: commit: 2
# 1e04a9a HEAD@{3}: commit: 3
# 05f755f HEAD@{4}: commit: 4
# 5cddd0e HEAD@{5}: commit: 5
```
ここで、
```shell
git reset HEAD@{2}
```
とすることで HEAD@{2} のコミットへ遡ることができます