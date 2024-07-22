# github-command

参考  
[ATLASSIAN](#https://www.atlassian.com/ja/git/tutorials)

目次
- [github-command](#github-command)
  - [git pull](#git-pull)
  - [git fetch](#git-fetch)
  - [git merge](#git-merge)
  - [git brach](#git-brach)
  - [git clone](#git-clone)
  - [git reset](#git-reset)
  - [git show](#git-show)
  - [git rebase](#git-rebase)
  - [git reset](#git-reset-1)
  - [git diff](#git-diff)
  - [git config](#git-config)
  - [git reflog](#git-reflog)
  - [git stash](#git-stash)

## git pull

これでリモートの`remote-branch`が`local-branch`に統合される。
```shell
git pull origin remote-branch:local-branch
```

## git fetch

これでリモートの`origin`がダウンロードされ、`merge`することでローカルに統合できるようになる。
```shell
git fetch origin
```

## git merge

`dev branch`にいる場合、以下で`dev branch`にリモートの`merge-branch`を統合する。
```shell
git merge origin/merge-branch
```

## git brach

今いる branch から {{ new-branch }} を派生して作成する。
```shell
git branch new-branch
```


## git clone

リモートリポジトリをダウンロードする。  
```shell
git clone https://{{ user-name }}:{{ token }}@github.com/username/repo.git
```

## git reset

`n`個のコミットを削除する。 

> `--soft`  
ワーキングエリアとステージングエリアには情報を保持する。  

> `--mixed`  
ワーキングエリアには情報を保持する。  

> `--hard`  
全て削除する。
```shell
git reset --soft HEAD~{n}
```

## git show

コミットの変更内容を表示する。
```shell
git show
```

## git rebase

コミットを編集する。  
`{n}`には編集したいコミットの数を入れる。
```shell
git rebase -i HEAD~{n}
```

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


## git diff
commit と add 前の比較
```shell
git diff
```
commit と add 後の比較
```shell
git diff --cached
```


## git config
`github`の`config`ファイルを設定するためのコマンド  
このコマンドでは、`viエディタ`でローカルの`config`ファイルを設定することができる。
```shell
git config --local --edit
```


## git reflog
reflog コマンドを用いると、以下のように表示されます。
```shell
git reflog
# 99698e4 HEAD@{0}: commit: 0
# 7c53a64 HEAD@{1}: commit: 1
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


## git stash
commit していない差分を保存する
```shell
git stash save "{{ stash につけたい名前 }}"
```
保存してある stash を確認する
```shell
git stash list
# stash@{0}: stash: 0
# stash@{1}: stash: 1
# stash@{2}: stash: 2
# stash@{3}: stash: 3
```
保存してある stash を適用して削除
```shell
git stash pop stash@{0}
```
保存してある stash を適用
```shell
git stash apply stash@{0}
```
保存してある stash の削除
```shell
git stash drop stash@{0}
```