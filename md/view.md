## View 基础控件

* 作为最基础的控件，包含绝大多数控件的基础方法
* <span style="color:red;">但其本身没有功能指向，一般在开发中也不需要直接使用到</span>

#### 写法

```html

<view id="view"></view>
```

#### 标签属性

| index | name         | description | comment |
|-------|--------------|-------------|---------|
| 1     | id           | 控件的id       |         |
| 2     | view-visible | 控件的显示/监听    |         |

#### 属性

| index | name             | description                                |
|-------|------------------|--------------------------------------------|
| 1     | viewManager      | 控件管理                                       |
| 2     | fatherView       | 父控件                                        |
| 3     | focusable        | 可上焦，默认false                                |
| 4     | isShowing        | 是否显示                                       |
| 5     | isDisplayRange   | 是否在可见范围                                    |
| 6     | positionByFather | 根据父控件（左上角）的坐标位置                            |
| 7     | positionAbsolute | 根据屏幕（左上角）的坐标                               |
| 8     | html             | 设置内部的html                                  |
| 9     | left             | ele的left值                                  |
| 10    | top              | ele的top值                                   |
| 11    | width            | ele的width值                                 |
| 12    | height           | ele的height值                                |
| 13    | ele              | 控件对应的节点                                    |
| 14    | style            | ele的style - readonly 使用getComputedStyle获取的 |
| 15    | position         | ele的坐标                                     |
| 16    | size             | ele的宽高                                     |
| 17    | data             | 控件的数据                                      |
| 18    | page             | 控件所在的page - readonly                       |

#### 方法

| index | name           | description          |
|-------|----------------|----------------------|
| 1     | findViewById   | 获取当前控件下id对应的控件（包括自身） |
| 2     | findEleById    | 获取当前控件下id对应的节点（包括自身） |
| 3     | show           | 显示（会出发显示监听）          |
| 4     | hide           | 隐藏（会出发显示监听）          |
| 5     | enlarge        | 中心放大（在部分不支持放大的盒子无效）  |
| 6     | restoreEnlarge | 恢复放大                 |
| 7     | setStyle       | 改变样式                 |