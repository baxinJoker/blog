# React中受控组件和非受控组件

```react

受控组件：值受到react控制的表单元素
    HTML中的表单元素是可输入的，也就是有自己的可变状态，而React中可变状态通常保存在state中，并且只能通过setState() 方法来修改，React讲state与表单元素值value绑定在一起，有state的值来控制表单元素的值


eg:
class App extends React.Component {
    constructor(){
        super()
        this.inputChange = this.inputChange.bind(this)
    }
    state = {
        txt : '受控'
    }
    inputChange(e){
       this.setState({
           txt: e.target.value
       })
    }
    render(){
        console.log(this.state);
        
        return (
            <div>
                {/* 把state的值设置给输入框的value，绑定change事件，这样用户在输入内容的时候调用相应函数，在函数里面把当前设置的值赋值给state，从而达到数据的统一 */}
                <input type="text" value={this.state.txt} onChange={this.inputChange}/>
            </div>
        )
    }
}
ReactDOM.render(<App />,document.getElementById('root'))


非受控组件：表单组件没有value prop
    调用 React.createRef() 方法创建ref对象，将创建好的 ref 对象添加到文本框中，通过ref对象获取到文本框的值


eg:
class App extends React.Component {
    constructor(){
        super()
        
        //创建 ref
        this.txtRef = React.createRef()
    }
    // 获取文本框的值
    getTxt =() => {
        console.log(this.txtRef.current.value)
    }
    render(){
        return (
          <div>
            <input type ="text" ref={this.txtRef} />
            <button onClick ={this.getTxt}>非受控</button>
          </div>
        )
    }
}
