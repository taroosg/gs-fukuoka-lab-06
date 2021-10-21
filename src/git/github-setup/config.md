# 設定ファイルの編集

## ターミナルで設定ファイルを開く

> 💻 ターミナルの操作

ややこしいので 1 つずつ確認しながら進めること！

- 下記のコマンドで設定ファイルに書き込む．
- 2 行目の「`vi ~...`」ではターミナル内でエディタを起動する．画面が変わりますがパニックにならないよう注意！

ターミナルで以下を 1 行ずつ実行．1 行目がファイルの作成で，2 行目でエディタでファイルを開く．

```bash
$ touch ~/.ssh/config
$ vi ~/.ssh/config
```

## 設定ファイルに書き込み

> 💻 ターミナルの操作

- このエディタにはインサートモードとコマンドモードの 2 つがあり，最初はコマンドモードで表示されるが，追記を行うにはインサートモードに変更する必要がある．
- インサートモードにするには「`i`」キーを押す．画面のどこかに `—INSERT—` や `—挿入—` などの文字列が表示される．その状態で「`Host github`」からの 5 行を追記する．
- 追記が終わったら「esc（コマンドモードに戻る）」→「`:wq`（保存して終了のコマンド）」→「`enter`（実行）」で元の画面に戻る．
- ミスったと感じたら「`esc`」→「`:q!`」→「`enter`」でエディタを終了できるので，もう一度「`vi ~...`」を入力してやり直しましょう．

`.ssh/config` ファイルを開くと空なので以下を追記する．

```text
Host github.com
  HostName github.com
  Identityfile ~/.ssh/id_rsa
  Port 22
  User git
```

## 権限の変更

> 💻 ターミナルの操作

続いて，設定ファイルの権限を変更する．ターミナルで以下を実行．

```bash
$ chmod 700 ~/.ssh/config
```

エラーが出なければ OK．