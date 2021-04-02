# 对象及作用域考察

```js

eg: 
var arg1 = 0
var arg2 = 0
function fn(arg1){
    fn = function(arg2){
        console.log(arg1+++arg2)
    }//第一次函数执行 fn执行最新的函数地址
    console.log(arg1++)
}
fn(1)
fn(1)




//output: 1  4