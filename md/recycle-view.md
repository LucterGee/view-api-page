## RecycleView 子控件可循环使用的列表控件

* 父类：GroupView
* 列表方向：纵向/横向
* 列表行/列：默认单行/单列，可设置
* 焦点可首尾变化：默认关，可开启
* 滚动效果可首尾相接：默认关，可开启

#### 写法

```html

<recycle id="recycle"></recycle>
```

#### 标签属性

| index | name             | description        | value         | comment             |
|-------|------------------|--------------------|---------------|---------------------|
| 1     | view-orientation | 列表方向               | v:纵向;<br>h:横向 | 默认纵向                |
| 2     | view-row         | 渲染的行数              |               | 只在横向时生效             |
| 3     | view-col         | 渲染的列数              |               | 只在纵向时生效             |
| 4     | view-circulate   | 滚动效果可首尾相接          |               | 打开效果需要在loop为true时生效 |
| 5     | view-loop        | 焦点可首尾变化            |               |                     |
| 6     | view-margin      | 每个adapter生成布局之间的间隔 |               |                     |

#### 属性

当data和adapter都设置之后，列表才会开始渲染

| index | name        | description   | value | comment |
|-------|-------------|---------------|-------|---------|
| 1     | adapter     | 适配器           |       |         |
| 2     | selectIndex | 当前上焦/驻留的index |       |         |
| 3     | data        | 列表数据          |       |         |

#### 方法

| index | name          | description |
|-------|---------------|-------------|
| 1     | push          | 在数据末尾中添加    |
| 1     | pop           |             |
| 1     | unshift       |             |
| 1     | shift         |             |
| 1     | splice        |             |
| 1     | sort          |             |
| 1     | reverse       |             |
| 1     | scrollByIndex | 滚动到对应index  |
| 1     | focusByIndex  | 上焦到对应index  |