## 简介

* 在原生js基础上开发的针对EPG的交互框架
* 参考了android的Application和activity实现整个页面的交互及生命周期
* 使用webpack打包
* 在线地址：http://kanchenai.gitee.io/view_page

## 起步

## View的使用

#### 创建一个简单的页面：

一个包含两个按钮,可以相会切换并点击的页面

* 在page路径下创建一个js文件，用require方法引入page布局
/src/page/HomePage.js
```javascript
export default class HomePage extends Page{
    onCreate(param){
        this.html = require("../html/home.html");
    }
}
```

* 在html路径下创建一个html文件，在这个文件中编写布局
/src/html/home.html
```html
<template>
    <button first-focus></button>
    <button style="left: 130px;"></button>
</template>
```

* 在配置中添加这个page
/view.config.js
```javascript
  /**
   * 定义PageName对应的Page，舍去在Page子类中赋值pageName步骤
   */
  export var PageConfig = {
            "HomePage": HomePage,
          }
  
  /**
   * 默认的page
   * @type {string}
   */
  export var LaunchPage = "HomePage";
```


以上代码展示了一个页面所需的文件及配置：
* HomePage.js中将布局文件引入，并且在这个文件中编写交互动作
* home.html包含了当前页面的布局
* 在view.config.js中配置page，提供给框架调用

#### Application的简介

* application会识别view.config.js中page，默认启动LaunchPage对应的page

* 使用自定义的application

继承Application
```javascript
export default class MyApplication extends Application {
    
}
```

在main.js中调用

```javascript
window.onload = function () {
    var application = new MyApplication("app");
    application.launch();
}
```

#### 控件的简介

* 在htm文件中使用，以下是一个可上焦的基础控件
```html
<item class="item"></item>
```

* view还提供了自定义控件的开发

## 特点

* view为我们提供了page跳转的基础，我们只需要在简单的配置后，将精力聚焦在page的业务、数据的传递
* 在webpack的基础上，实现单页面效果，page之间的跳转在同一url中实现，节省切换url时文件加载的时间
* 由于所有page都是在同一个application中执行，所有的page可以调用到相同的application，
所以可以将全局动作在application中执行，全局信息在application中保存
* view还提供了一些基础的控件，方便大家使用