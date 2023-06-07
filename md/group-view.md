## GroupView 多个可上焦控件的组控件

* 父类：ScrollView
* 作为最基础的组控件，内置<span style="color:red;">焦点就近原则</span>

#### 写法

* <span style="color:red;">必须设置固定宽高，滚动范围以宽高为准（overflow：hidden时可见的），不以可见节点为准</span>

```html

<group id="group"></group>
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
| 9     | view-select    | 是否保留上一次上焦记录 |                               |         |

#### 方法

| index | name         | description |
|-------|--------------|-------------|
| 1     | requestFocus | 上焦          |