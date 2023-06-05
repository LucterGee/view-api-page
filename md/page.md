## Page详解

#### 生命周期

* onCreate
* onResume
* onPause
* onStop
* onDestroy

#### onCreate 创建

* page的第一个阶段
* 设置page
  * 设置布局
  * page中的控件初始化
  * 获取page数据，并设置到控件中

示例

```javascript
export default class HomePage extends Page {
    //内部没有内容，需要在这个方法中调用this.html = "";设置布局
    onCreate(param){//param是传入的参数，param由application或上一个Page组装
        this.html = "<div></div>";//这里的html一般由import引入
    }
}
```

#### onResume 页面继续

* 创建page或返回page后的阶段
* 不同场景下，触发的onResume，需要不同的操作

示例

```javascript
export default class HomePage extends Page {
  //Page执行到前台，页面已显示
  //1.从创建之后到前台
  //2.从其他Page返回当前Page
  onResume(){}
}
```

#### onPause 页面暂停

* 跳转到其他页面之前调用
* 页面停止之前先暂停，所以停止之前也会调用
* 保存当前页面的一些数据在这里执行
  * 异常退出app时，不会调用onPause之后的动作，所以需要在这里保存

示例

```javascript
export default class HomePage extends Page {
    //Page执行进入后台状态，页面已隐藏
    //跳转到其他页面时，有两种状态
    //1.当前页面暂停
    //2.当前页面关闭，紧接着会调用停止方法
    onPause() {
        //一般播放暂停在这里调用
        //保存页面数据
      this.saveParam({});
    }
}
```

#### onStop 页面停止

* 正常finish page之前调用
* 跳转到外部链接之前调用
* 正常退出app之前页面调用stop，所以退出app之前也会调用

示例

```javascript
export default class HomePage extends Page {
  //Page执行到停止
  onStop(){
    
  }
}
```

#### onDestroy 页面销毁

* 正常finish page之前调用

示例

```javascript
export default class HomePage extends Page {
  onDestroy(){
    
  }
}
```

#### Page之间的数据传递

* 跳转到新的Page

示例

```javascript
export default class HomePage extends Page {
  //页面默认的点击监听
  onClickListener(view) {
    var listPage = new ListPage();//ListPage是另一个Page
    this.startPage(listPage, {data: "llllll"});//第二个参数是传递到ListPage的数据
  }
}
  
export default class ListPage extends Page {
  onCreate(param){//由HomePage中传递的数据 {data: "llllll"}
    
  }
}
```

* 返回到上一个页面

示例

```javascript
export default class ListPage extends Page {
  //重写返回键
  key_back_event() {
    this.setResult({data: "来自ListPage的数据"});
    this.finish();//回到上一个Page（HomePage）
  }
}
	
export default class HomePage extends Page {
  onResult(backResultData){//由ListPage回传的数据，{data: "来自ListPage的数据"}
    
  }
}
  
```

#### 获取对应的控件、节点


* 获取对应控件，使用findViewById方法
  * findViewById的参数id，对应必须是控件
* 获取对应节点，使用findEleById方法

示例

home.html
```html
<template>
    <div class="bg"><img id="bg"></div>
    <button class="button" id="button"></button>
</template>
```

```javascript
export default class HomePage extends Page {
    onCreate() {
        this.html = require("home.html")

        this.button = this.findViewById("button");
        this.imageView = this.findViewById("bg");//获取的是ImageView对象
        this.imageEle = this.findEleById("bg");//获取的是节点
    }
}
```




