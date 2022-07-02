# JavaScript 問題集 回答
[< Back](../)

## リンク

* [JavaScript](../)
    * [Quiz](../quiz/)
    * [Answer](./) 今ココ

## 1 計算

### 1-1
* `123 + 456`
* `123 - 456`
* `123 * 456`
* `123 / 456`
* `1024 \ 11`
* `3 ** 10`


## 2 デバック表示

### 2-1
```js
console.log("Hello world!");

// シングルクオーテーションでもよい
console.log('Hello world!');
```


## 3 変数

### 3-1
```js
let hoge = 3;
let fuga = 5;

hoge + fuga
// 8
```

### 3-2
次のうち、一般の変数名として許可されているものをすべて選びましょう
* **hoge123**
* ~~456fuga~~ 数字で始まっている
* **$piyo** ドルマークはOK(ただしあまりお勧めしない)
* **for_user** アンダースコアはOK
* ~~to-robots~~ ハイフンは許可されていない
* **FizzBuzz**


## 4 if文

### 4-1
```js
let isOK = confirm("Are you OK?");

if (isOK) {
    alert("Loading..");
} else {
    alert("Canceled..");
}
```

### 4-2
```js
let day = new Date().getDay();

if (day === 0) {
    console.log("日曜日");
} else if (day === 1) {
    console.log("月曜日");
} else if (day === 2) {
    console.log("火曜日");
} else if (day === 3) {
    console.log("水曜日");
} else if (day === 4) {
    console.log("木曜日");
} else if (day === 5) {
    console.log("金曜日");
} else {
    console.log("土曜日");
}
```


## 5 while文

### 5-1
```js
// 乱数の一時保存用変数
// 0.1以上の初期値を入れることで、いきなりループが終わるのを防ぐ
let temp = 1;

while (temp > 0.1) { // condition には適切な条件式を入れる
    
    // 乱数を生成して temp に保存する
    temp = Math.random();
    
    // その乱数を表示する
    console.log(temp);

}
```
別解
```js
let temp = 1;

// temp <= 0.1 じゃない間繰り返す ⇔ temp <= 0.1 になるまで繰り返す
while (!(temp <= 0.1)) {
    temp = Math.random();
    console.log(temp);
}
```