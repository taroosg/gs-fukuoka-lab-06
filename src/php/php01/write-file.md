# ファイル操作（書き込み）

## 実装するアプリケーション（todo リスト）の概要

サーバではマシン内のファイルを直接操作することができる（ブラウザ=クライアントサイドからは操作できない）．

この特徴を活かし，ユーザが入力して送信したデータをファイルに保存する todo リストのアプリケーションを実装する．

まずは送信したデータを txt ファイルに書き込んで保存する

### やりたいこと

1. フォームにデータを入力し，サーバに送信する．
2. サーバで受け取ったデータを txt ファイルに書き込んで保存する．
3. 保存してあるデータを読み込んで HTML を作成し，画面に表示する．

### 必要なファイル

- 保存用の txt ファイル「`data`」ディレクトリの「`todo.txt`」（自動で作成されるので準備する必要はない）．
- データを入力して送信するファイル（`todo_txt_input.php`）
- データを受け取ってファイルに書き込むファイル（`todo_txt_create.php`）

## ファイル書き込み処理の実装

### データ送信側ファイルの処理

1. 送信先のファイルを指定する（今回は`todo_txt_create.php`）．
2. 送信方式を指定する（GET or POST）← 今回は POST で実装．
3. input タグに name 属性を指定する．

```php
// todo_txt_input.php

// `action`, `method`, `name`の3つを指定する．
<form action="todo_txt_create.php" method="POST">
  // ...
  <div>
    todo: <input type="text" name="todo">
  </div>
  <div>
    deadline: <input type="date" name="deadline">
  </div>
  <div>
    <button>submit</button>
  </div>
  // ...
</form>

```

### データ受信側ファイルの処理

1. データを受け取る
2. 書き込み先のファイルを開く（なければ新たにファイルを作成）
3. 他の人が書き込まないようロックする
4. データを書き込む
5. ロックを解除する
6. ファイルを閉じる
7. 入力画面に移動

```php
// todo_txt_create.php

// まずは`var_dump($_POST);`で値を確認すること！！

// データの受け取り
$todo = $_POST["todo"];
$deadline = $_POST["deadline"];

// データ1件を1行にまとめる（最後に改行を入れる）
$write_data = "{$deadline} {$todo}\n";

// ファイルを開く．引数が`a`である部分に注目！
$file = fopen('data/todo.txt', 'a');
// ファイルをロックする
flock($file, LOCK_EX);

// 指定したファイルに指定したデータを書き込む
fwrite($file, $write_data);

// ファイルのロックを解除する
flock($file, LOCK_UN);
// ファイルを閉じる
fclose($file);

// データ入力画面に移動する
header("Location:todo_txt_input.php");

```

### 【参考】ファイル操作時の主なオプション

| 引数    | 意味合い                                                    |
| ------- | ----------------------------------------------------------- |
| **`r`** | 読み込みのみで開く                                          |
| `r+`    | 読み込み/書き込み用に開く                                   |
| `w`     | 書き込みで開く&内容を削除 → ファイルがなければ作成          |
| `w+`    | 読み込み/書き込みで開く&内容を削除 → ファイルがなければ作成 |
| **`a`** | 追加書き込みのみで開く → ファイルがなければ作成             |
| `a+`    | 読み込み/追加書き込みで開く → ファイルがなければ作成        |

[参考リンク](https://www.php.net/manual/ja/function.fopen.php)

## 練習

1. `todo_txt_input.php`の form 欄の設定を記述しよう！
2. `todo_txt_create.php`でデータを受け取り，ファイルに書き込もう！
3. 書き込み処理の結果を`todo.txt`で確認しよう！
   - エディタから txt ファイルを開いて書き込まれていれば OK．

## ⚠️ MacOS の場合は権限の設定が必要

（WindowsOS の場合は設定不要）

- 初期状態では PHP からファイルを操作する権限が付与されていない．
- 以下の手順で権限を設定する．

1. 「htdocs に入れた講義フォルダ」で
2. メニュー表示 => 情報を見る => 共有とアクセス権
3. 全て「読み/書き」に変更 => 歯車ボタン => 内包している項目に適用