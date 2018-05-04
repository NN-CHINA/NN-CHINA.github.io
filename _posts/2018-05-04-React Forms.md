---

title: React(Forms)  
cateogries: React  

---

**受控组件(Controlled Components):**  
在HTML中，诸如有代表性的表单元素`<input>`，`<textarea>`, 和 `<select>`都包含自己的状态并且基于用户的输入来更新。  
在React中，可变的状态是被保存在控件的state属性中，并且只能使用setState()更新。

基于两者，可以让React的state成为数据源（single source of truth），在用户后续的输入中，React组件渲染表单，也会控制表单内的变化。这样的控件称为`Controlled Components`

**非受控组件：**  
`<input type="file">`  
[File API](https://developer.mozilla.org/en-US/docs/Web/API/File/Using_files_from_web_applications)

**注意：**  
1. 操作多个表单元素时，可以为每个元素设置`name`属性;

**参考代码如下：**  

	import React, { Component } from 'react';

	export default class Forms extends Component {
	  constructor(props) {
	    super(props)
	    this.state=({
	      value:'',
	      textValue:'There is text area!',
	      selectValue:'cat',
	      multiSelectValues:['A','B'],
	      })
	    this.handleSubmit = this.handleSubmit.bind(this);
	    this.handleChange = this.handleChange.bind(this);
	    this.handleTextAreaChange = this.handleTextAreaChange.bind(this);
	    this.handleSelectChange = this.handleSelectChange.bind(this);
	  }

	  handleSubmit(event) {
	    console.log(event);
	    const name = this.state.value;
	    var alertString = 'A name is Submitted:' + this.state.value;
	    if (name == '') {
	      alertString = 'You need input correct Name';
	    }
	    alert(alertString);
	    event.preventDefault();
	  }

	  handleChange(event) {
	    console.log(event);
	    this.setState(
	      {value: event.target.value}
	    )
	  }

	  handleTextAreaChange(event) {
	    this.setState({
	      textValue:event.target.value
	    })
	  }

	  handleSelectChange(event) {
	    //equivalent
	    // var partialState = {};
	    // partialState[name] = value;
	    // this.setState(partialState);
	    const name = event.target.name;
	    this.setState({
	      //Computed property names
	      [name]:event.target.value
	    })
	  }

	  render() {
	    return (
	      <div>
	        <div>
	            <form onSubmit={this.handleSubmit}>
	                <label>
	                Name:
	                <input type='text' name='name' value={this.state.value} onChange={this.handleChange}/>
	              </label>
	              <input type='submit' value='Submit'/>
	            </form>
	        </div>
	
	        <div>
	          <label>
	              <textarea value={this.state.textValue} onChange={this.handleTextAreaChange}>
	              </textarea>
	          </label>
	        </div>
	
	        <div>
	          <select>
	            <option value='apple'>Apple</option>
	            <option value='banana' selected>Banana</option>
	          </select>
	        </div>
	
	        <div>
	          <select value={this.state.selectValue} onChange={this.handleSelectChange} name='selectValue'>
	            <option value='apple'>Orange</option>
	            <option value='cat'>Cat</option>
	            <option value='strawberry'>Strawberry</option>
	          </select>
	        </div>
	
	        <div>
	          <select value={this.state.multiSelectValues} onChange={this.handleSelectChange} name='multiSelectValues' multiple={true}>
	            <option value='D'>D</option>
	            <option value='A'>A</option>
	            <option value='B'>B</option>
	          </select>
	        </div>
	
	
	        <div>
	          <input type="file" />
	        </div>
	      </div>
	    )
	  }
	}
