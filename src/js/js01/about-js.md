# JavaScript

## JavaScript の役割

| 言語                 | 役割                                                                   |
| -------------------- | ---------------------------------------------------------------------- |
| HTML（マスター済み） | コンテンツの指定<br>タイトル，文章，画像などの記述                     |
| CSS（マスター済み）  | コンテンツの装飾<br>色，大きさ，配置などの指定                         |
| JavaScript           | ユーザー操作，イベント発生による動きを実現<br>（わりとなんでもできる） |

## JavaScript とは

**JavaScript ≠ JAVA**

JavaScript と JAVA の違い

| JavaScript         | JAVA             |
| ------------------ | ---------------- |
| フロントエンド言語 | サーバサイド言語 |
| カモミール         | カモ             |
| オーストラリア     | オーストリア     |
| ハムスター         | ハム             |
| メロンパン         | メロン           |

## Web アプリケーションに欠かせない JavaScript

![Webアプリケーションのしくみ](./img/js_introduction_web_app.svg)

### 言語別人気ランキング（2020 年）

| 言語       | 使用している開発者（%）                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| JavaScript | <code>&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;</code>69.7% |
| HTML/CSS   | <code>&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;</code>62.4%                                                 |
| SQL        | <code>&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;</code>56.9%                                                                               |
| Python     | <code>&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;</code>41.6%                                                                                                                                                                         |
| JAVA       | <code>&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;</code>38.4%                                                                                                                                                                                                 |
| C#         | <code>&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;</code>32.3%                                                                                                                                                                                                                                     |
| TypeScript | <code>&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;</code>28.3%                                                                                                                                                                                                                                                             |
| PHP        | <code>&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;&#124;</code>25.8%                                                                                                                                                                                                                                                                         |

[ソース: https://insights.stackoverflow.com/survey/2020/#technology-programming-scripting-and-markup-languages](https://insights.stackoverflow.com/survey/2020/#technology-programming-scripting-and-markup-languages)

## JavaScript 周辺の技術

![JS周辺技術](./img/js_introduction_around_js.svg)

### よく使われる技術

| 技術                                                                                                   | 特徴                                                                                                                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <img src="./img/1280px-JQuery-Logo.svg.png" width="200px">                                             | - JavaScript のライブラリ．<br>- ユーザ操作イベントやアニメーションを実現<br>- ✅ 生 JS と比較して短くかける．<br>- ✅ web アプリケーションで広く普及している．<br>- ✅ 導入が簡単．<br>- ✅ 学習コストが低い．<br>- 🔼 難しいことをやろうとすると複雑になる．<br>- まずはここから！ |
| <img src="./img/react-logo.png" width="200px"><br><img src="./img/Vue-logo-001.svg" width="200px"><br> | - JavaScript のライブラリ．<br>- ✅ モダンな web アプリケーション（SPA）を実現<br>- ✅ 高速！<br>- ✅ TypeScript での実装も可能<br>- ✅ スマホアプリも見据えた開発が可能．<br>- 🔼 学習コスト<br>- 🔼 環境構築がややハードル．<br>- （私は React が好き）                            |
| <img src="./img/nodejs-logo-vector.svg" width="200px">                                                 | - サーバサイドで JavaScript を動かす技術．<br>- ✅ フロントもサーバも JavaScript で書ける．．！<br>- ✅ サーバサイドの中では環境構築が容易<br>- 🔼 難しいことをやろうとすると複雑になる．                                                                                            |

## JavaScript を書く

### 書き方

`<script></script>`の間に処理を記述！

### 書く場所

- html ファイルの`</body>`のすぐ上に書こう！
- ほかにもいくつか書ける場所があります．
- 別にファイルを作るやり方もあります．

### まず動かす！！

- `alert()`
- `console.log()`

> 文字列は「`'`」か「`"`」で囲む．どちらでも OK！

```html
<script>
  alert("Hello world");

  console.log("Hello world");
</script>
```