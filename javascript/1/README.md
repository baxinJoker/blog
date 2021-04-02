# js中隐式转换原理

```js
var a = ？
if(a == 1 && a == 2 && a == 3){
    console.log('隐式转换')
}

解答：
// == 隐式转换调用变量默认或者重写的valueOf方法
a = {
    value:0,
    valueOf:function(){
        return  ++this.value
    }
}
