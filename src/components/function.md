# 関数

## 関数（function）とは

- 関数とは記述した処理をまとめて名前をつけて使い回せるようにしたもの．
- 一度処理を定義してしまえば，呼び出すだけで実行可能！

### 例

- 関数には「定義」と「実行」が必要．
- 関数には必ず名前をつける．
- `{}`内に実行してほしい処理を記述する．
- 「実行」したいときは名前を呼び出す．

```js
// 関数の定義
function test(){
  console.log('関数は便利！');
}

// 関数の実行
test();

```

## 引数と戻り値

関数は「なにかを入力して」「処理した結果を出力する」動きが基本となる．

### 引数

引数とは「関数に入力する値」である．

- 定義した関数に対して，処理に必要な値を入力する．
- 引数の数は一つでも複数でもOK！

### 戻り値

戻り値とは「関数から出力されてくる値」である．

- 関数の中で計算などを実行した後，結果を返す処理．
- 関数内の変数，配列，オブジェクトなどで返せる．

### 例

`a`と`b`の2つの数を入力し，「加算した結果」を出力する関数を考える．

この場合，`a`と`b`が「引数」で`total`が戻り値となる．

```js
// 関数の定義
function add(a, b){
  const total = a + b;
  return total;
}

// 関数の実行
const sum = add(10, 20);
console.log(sum);   // 30

```

## 数学の関数と同じ

プログラミングの関数は理解が難しいものの一つであるが，数学の関数と同じイメージを持つと理解しやすい．

### 数学の関数

数学の関数は「何かの数値を入力」すると「決まった計算を実行した結果を出力」するものである．

例えば，`f(x) = x^2 + 2x + 1`と関数を定義すると．．．

- `f(2) = 9`,
- `f(5) = 36`,
- `f(10) = 121`

となる．この場合，入力値・関数・出力値をまとめると以下のようになる．

|入力値|関数|出力値|
|--|--|--|
|2|`f(x) = x^2 + 2x + 1`|9|
|5|`f(x) = x^2 + 2x + 1`|36|
|10|`f(x) = x^2 + 2x + 1`|121|

### プログラミングの関数

上記の例をJavaScriptで書くと以下のようになる．

```js
function calculate(x) {
  const result = x * x + 2 * x + 1;
  return result;
}

calculate(2);   // 9
calculate(5);   // 36
calculate(10);    // 121

```

この場合も「記述の仕方が異なるだけでやっていることは同じ」である．

|入力値|関数|出力値|
|--|--|--|
|2|`calculate(x)`|9|
|5|`calculate(x)`|36|
|10|`calculate(x)`|121|


### 💡Key Point

>引数と戻り値がない場合もある（ややこしいポイント）

## 言語にはじめから用意されている関数

これまでに使用した乱数関連も関数であるが，これらはJavaScriptがはじめから用意している関数である．

このような関数を「ビルドイン関数」と呼ぶ．

対して，開発者が自ら定義した関数を「ユーザ定義関数」と呼ぶ．

|引数|関数|戻り値|
|-:|--|-:|
|なし|`Math.random();`|0.534714863872|
|3.1415926535|`Math.floor(3.1415926535);`|3|

```js
Math.random();    // 0.534714863872
  // 引数： なし
  // 戻り値： 0.534714863872

Math.floor(3.1415926535);   // 3
  // 引数： 3.1415926535
  // 戻り値： 3

```

## 【参考】関数の記述方法

JavaScriptにおける関数の定義は以下の3種類を用いることができる．どの方法で記述しても実行方法は同じ．

（現段階では）どれでも同様と考えてOK．

```js
function add1(a, b){
  return a + b;
}

const add2 = function(a, b){
  return a + b;
}

const add3 = (a, b) => {
  return a + b;
}

// 全部同じという理解でOK！
const result1 = add1(10, 20);
const result2 = add2(10, 20);
const result3 = add3(10, 20);

```


## 関数の利用

### 関数の利点

イベントごとに毎回同じ処理を書くのは面倒！

関数を定義しておけば，ボタン押したら実行するだけ！

### 例

押したボタンに応じて，異なる範囲の乱数を発生させたい！

```js
// 関数の定義
function generateRandomNumber(min, max){
  const rand = Math.floor(Math.random() * (max - min + 1) + min);
  return rand;
}

// 実行するときはこんな感じ
const result = generateRandomNumber(1, 9);
console.log(result);

```


### ボタンクリックイベントと組み合わせ

ボタンによって異なる範囲の乱数を発生させることもできる．

```js
$('#btn01').on('click', function () {
 const result = generateRandomNumber(1, 10);
  $('#echo').text(result);
});

$('#btn02').on('click', function () {
 const result = generateRandomNumber(10, 20);
  $('#echo').text(result);
});

$('#btn03').on('click', function () {
 const result = generateRandomNumber(20, 100);
  $('#echo').text(result);
});

```

【参考】janken.htmlに関数を使用したじゃんけんの例もあります！


## 練習

- 最小値と最大値を入力してランダムな数を返す関数を定義しよう！
- 各ボタンのクリック時に関数を実行し，結果を`#echo`に出力しよう！