# JavaScript
[< Back](../)

## リンク

* [JavaScript](./) 今ココ
    * [Quiz](./quiz/)
    * [Answer](./answer/)


## このメモの説明

`<三角括弧>`は適宜入れる値など
`[角括弧]`は省略できる値など


## 基本知識

命令の最後には`;`(セミコロン)  
`//`より右は、コンピューターに読み込まれない(コメント)

### リテラル
プログラムに直接値を書く時の書き方

型|書き方|例
:--|:--|:--
Number(数値)|普通に数値を書く|123<br>3.14
String(文字列)|`"`または`'`で囲む|"hoge"<br>'huga'
Boolean(真偽値)|真なら`true`<br>偽なら`false`|true<br>false


## 演算

### 構文
コメントは計算結果である。
```js
1 + 1   // -> 2
2 - 3   // -> -1
2 * 3   // -> 6
6 / 4   // -> 1.5
10 % 3  // -> 1
-7 % 5  // -> -2
2 ** 16 // -> 256

1 == 1   // -> true
1 == 2   // -> false
1 == "1" // -> true
1 === "1" // -> false
2 != 3   // -> true
2 !== "2"   // -> true
3 < 4    // -> true
4 > 5    // -> false
1 <= 2   // -> true
5 >= 5   // -> true

true || false // -> true
true && false // -> false
!true         // -> false
```

|命令|内容|
|:--|:--|
|a + b<br>a - b<br>a * b<br>a / b|普通に加減乗除|
|a % b|`a`を`b`で割った余り<br>`a`の符号と同じ方を返す|
|a ** b|`a`の`b`乗(指数)|
|a == b|`a`と`b`がなんとなく等しいかどうか(非推奨)|
|a === b|`a`と`b`が厳密に等しいかどうか|
|a != b|`a`と`b`がなんとなく違うかどうか(非推奨)|
|a !== b|`a`と`b`が少しでも違うかどうか|
|a < b<br>a > b<br>a <= b<br>a >= b|`a`が`b` 未満/超過/以下/以上 かどうか|
|a \|\| b|`a`または`b`が真かどうか(OR)|
|a && b|`a`かつ`b`が真かどうか(AND)|
|!a|`a`が真ではないかどうか(NOT)|


## 変数

値を入れて保存しておくコンテナようなもの。数学のものとは異なると考えたほうが良い。  

### 構文
```js
// 宣言(箱を用意する)
let hoge;

// 代入(箱の中身を設定する)
hoge = 123;

// まとめて
let huga = 456;
```

|命令|内容|
|:--|:--|
|let <変数名>;|変数を宣言する。|
|<変数名> = <式>;|<式>の結果を変数に代入する。|

※ 変数名に使えるのは アルファベット(大文字小文字を区別する), 数字, `_`(アンダースコア), `$`(ドル)だけ (ただし数字から始めることはできない)
* OKな例
    * foge
    * HUGA123
    * piyo_piyo
* NGな例
    * 123example ⇒ 数字から始まっている
    * q&a ⇒ 許可されてない記号を含む
    * *var ⇒ 特別な意味を持つ単語(予約語)

### 予約語について
> await break case catch class const continue debugger default delete do else export extends finally for function if import in instanceof new return super switch this throw try typeof var void while with yield  
> enum  
> implements interface package private protected public

以上の単語は特別な意味を持つ為、原則使用できない


## デバッグ表示(console.log)

### 構文
```js
console.log("Hello world!");
```

|命令|内容|
|:--|:--|
|console.log(<表示内容1>\[, 表示内容2...])|デベロッパーツール(検証)のConsoleタブに出力する|


## 条件分岐(if文)

### 構文
```js
if (conditional) {
    // 条件式が真のときのみ実行する内容
}
```

|命令|内容|
|:--|:--|
|if (<条件式>) {<br><真のときのみ実行する内容><br>}|条件式(今回は`conditional`)が真(`true`)の時だけ`{　}`の中を実行する。|

