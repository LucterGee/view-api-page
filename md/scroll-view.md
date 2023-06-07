## ScrollView 滚动控件

* 父类View
* 作为最基础的滚动空间，包含绝大多数滚动控件的基础方法
* <span style="color:red;">但其本身除了滚动，没有功能指向，一般在开发中也不需要直接使用到</span>

#### 写法

```html

<scroll id="scroll"></scroll>
```

#### 标签属性

| index | name             | description | comment     |
|-------|------------------|-------------|-------------|
| 1     | view-animation   | 是否开启滚动动画    |             |
| 2     | view-scrollStart | 开始滚动监听      |             |
| 3     | view-scrolling   | 滚动中监听       |             |
| 4     | view-scrollEnd   | 结束滚动监听      |             |
| 5     | view-locate      | 滚动的目标位置     | 调用滚动到子控件时生效 |

#### 方法

| index | name                    | description |
|-------|-------------------------|-------------|
| 1     | scrollToChild           | 滚动到子控件      |
| 2     | scrollVerticalToChild   | 纵向滚动到子控件    |
| 3     | scrollHorizontalToChild | 横向滚动到子控件    |
| 4     | scrollTo                | 滚动到         |
| 5     | scrollVerticalTo        | 纵向滚动到       |
| 6     | scrollVertical          | 纵向滚动        |
| 7     | scrollVerticalToStart   | 纵向滚动到最顶部    |
| 8     | scrollVerticalToEnd     | 纵向滚动最底部     |
| 9     | scrollHorizontalTo      | 横向滚动到       |
| 10    | scrollHorizontal        | 横向滚动        |
| 11    | scrollHorizontalToStart | 横向滚动到最左侧    |
| 12    | scrollHorizontalToEnd   | 横向滚动到最右侧    |