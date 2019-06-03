## JavaScript@color[orange](再入門)
##### ~論理式が返すのは真偽値じゃない~
---

@snap[midpoint span-100]
@size[1.0em](Qiita</br>)
[@size[0.7em](3歳娘「いつから論理式が真偽値のみを返すと錯覚していた？」)](https://qiita.com/Yametaro/items/17f9b2baa67440b8664a)
@snapend

---
```javascript
var a = 1 == 0;
console.log("a -> " + a);
```
Note:


---
```javascript
if (0 || 1) {
    console.log("aaa");
} else {
    console.log("bbb");
}
```
---
```javascript
var a = 1 && 2 && 3 && 4 && 5 && 0;
console.log(a);
```
---
いつから</br>論理式が真偽値のみを返すと錯覚していた？

Note:
true false だと思った方

---
@snap[west span-0]
AND演算子：</br>
@css[fragment](@size[0.8em](　左右の値どちらもtruthyなら、trueを返す。</br>))
OR演算子：</br>
@css[fragment](@size[0.8em](　左右の値どちらかがtruthyなら、trueを返す。</br>))
@size[0.5em](</br>)
@size[0.5em](※ truthy ... Booleanに変換したとき、trueとみなされる値。1、"false" など</br>)
@size[0.5em](※ falsy ... Booleanに変換したとき、falseとみなされる値。0、null、udefined など</br>)
@snapend

@snap[midpoint fragment]
@fa[times fa-10x]
@snapend

---
@snap[west span-0]
AND演算子：</br>
@css[fragment](@size[0.8em](　左の値がfalsyなら左の値、truthyなら右の値を返す。</br>))
OR演算子：</br>
@css[fragment](@size[0.8em](　左の値がtruthyなら左の値、falsyなら右の値を返す。</br>))
@size[0.5em](</br>)
@size[0.5em](※ truthy ... Booleanに変換したとき、trueとみなされる値。1、"false" など</br>)
@size[0.5em](※ falsy ... Booleanに変換したとき、falseとみなされる値。0、null、udefined など</br>)
@snapend

---
```javascript
var a = "こんにちは" && "こんばんは";
var b = 0 && "こんばんは";
console.log("a -> " + a);
console.log("b -> " + b);
```

+++
```javascript
var a = "こんにちは" || "こんばんは";
var b = 0 || "こんばんは";
console.log("a -> " + a);
console.log("b -> " + b);
```

---
### 

+++
```javascript
// デフォルト値の設定
init: function(_name) {
    this.name = _name || "名無し";
}
```
+++
```javascript
// パフォーマンスの良いコード
var a = lightFunction() || normalFuction() || heavyFunction();
```

+++
@snap[north]
### 短絡評価</br>
@size[0.7em](ショートサーキット評価)
@snapend

@snap[west span-0]
@size[0.9em](返すべき値が途中で決まった場合、最後まで評価しない</br></br>)
@size[0.9em](　ANDの場合： falsyがあった時点で、その値を返す。</br>)
@size[0.9em](　ORの場合：　truthyがあった時点で、その値を返す。</br>)
@snapend
+++
```
// ■条件演算子もどき
var isChild = true;
var price = isChild && 200 || 100;
console.log("price -> " + price);
```

---
```javascript
var a = 1 && 2 && 3 && 4 && 5 && 0;
console.log("a -> " + a);
```
+++
```javascript
var a = 2 && 3 && 4 && 5 && 0;
console.log("a -> " + a);
```

+++
```javascript
var a = 3 && 4 && 5 && 0;
console.log("a -> " + a);
```

+++
```javascript
var a = 5 && 0;
console.log("a -> " + a);
```

---


+++
```javascript
// trueを返すまで、func(n)を実行
func(1) ||
func(2) ||
func(3) ||
func(4);

function func(n){
  console.log(n + "回目の関数");
  return n==3;
}
```
@box[north-east](① # 1回目の関数</br></br>)
@box[east](② # 1回目の関数</br>2回目の関数</br>)
@box[south-east](③ # 1回目の関数</br>2回目の関数</br>3回目の関数)
+++

```javascript
// falseを返すまで、func(n)を実行
func(1) &&
func(2) &&
func(3) &&
func(4);

function func(n){
  console.log(n + "回目の関数");
  return n==3;
}
```
@box[north-east](① # 1回目の関数</br></br>)
@box[east](② # 1回目の関数</br>2回目の関数</br>)
@box[south-east](③ # 1回目の関数</br>2回目の関数</br>3回目の関数)

+++
```
// ■条件演算子もどき
var isChild = true;
var price = isChild && 200 || 100;
console.log("price -> " + price);
```
---
@snap[north]
### まとめ
@snapend

@snap[west span-0]
@size[0.9em](AND演算子：</br>)
@size[0.8em](　左の値がfalsyなら左の値、truthyなら右の値を返す。</br>)
@size[0.9em](OR演算子：</br>)
@size[0.8em](　左の値がtruthyなら左の値、falsyなら右の値を返す。</br>)
@size[0.2em](</br>)
@size[0.9em](短絡評価：</br>)
@size[0.8em](　返すべき値が決まったら、後の式は評価しない。</br>)
@snapend

---
@snap[north]
### 参考資料
@snapend

@snap[west span-0]
@size[1.0em](JavaScript|MDM</br>)
[@size[0.7em](論理演算子</br>)](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Operators/Logical_Operators)
[@size[0.7em](Truthy</br>)](https://developer.mozilla.org/ja/docs/Glossary/truthy)
[@size[0.7em](Falsy</br>)](https://developer.mozilla.org/ja/docs/Glossary/falsy)
@snapend

