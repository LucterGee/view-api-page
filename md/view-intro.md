## 控件

* View框架中自带的基础控件

## html编译

* id
    * id作为key值，冲突比较严重，且不能使用getElementById来查找相同id对应多个节点
    * 在编译过程中id会被转成view-id，框架已提供findEleById来获取对应的节点
* view-type
    * view-type作为tag时，会被转化为div+属性view-type=@{view-type}
    * 部分tag在页面上渲染时，在个别盒子上会出现异常，所以在编译过程中就会被转化，不会在页面中渲染

示例

编码部分
```html
    <view id="view"></view>
```

编译之后的
```html
    <div view-type="view" view-id="view"></div>
```

#### view-id

* 一个页面中可以存在多个view-id相同值的节点
* 可以通过框架提供的方法来获取对应的控件或节点
* 在明确知道目标控件（节点）的父控件时，可以直接使用，效率较高，如下：
```javascript
    var view = fatherView.findViewById("id");
    var ele = fatherView.findEleById("id");
```


#### findViewById

获取id对应的控件
* 在查找控件时，以广度优先来查找，直到找到id对应的控件

#### findEleById

获取id对应的节点
* 在查找控件时，以广度优先来查找，直到找到id对应的节点

#### 监听

* 在标签属性中定义的字符串监听
  * 在Page中引入，这个监听在page中
  * 在Fragment中引入，这个监听在fragment中
  * dialog/其他 同理
* 给控件赋值监听
  * 字符串同标签属性
  * 具体方法
  * 不定义：默认往父控件上报，直到page