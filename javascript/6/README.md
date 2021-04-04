# 什么是防抖和节流？怎样实现？

## 防抖

触发高频事件后 n 秒内函数只会执行一次，如果 n 秒内高频事件再次被触发，则重新计算时间。

```js   
function debounce(fn,delay){
    let timer
    return function() {
        clearTimeout(timer)
        timer = setTimeout(function(){
            fn()
        },delay)
    }
}

## 节流

高频事件触发，但在 n 秒内只会执行一次，所以节流会稀释函数的执行效率。



function throttle(fn,delay){
    let flag
    return function(){
        if(flag){
            return 
        }
        flag = true
        fn()
        setTimeout(function(){
            flag = false
        },delay)

    }
}