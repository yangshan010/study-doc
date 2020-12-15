# Refs 转发

> Ref 转发是将`ref`自动的通过组件传递到其子组件的技巧

#### 函数组件无法接受 Refs

在以往的方式中，会定义一个特殊的 props，来接受 ref，达到转发的效果

```javascript
function Custom(props) {}
```
