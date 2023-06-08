## LogView 打印控件

* 父类：RecycleView
* 每个Page都会自带一个打印控件
* 在开发、测试打包使用时，默认显示，在正式打包时，默认隐藏

#### 用法

在page中使用

```javascript
    this.i("显示绿色的提示信息");
    this.w("显示黄色的警告信息");
    this.e("显示红色的错误信息");
```

#### 注意点

* 必须在this.html = "";之后使用