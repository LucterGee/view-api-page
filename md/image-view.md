## ImageView 图片

* 父类：View
* 识别img标签
* 自带懒加载

#### 写法

与原生的img写法相同

```html
<img src="../../a.png" id="img">
```

#### 图片动态设置

```javascript
    var image = this.findViewById("img");//获取到ImageView控件
img.src = "../../a.png";//使用ImageView的src设置图片，会触发懒加载

var image = this.findEleById("img");//获取到ImageView的节点
img.src = "../../a.png";//节点的src设置图片，不会触发懒加载
```

#### 标签属性

| index | name      | description | value                 | comment |
|-------|-----------|-------------|-----------------------|---------|
| 1     | view-lazy | 是否使用懒加载     | true/1:是<br>false/0:否 | 默认是     |