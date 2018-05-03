---
title: React(Lists and Keys)  
tags: React  
categories: React  

---

**列表和键**



**键(Keys)**  

keys作用：  

1. 作为条目的唯一标识，在条目改变，被添加或被移除时，可以定位到对应的条目；

		<li key={number.toString()}>1</li>
	 
2. 定位条目；
		
	 
**注意：**

1. 通常使用数据中的IDs作为其key值，要求key值唯一；
2. 如果没有指定key值，React默认将使用索引作为key值；
3. keys只能在数组周围的上下文起作用（Keys only make sense in the context of the surrounding array.）；
4. 在`map()`中的元素才需要key（A good rule of thumb is that elements inside the map() call need keys.）；


