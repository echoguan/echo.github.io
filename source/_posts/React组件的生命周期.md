---
title: React组件的生命周期
categories: 技术
date: 2018-04-03 17:23:10
tags:
  - 笔记
  - React
  - 《深入浅出React和Redux》
---

- 为了理解`React`的工作过程，我们必须要了解`React`组件的**生命周期**。
- 生命周期可能会经历如下三个过程：
  - 装载过程（`Mount`），也就是把组件第一次在`DOM树`中渲染的过程。
  - 更新过程（`Update`），当组件被重新渲染的过程。
  - 卸载过程（`Unmount`），组件从`DOM`中删除的过程。
- 三个不同的过程中，React库会依次调用组件的一些成员函数，这些函数叫做**生命周期函数**。
- 定制一个React组件，实际上就是定制这些生命周期函数。


#### 装载过程
- 当组件第一次被渲染的时候，依次调用的函数如下：
  - `constructor`
  - `getInitialState`
  - `getDefaultProps`
  - `componentWillMount`
  - `render`
  - `componentDidMount`


##### 1. **constructor**
- `constructor`也就是ES6中每个类的构造函数
- 但并不是每个组件都需要定义自己的构造函数。无状态的`React组件`往往就不需要定义构造函数。
- 一个组件需要构造函数，往往是为了以下的目的：
  - **初始化`state`**。因为组件生命周期中任何函数都可能要访问`state`，那么整个生命周期中第一个被调用的构造函数自然是初始化`state`最理想的地方。
  - **绑定成员函数的`this`环境**。


##### 2. getInitialState 和 getDefaultProps
- 这两个方法都只有用`React.createClass`方法创造的组件类才会发生作用。**使用`ES6`语法时，这两个函数根本不会产生作用**。
  - `getInitialState`函数的返回值会用来初始化组件的`this.state`。
  - `getDefaultProps`函数的返回值可以作为`props`的初始值。
- 在`ES6`中，在构造函数中通过给`this.state`赋值完成状态的初始化；通过给类属性`defaultProps`赋值指定`props`的初始值，达到的效果是完全一样的。

```
class Sample extends React.Component{
  constructor(props){
    super(props);
    this.state = {foo : 'bar'};
  }
};

Sample.defaultProps = {
  sampleProp: 0
};
```

- `React.createClass`已经被Facebook官方逐渐废弃，不建议使用。

##### 3. **render**
- `render`函数无疑是`React组件`中最重要的函数。
  - 一个组件可以忽略其他所有函数都不实现，但是一定要实现`render函数`。
  - 因为所有React组件的父类`React.Component类`对除`render`之外的生命周期函数都有默认实现。
- `render`函数并不做实际的渲染动作，它只是返回一个`JSX`描述的结构，最终由`React`来操作渲染过程。
- 如果某些特殊组件的作用不是渲染界面，或者，在某些情况下选择没有东西可画，那就让`render`函数返回一个`null`或者`false`，告诉`React`，该组件这次不需要渲染任何`DOM元素`。
- `render函数`应该是一个**纯函数**。在`render`中调用`this.setState`毫无疑问是错误的。