### 応用(if - else)
```js
if (conditional) {
    // 条件式が真のときのみ実行する内容
} else {
    // 条件式が偽のときのみ実行する内容
}
```
### 応用(if - else if - else)
```js
if (conditional1) { // conditional1 : 条件式1
    // 条件式1が真のときのみ実行する内容
} else if (conditional2) { // conditional2 : 条件式2
    // 条件式1が偽で、条件式2が真のときのみ実行する内容
} else {
    // 条件式が全て偽のときのみ実行する内容
}

//以下のコードと同じ意味である
if (conditional1) { // conditional1 : 条件式1
    // 条件式1が真のときのみ実行する内容
} else {
    if (conditional2) { // conditional2 : 条件式2
        // 条件式1が偽で、条件式2が真のときのみ実行する内容
    } else {
        // 条件式が全て偽のときのみ実行する内容
    }
}

// 条件は3つ以上あってもよい
if (conditional1) { // conditional1 : 条件式1
    // 条件式1が真のときのみ実行する内容
} else if (conditional2) { // conditional2 : 条件式2
    // 条件式1が偽で、条件式2が真のときのみ実行する内容
} else if (conditional3) { // conditional3 : 条件式3
    // 条件式1と条件式2が偽で、条件式3が真のときのみ実行する内容
} else {
    // 条件式が全て偽のときのみ実行する内容
}

// elseはなくてもよい
if (conditional1) { // conditional1 : 条件式1
    // 条件式1が真のときのみ実行する内容
} else if (conditional2) { // conditional2 : 条件式2
    // 条件式1が偽で、条件式2が真のときのみ実行する内容
}
```


## 繰り返し(while文)

### 構文
```js
while (conditional) {
    // 条件式が真の間繰り返し実行する内容
}
```

|命令|内容|
|:--|:--|
|while (<条件式>) {<br><繰り返し実行する内容><br>}|条件式(今回は`conditional`)が真(`true`)の間だけ`{　}`の中を繰り返し実行する。|

### 応用
```js
while (true) {
    // 無限ループする内容
}
```


## 繰り返し(for文)

### 構文
```js
for (begin; conditional; step) {
    // 条件式が真の間繰り返し実行する内容
}
```

|命令|内容|
|:--|:--|
|for (<初期化>; <条件式>; <増減など>) {<br><繰り返し実行する内容><br>}|条件式(今回は`conditional`)が真(`true`)の間だけ`{　}`の中を繰り返し実行する。<br><初期化>は初めに一度だけ実行され、<増減など>は繰り返すたびに実行される|

### 基本の書き方
```js
// 10回繰り返す
for (let i = 0; i < 10; i++) {
    console.log(i); // 実際には使う内容に合わせて書き換えましょう
}
// 0
// 1
// 2
// (中略)
// 10
```

## 関数

命令をひとまとめにしてまとめて実行できるもの。  
数学とはやや異なった意味合いを持つ。  
実行時に値を与えてそれに合わせて動作を変えたり、逆に値を返してもらったりできる。

### 構文
```js
// 関数の定義
function functionName() {
    // 実行する内容
}

// 関数の実行
functionName();
```

|命令|内容|
|:--|:--|
|function <関数名>(\[引数1, 引数2...]) {<br>実行する内容<br>}|<関数名>という名前の関数を定義する。<br>引数は例を参照|
|<関数名>()|<関数名>という名の関数を実行する。<br>その関数が値を返す場合は、この式の値はその戻り値(返り値)と呼ばれる値になる。(例参照)|
|return \[戻り値]|戻り値を返してその関数の処理をそこで終了する。|

```js
function showHello() {
    console.log("Hello!");
}

logHello();
// -> Hello!

function showMessage(message) {
    console.log(message);
}

showMessage("How are you doing?");
// -> How are you doing?


function getTax(price, isReduced) {
    if (isReduced) {
        return price * 0.08;
    } else {
        return price * 0.10;
    }
}

getTax(200, true); // 実行時に priceに200, isReducedにtrue が代入される
// -> 16

getTax(300, false);
// -> 30
```