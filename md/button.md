## Button 按钮

* 父类：ItemView
* 和ItemView区别
    * 主要偏向点击功能
    * 控件风格以按钮形式
    * 方法及功能与ItemView基本一致

#### 写法

这里的button标签，和原生的button没有关系，在渲染的时候，以div形式渲染

````html

<button id="button"></button>
````

#### 标签属性

| index | name          | description  | value             | comment         |
|-------|---------------|--------------|-------------------|-----------------|
| 1     | value         | 按钮文字         |                   |                 |
| 2     | size-type     | 大小类型         | medium/small/mini | 默认small         |
| 3     | size          | 大小           | width,height      | 例如：200,100 英文逗号 |
| 4     | focus-enlarge | 上焦后放大比       |                   | 默认100           |
| 5     | focus-color   | 默认焦点/背景边框的颜色 |                   | 默认#de2910       |
| 6     | value-color   | 文字颜色         |                   | 默认#dcdfe6       |
| 7     | radius        | 按钮圆角         |                   | 默认7px           |


#### 定制化

* 定制背景

在button中定义一个<span style="color:red;">id为bg</span>的子节点，这个子节点会替代默认的背景

示例
```html

<button id="button">
    <div style="background: #aaaaaa" id="bg"></div>
</button>
```

注：示例中定制了一个#aaaaaa的背景，这里可以使用各种样式，当然也可以用图片代替，但<span style="color:red;">大小以size-type或size为准</span>

* 定制焦点

在button中定义一个<span style="color:red;">id为focus</span>的子节点，这个子节点会替代默认的焦点

示例
```html

<button id="button">
  <img src="../images/focus/120x60.png" width="158" height="98" id="focus">
</button>
```

注：这里id为focus的节点，需要设置固定宽高，这个<span style="color:red;">宽高会设置到button中</span>，button的背景、文字宽高不变，但会<span style="color:red;">居中</span>

* 添加icon

在button中定义一个<span style="color:red;">id为icon</span>的子节点，这个子节点会添加到按钮中

```html

<button id="button">
  <img src="../images/icon/icon_vip.png" width="28" height="16" locate="center" id="icon">
</button>
```

注：id为icon的节点中，定义的属性locate="center"表示icon在button中的位置，
* locate
  * left：靠左（默认）
  * center：居中
  * right：靠右


