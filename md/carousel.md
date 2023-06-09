## CarouselView 轮播

* 父类：RecycleView
* 较父类RecycleView来说，CarouselViews写死一些效果，新增了放大缩小

#### 写法

```html

<carousel style=" width: 1280px;height: 300px;overflow: hidden;" id="carousel"></carousel>
```

#### 标签属性

| index | name          | description | value             | comment                                |
|-------|---------------|-------------|-------------------|----------------------------------------|
| 1     | poster-size   | 大小          | width,height      | 例如：200,100 英文逗号，poster-white使用         |

#### 定制化

CarouselView的定制，其实就是对内部Poster的定制，这个可以参考Poster

```html

<carousel style=" width: 1280px;height: 300px;overflow: hidden;" poster-size="800,280" id="carousel_custom_poster">
    <poster-white id="poster"></poster-white>
</carousel>
```

<span style="color:red;">注：这里内部的id必须时poster</span>