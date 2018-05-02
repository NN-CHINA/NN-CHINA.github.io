---
title:React（Handling Events）  
categories：React  
tags:React  

---


##### **操作事件**（Handling Events）
与DOM元素的操作事件类似，不同之处在于：  

1. React事件命名使用驼峰形式而不是小写；  
2. 传递的函数作为参数而不是字符串；  
3. React不能传`false`去阻止事件响应，而必须明确的调用`preventDefault `来实现；

例如：  
HTML:  

	 <button onclick="activatelasers(); return false">
		Activate Lasers
	 </button>
		
React：

	<button onClick={handleClick}>
	  Activate Lasers
	</button>
	
	function handleClick(e) {
    	e.preventDefault();
  	}
  	
 注意
 
 1. 调用方法没有写`()`时，例如：`onClick={this.handleClick}`应该在构造器中`this.handleClick = this.handleClick.bind(this);`绑定；
 2. 如果并没有使用类范围的语句，可以使用在回掉中使用箭头函数；如：`(e) => this.handleClick(e)`;
 3. 如果在onClick中使用箭头函数问题是，每次渲染控件都会创建新的回调。当回掉作为更低层次的组件的属性时，可能会造成额外的重渲染;
 4.  `<button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>`
`<button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>`
上边两行等价，分别使用`arrow functions`和`Function.prototype.bind`其中`e`代表React事件将被传递作为一个第二参数在id之后，使用arrow functions`必须明确传递它；然而使用`bind`会使参数都被对应地自动传递；