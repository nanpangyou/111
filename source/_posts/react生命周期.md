---
title: react生命周期
date: 2020-03-31 10:06:14
tags: 
    - react
    - note
---

# React 的生命周期

## React 组件生命周期的执行次数是什么样子的？

- 只执行一次 : `constructor、 componentWillMount、componentDidMount`

- 执行多次 : `render、 子组件的componentWillReceiveProp、componentWillUpdate、componentDidUpdate`

- 有条件执行 : `componentWillUnmount` (页面离开，组件销毁时)

- 不执行的 : 根组件（ReactDOM.render在DOM上的组件）的`componentWillReceiveProps`（因为压根没有父组件给传递props）  

## 执行顺序

假设组件嵌套关系是 App里有parent组件，parent组件有child组件。

如果不涉及`setState`更新

```
    App：   constructor --> componentWillMount -->  render --> 
    parent: constructor --> componentWillMount -->  render --> 
    child:    constructor --> componentWillMount -->  render  --> 
    componentDidMount (child) -->  componentDidMount (parent) --> componentDidMount (App)
```

这时候触发App的setState事件

```
    App：   componentWillUpdate --> render --> 
    parent: componentWillReceiveProps --> componentWillUpdate --> render --> 
    child:    componentWillReceiveProps --> componentWillUpdate --> render -->
    componentDidUpdate (child) -->  componentDidUpdate (parent) --> componentDidUpdate (App)
```

如果触发Parent的setState事件

```
parent： componentWillUpdate --> render --> 
child:     componentWillReceiveProps --> componentWillUpdate --> render --> 
componentDidUpdate (child) -->  componentDidUpdate (parent) 
```

如果只触发child的setState事件

```
child： componentWillUpdate --> render -->  componentDidUpdate (child)
```

这个的执行顺序类似于压栈和出栈


## 参考
 - [react的生命周期](https://www.cnblogs.com/soyxiaobi/p/9559117.html)