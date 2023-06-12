## Poster 可点击海报

* 父类：ItemView
* 和ItemView区别
    * 主要偏向展现内容功能
    * 控件风格以海报形式
    * 方法及功能与ItemView基本一致
* 根据风格，可以区分为:
    * Poster
    * PosterWhite
    * PosterShadow
    * 待扩展...

#### 写法

````html

<poster id="poster"></poster>
<poster-white id="poster_1"></poster-white>
<poster-shadow id="poster_2"></poster-shadow>
````

#### 标签属性

| index | name          | description | value             | comment                                |
|-------|---------------|-------------|-------------------|----------------------------------------|
| 1     | size-type     | 大小类型        | medium/small/mini | 默认small                                |
| 2     | size          | 大小          | width,height      | 例如：200,100 英文逗号,poster、poster-shadow使用 |
| 3     | poster-size   | 大小          | width,height      | 例如：200,100 英文逗号，poster-white使用         |
| 4     | focus-enlarge | 上焦后放大比      |                   | 默认100                                  |

注：size、poster-size都是指海报大小，不同的是，poster和poster-shadow只有海报，海报大小即控件大小，poster-white还有文字；所以：
  * poster和poster-shadow：size
  * poster-white：poster-size


#### 定制化

* 定制焦点

在poster中定义一个<span style="color:red;">id为focus</span>的子节点，这个子节点会替代默认的焦点

示例
```html

<poster id="poster">
  <img src="../images/focus/176x277.png" width="214" height="305" id="focus">
</poster>

<poster-white id="poster_1">
  <img src="../images/focus/176x277.png" width="214" height="305" id="focus">
</poster-white>

<poster-shadow id="poster_2">
  <img src="../images/focus/176x277.png" width="214" height="305" id="focus">
</poster-shadow>
```

注：这里id为focus的节点，需要设置固定宽高，这个<span style="color:red;">宽高会设置到poster中</span>，poster的图片、文字宽高不变，但会<span style="color:red;">居中</span>

* 定制文字

在poster中定义一个<span style="color:red;">id为name</span>的子节点，这个子节点会替代默认的文字

示例
```html
<poster-white id="poster_1">
  <text style="color:red;" id="name"></text>
</poster-white>

<poster-shadow id="poster_2">
  <text style="color:red;" id="name"></text>
</poster-shadow>
```

注：这里id为name的节点，width、height、line-height会被内部覆盖，其他属性生效