# SSH鍵の発行

## 作業ディレクトリの確認

>💻 ターミナルの操作

ターミナルを起動するとホームディレクトリにいるはずだが一応下記を実行．

```bash
$ cd ~
```

## フォルダの準備

>💻 ターミナルの操作

- ssh-keyは適切な場所に配置しないと動かない．
- 以下の手順でフォルダを準備する．

下記コマンドでファイルとフォルダの一覧を表示する．

```bash
$ ls -a
```

一覧が表示されるので，「`.ssh`」フォルダを探す．

**`「.ssh」`が存在しない場合のみ**下記コマンドでホームディレクトリに`.ssh`フォルダを作成する．

```bash
$ mkdir -p ~/.ssh
```

エラーが出なければOK．


## ssh-key の発行

>💻 ターミナルの操作

- GitHubにアクセスするにはssh-keyが必要となる．
- ssh-keyは公開鍵と秘密鍵のペアになっており，「公開鍵をGitHubに登録」「秘密鍵をPCのローカルに保存」することで通信時に組み合わせがあっているかどうか判断する．
- ターミナル(windowsはGitBash)を開いて以下のコマンドを入力する．

まずは以下のコマンドで作業ディレクトリを`.ssh`（前項で準備したフォルダ）に変更する．

```bash
$ cd ~/.ssh
```

続いて，以下のコマンドでsshキー（公開鍵と秘密鍵のペア）を発行する．

```bash
$ ssh-keygen
```

実行結果

```bash
Generating public/private rsa key pair.
Enter file in which to save the key (/home/vagrant/.ssh/id_rsa):
```

上の後で`github_rsa`を入力してEnter．

```bash
Enter passphrase (empty for no passphrase):
```

続き．とりあえず入力せずにEnter．

```bash
Enter same passphrase again:
```

続き．パスワード入力していないので再度そのままEnter．

```bash
Your identification has been saved in github_rsa.
Your public key has been saved in github_rsa.pub.
The key fingerprint is:
6f:09:00:22:44:55:66:77:95:89:41:7d:a7:58:1b:92 vagrant@localhost.localdomain
The key's randomart image is:
+--[ RSA 2048]----+
|   .o. .         |
|     oEo+ .      |
|    . +=+=       |
|     o.+==       |
|    . . S .      |
|       - + .     |
|      .   +      |
|         .       |
|                 |
+-----------------+
```

これでssh-keyを発行できた．

### 【参考】

>以下のコマンドで発行した内容を確認できるので，うまくいかない場合は確認してみると良い．
>
>```bash
>$ ls -la | grep GitHub
>```
>
>下記のようになっていればOK．（細かな文字列や数値は異なっていてOK）．
>
>```bash
>-rw-------  1 vagrant vagrant 1675 11月 20 12:18 2014 github_rsa
>-rw-r--r--  1 vagrant vagrant  411 11月 20 12:18 2014 github_rsa.pub
>```


## sshキーの設定

>💻 ターミナルの操作

引き続き，以下のコマンドでssh-keyを動作するようにする．

```bash
$ eval $(ssh-agent)
```

実行結果（数値は異なっていてOK）

```bash
Agent pid 9899
```

作成したキーペアをssh-agentに登録する．

```bash
$ ssh-add ~/.ssh/github_rsa
```

実行結果（ディレクトリなどは異なっていてOK）

```bash
Identity added: /home/vagrant/.ssh/github_rsa
```

以上でssh-keyの準備は完了だが，設定ファイルに変更を加える必要がある．
