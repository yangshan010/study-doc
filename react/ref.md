## Refs

### React.createRef

#### 创建Refs

```javascript
class MyComponent extends React.Compone {
  constructor(props){
    super(props);
    this.myRef = React.createRef
  }
  render(){
    return <div ref={this.myRef} />
  }
}
```

#### 读取Refs

```javascript
const node = this.myRef.current;
```

ref的值根据节点的类型不同而不同

- 当`ref`用于html元素时，`ref`接收DOM元素作为`current`的属性
- 当`ref`用于自定义的class组件，ref对象接收组件挂载实例作为其`current`属性
- **不能在函数组件上使用ref属性**，因为他们没有实例

### 回调Refs

#### 创建Refs

```javascript
class MyComponent extends React.Compone {
  constructor(props){
    super(props);
    this.myRef = null
  }
  render(){
    return <div ref={ref => this.myRef = ref} />
  }
}
```

#### 读取Refs

```javascript
const node = this.myRef;
```

### 在函数组件中使用Refs

```javascript
function TextInput(props) {
  const textInput = React.useRef(null);
  const handleClick = () => {
    textInput.foucs()
  }
  return <div>
    	<input ref={textInput}/>
      <button onClick={handleClick}>click</button>
    </div>
}
```

