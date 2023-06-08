## TextView 文字

* 父类：View
* 这个组件主要是为了跑马灯

#### 写法

```html

<text id="text"></text>
```

#### 属性

| index | name | description | value | comment          |
|-------|------|-------------|-------|------------------|
| 1     | text | 改变跑马灯文字     |       | 原本需要跑马灯，改变之后依旧执行 |

#### 方法

| index | name         | description |
|-------|--------------|-------------|
| 1     | marquee      | 执行跑马灯       |
| 2     | clearMarquee | 取消跑马灯       |

#### 注意

* style中的white-space
  * nowrap 强制单行，横向跑马灯
  * 其他：可能多行，执行纵向跑马灯
* 默认设置overflow：hidden
* 默认设置lineHeight为height