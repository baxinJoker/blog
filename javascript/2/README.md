# 斐波那契数列第n项的值

```js

funtion fn(n){//递归
    if(n == 1 || n == 2){
        return 1
    }
    return fn(n-1) + fn(n-2)
}