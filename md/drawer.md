## Drawer 抽屉

* 父类：GroupView

#### 写法

```html

<drawer slide-from="left" id="drawer_left">
    <group style="width: 300px;height: 720px;background: white;" id="content">
        <button value="按钮"></button>
        <!--        其他内容-->
    </group>
</drawer>
```

#### 标签属性

| index | name       | description   | value                 | comment |
|-------|------------|---------------|-----------------------|---------|
| 2     | slide-from | 从哪显示抽屉        | right/left/top/bottom | 默认right |
| 3     | key-back   | 显示后，返回键是否关闭抽屉 | true/1:是<br>false/0:否 | 默认是     |


<span style="color:red;">注：这里内部的id必须时content</span>