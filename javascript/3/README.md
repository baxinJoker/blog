# 获取对象key的几种方式

```js

方法一：for ... in //获取 自有属性、可枚举属性、及原型对象上继承的属性
方法二：Object.keys() //获取 自有属性、可枚举属性 
方法三：Object.getOwnProperty() //获取 自由属性（包括可枚举不可枚举）

eg: 
var person = {
    name: "baxin",
    age: 25
}
Object.defineProperty(person,'skin',{
    value: 'yellow',
    enumerable:false
})
Object.defineProperty(person,'hair',{
    value: 'black',
    enumerable:true
})
Object.prototype.leftHand = function(){
    console.log('左手')
}
Object.prototype.rightHand = function(){
    console.log('右手')
}

for(let key in person){
    console.log(key)
} //output: name age hair leftHand rightHand

Object.keys(person) // output: name age hair

Object.getOwnProperty(person) // output: name age skin hair