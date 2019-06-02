## JavaScript@color[orange](再入門)
##### ~論理式が返すのは真偽値じゃない~
---

![yametaro](https://qiita-image-store.s3.amazonaws.com/0/295452/profile-images/1554676443)
@snap[midpoint span-100]
@size[0.5em]([3歳娘<br/>「いつから論理式が真偽値のみを返すと錯覚していた？」](https://qiita.com/Yametaro/items/17f9b2baa67440b8664a))
@snapend

---
```javascript
var a = 1 !== 0;
console.log(a);
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
いつから論理式が真偽値のみを返すと錯覚していた？

Note:
true false だと思った方

---
@snap[west span-0]
AND演算子：</br>
@css[fragment](　左右の値どちらもtruthyなら、trueを返す。)</br>
OR演算子：</br>
@css[fragment](　左右の値どちらかがtruthyなら、trueを返す。)</br>
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
@css[fragment](　左の値がfalsyなら左の値、truthyなら右の値を返す。</br>)
OR演算子：</br>
@css[fragment](　左の値がtruthyなら左の値、falsyなら右の値を返す。</br>)
@size[0.5em](</br>)
@size[0.5em](※ truthy ... Booleanに変換したとき、trueとみなされる値。1、"false" など</br>)
@size[0.5em](※ falsy ... Booleanに変換したとき、falseとみなされる値。0、null、udefined など</br>)
@snapend

---
```javascript
var a = 0 || "こんにちは";
console.log(a);
```


---
```javascript
var user = {};
var name = user.name || "名無しさん";
```
---
#### 短絡評価（ショートサーキット評価）
```javascript
var a = lightFunction() || heavyFunction();
```
---

```javascript
var a = 1 && 2 && 3 && 4 && 5 && 0;
console.log(a);
```
+++
```javascript
var a = 2 && 3 && 4 && 5 && 0;
console.log(a);
```

+++
```javascript
var a = 3 && 4 && 5 && 0;
console.log(a);
```

+++
```javascript
var a = 5 && 0;
console.log(a);
```

---

---

```javascript

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

---

```

```

