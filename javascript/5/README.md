# javascript const\let\var的区别

```js

const //常量 不能改变声明变量的值 不会造成变量提升，在代码运行到const声明之前因为变量提升的问题之间会造成暂时性死域，并且const不会挂载到全局window


let // 不会造成变量提升，在代码运行到const声明之前因为变量提升的问题之间会造成暂时性死域，并且const不会挂载到全局window

var // 会造成变量提升，不会造成暂时性死域，变量声明时会自动挂载到全局window上