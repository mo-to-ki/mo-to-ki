# aws-command
目次
> [aws-config](#aws)
>   aws　の認証情報を複数管理する方法


<a id=aws></a>
## aws config

`aws`は以下のディレクトリで認証情報を管理している
```
└── .aws
    ├── .config
    └── .credentials
```

具体的な管理方法は下記のように  
.config ファイル で `[profile {profile}]`  
.credentials　ファイル で `[{profile}]`  
のようにプロフィール名を指定している。  

ただし、実際の運用の場合には、誤用を防ぐために`[default]`は使用しない方が良い。

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
