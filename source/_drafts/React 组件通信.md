---
title: React 组件通信
tags: React 组件 通信
---
## React 组件通信

### 1.需要通信的组件关系 
#### 1.1 父子组件 
##### 1.1.1 父组件到子组件
父组件通过向子组件传递 props,来实现父组件到子组件的通信
##### 1.1.2 子组件到父组件
- 父组件将一个函数 fn 作为子组件的 props 传给子组件
- 子组件在恰当的时候调用这个 fn，并且把数据放在 fn 的参数里
### 2. 跨级组件
- 待写
### 3. 没有嵌套关系的组件
#### 3.1 使用消息中间件
使用 eventHub/eventBus 来通信
一个组件监听某个事件，另一个组件触发相同的事件并传参，即可实现两个组件的通信
缺点是事件容易越来越多，不好控制代码的复杂度
#### 3.2 使用 Redux
- 每次操作触发一个 action
- action 会触发对应的 reducer
- reducer 会用旧的 state 和 action 早出一个新的 state
- 使用 store.subscribe 监听 state 的变化，一旦 state 变化就重新 render（render 会做 DOM diff，确保只更新该更新的 DOM）
