----
title:React(Components and Props)
categories:React
tags:React

---


##### 属性（Components and Props）

组件可以使UI被分离成单独的，可复用，隔离的部分。

**组件**：类似JS中的函数，它接受任意的被称为`props(properties)`输入并返回在屏幕上显示的React元素。

	JS function:
	function Welcome(props) {
  		return <h1>Hello, {props.name}</h1>;
	}
	
	ES6 class
	class Welcome extends React.Component {
  		render() {
    		return <h1>Hello, {this.props.name}</h1>;
  		}
	}
	
	
**注意：**

1. 组件名首字母大写；
2. 所有的组件都必须表现地像对他们的属性带有尊敬的函数。(All React components must act like pure functions with respect to their props.)