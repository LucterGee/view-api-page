## ItemView 可上焦控件

* 父类View
* 可上焦的基础组件，包含焦点相关的基础方法

#### 写法

* <span style="color:red;">className必须是item</span>
* className为focus这个节点是框架默认的焦点样式，当然也可以自定义

```html

<item class="item" id="item">
    <div class="focus"></div>
</item>
```

#### 标签属性

| index | name           | description | value                         | comment |
|-------|----------------|-------------|-------------------------------|---------|
| 1     | view-focusable | 是否可上焦       | false/0:false;<br>true/1:true | 默认true  |
| 2     | view-up        | 焦点上         | 目标控件id                        | 默认就近原则  |
| 3     | view-down      | 焦点下         | 目标控件id                        | 默认就近原则  |
| 4     | view-left      | 焦点左         | 目标控件id                        | 默认就近原则  |
| 5     | view-right     | 焦点右         | 目标控件id                        | 默认就近原则  |
| 6     | view-change    | 焦点上下左右      | 目标控件（上,下,左,右）id               | 默认就近原则  |
| 7     | view-click     | 点击监听        |                               |         |
| 8     | view-focus     | 焦点变化监听      |                               |         |

#### 方法

| index | name             | description |
|-------|------------------|------------|
| 1     | requestFocus      | 上焦         |
| 2     | requestUnFocus       | 失焦         |