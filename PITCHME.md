## JavaScript@color[orange](再入門)
##### ~論理式が返すのは真偽値じゃない~
---

@snap[docslink]
@size[0.2em][3歳娘<br/>「いつから論理式が真偽値のみを返すと錯覚していた？」](https://qiita.com/Yametaro/items/17f9b2baa67440b8664a)
@snapend

---
```javascript
var a = 1 !== 0;
console.log(a);
```
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
- 左右の値どちらかがtruthyなら、trueを返す。|
- 左側がtruthyな場合は左側の値を返す。逆に、左側がfalsyな場合は右側の値を返す。|
@snap[fragment]
@fa[times]
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

