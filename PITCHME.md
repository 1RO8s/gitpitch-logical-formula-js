## JavaScript@color[orange](再入門)
##### ~論理式が返すのは真偽値じゃない~
---

![ss](https://qiita-image-store.s3.amazonaws.com/0/295452/profile-images/1554676443)
---

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
@snap[north-east span-40 text-08]
@box[](AND演算子 # 左右の値どちらもtruthyなら、trueを返す。)
@snapend

---
@snap[west span-0]
AND演算子：</br>
@css[fragment](　左右の値どちらもtruthyなら、trueを返す。)</br>
OR演算子：</br>
@css[fragment](　左右の値どちらかがtruthyなら、trueを返す。)
@snapend

@snap[south-west span-0]
@size[0.5em](※ truthy ... Booleanに変換したとき、trueとみなされる値。1、"false" など)</br>
@size[0.5em](※ falsy ... Booleanに変換したとき、falseとみなされる値。0、null、udefined など)
@snapend

@snap[midpoint fragment]
@fa[times fa-10x]
@snapend

---
```javascript
var a = 0 || "こんにちは";
console.log(a);
```


---
@title[よくある使い方]
```javascript
var user = {};
var name = user.name || "名無しさん";
```

