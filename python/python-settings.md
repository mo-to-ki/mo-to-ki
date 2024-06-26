# python-settings
目次

- [python-settings](#python-settings)
  - [package](#package)
    - [pyenv](#pyenv)
  - [pip library](#pip-library)
    - [venv](#venv)


## package
### pyenv
`python`の`version`管理を行うことがでる。  
`brew`ででインストールして、`$PATH`を通すことで使用することがでる。

`pyenv`にある`python`のバージョン確認  
```shell
pyenv versions
```
`pyenv`でインストール可能なバージョン一覧を表示
```shell
pyenv install --list
```

`pyenv`で`Python`のバージョンをインストール
```shell
pyenv install 3.x.x
```

グローバル環境の設定  
```shell
pyenv global python-version
```

ローカル環境の設定  
```shell
pyenv local python-version
```

`pyenv`で設定した`version`の解除  
```shell
pyenv {local or global} --unset
```

## pip library
### venv
仮想環境の作成  
```shell
python -m venv env-name
```

仮想環境の実行  
```shell
source ./env-name/bin/activate
```

仮想環境の停止
```shell
source ./env_name/Scripts/deactivate
```

`pip install`すると
`./lib/{python-version}/site-packages`
にデータが保存される
