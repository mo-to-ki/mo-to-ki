# aws-command
目次
> [aws-config](#aws)  
    aws　の認証情報を複数管理する方法


<a id=aws></a>
## aws config

`aws`は以下のディレクトリで認証情報を管理している
```
└── .aws
    ├── .config
    └── .credentials
```

認証情報の設定方法は以下のコマンドで行う。  
以下では、`profile-name`というプロフィール名の認証情報を設定している。  

誤用を防ぐために`--profile`でプロフィール名を指定した方が良い。  
```shell
aws configure --profile profile-name
```

具体的な管理方法は下記のように  
.config ファイル で `[profile profile-name]`  
.credentials　ファイル で `[profile-name]`  
のようにプロフィール名を指定している。  

* **.config**
```shell:.config
[profile hoge]
output = json
region = {リージョン}

[profile fuga]
output = json
region = {リージョン}

[default]
output = json
region = {リージョン}
```
* **.credentials**
```shell:.credentials
[hoge]
aws_access_key_id = {アクセスキー}
aws_secret_access_key = {シークレットキー}

[fuga]
aws_access_key_id = {アクセスキー}
aws_secret_access_key = {シークレットキー}

[default]
aws_access_key_id = {アクセスキー}
aws_secret_access_key = {シークレットキー}
```

ちなみに、`aws`コマンド使用時には、以下のようにプロフィールを指定することで使い分けることができる。
```shell
aws {command} --profile {profile}
```
