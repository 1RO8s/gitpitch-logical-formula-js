### JavaScriptの@color[再入門](red)
~論理式が返すのは真偽値じゃない~
---
```
var a = 1 !== 0;
console.log(a);
```
---
```
if (0 || 1) {
    console.log("aaa");
} else {
    console.log("bbb");
}
```
---
```
var a = 1 && 2 && 3 && 4 && 5 && 0;
console.log(a);
```
```
var a = 0 || "こんにちは";
console.log(a);
```


---?color=lavender
@title[よくある使い方]
```javascript
var user = {};
var name = user.name || "名無しさん";
```

