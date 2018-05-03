---
title: React(State and Lifecycle)  
tags: React  
categories: React  

---


##### 状态和生命周期(State and Lifecycle)

**注意**

1. 与属性相似，但状态私有且完全被控件控制；
2. 仅适用于被定义成类的控件；
3. 生命周期(Lifecycle)
	`componentDidMount()`组件已渲染到DOM
	`componentWillUnmount()`组件已从DOM上移除
4. 不要直接修改状态；`this.state.comment = 'Hello';`而是用`this.setState({comment: 'Hello'});`,唯一可以赋值的地方是在构造器中;
5. 状态和属性更新可能是异步的。React可能把一批的状态改变调用变成单一的更新操作（React may batch multiple setState() calls into a single update for performance.），因此不应该依赖他们的值去计算下个状态；
6. 同步操作，使用第二形式的`setState()`可接受函数而不是对象。
