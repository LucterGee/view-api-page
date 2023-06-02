## Application详解

app的特定处理，需要新建一个继承Application的子类，并在main.js中代替Application启动

#### 生命周期

* onLaunch
* onCreate
* onStop
* onDestroy

#### onLaunch 启动

* app的第一个阶段
* 一般用于对地址栏的参数进行相应的处理
    * 决定第一个页面
    * 处理外部参数，全局保存
    * 定义第一个页面的参数

示例

```javascript
export default class MyApplication extends Application {
    onLaunch(urlParam) {
        console.log("onLaunch，地址栏参数：", urlParam);//外部在地址栏中传递的参数
        var firstPage = null;
        var param = null;//这个是传递给第一个Page的参数
        switch (urlParam.pageKey) {//根据参数中的规定key对应的值选择哪个Page是第一个Page
            case "home":
                // firstPage = new HomePage();
                firstPage = "HomePage";//对应view.config.js中的页面，两种形式都是可以的，但建议使用这种
                break;
        }
        return {firstPage, param};//返回第一个Page，及对应的参数
    }
}

```

#### onCreate 创建

* 启动第一个page之前调用

示例

```javascript
export default class MyApplication extends Application {
    //应用创建，启动第一个页面之前调用
    onCreate(page, param) {//page为第一个Page，param为对应的参数
    }
}

```

#### onStop 停止

* 在跳转到外部，和销毁应用时调用
* 一些对应的处理可以在这里执行

示例

```javascript
export default class MyApplication extends Application {
    //应用停止，一般在跳转到外部，和销毁应用时调用
    onStop() {
    }
}

```

#### onDestroy 销毁

* 跳转到外部不会调用该方法，只有销毁时会调用
* 如果是android混合模式，可以在这里调用关闭WebView或关闭android app

示例

```javascript
export default class MyApplication extends Application {
    //应用停止，一般在跳转到外部，和销毁应用时调用
    onDestroy() {
    }
}
```  

#### 设置返回地址

* 一般在正常推出app时，跳转到设置的返回地址

示例

```javascript
export default class MyApplication extends Application {
  //如果是android混合模式，也可以在这里调用关闭WebView或关闭android app
  exitUrl() {
    var url = "";//退出应用跳转的地址，这地址可以自定义，一般由启动应用时，地址栏中的参数，比如：backUrl、returnUrl等
    return url;
  }
}
```

#### 全局播放器设置

* 一般情况一个盒子在同一时间只能使用一个播放器，所以这个播放器实例在全局通用
* 在不同的运行环境，可调用的播放器是不同的，可以根据环境来设置

示例

```javascript
export default class MyApplication extends Application {
  getPlayerInstance() {
    var player = {};
    try{
      player = new IptvPlayer();//iptv的播放器
    }catch (e){
      //其他播放器创建
      player = new AliWebPlayer();//阿里web播放器
    }
    return player;
  }
}
```

#### 进入app的模式

默认情况，app会根据cookie中保存的信息自行判断使用那种模式进入，但在一些特殊请款下，cookie中的数据未被正常处理
* 直接关闭盒子
* 按home键，返回盒子首页
* 异常退出

在没有特殊需求下，重新进入app，会返回退出的页面，但在外部跳转到具体目标页面时，需要忽略cookie中的记录

示例

```javascript
export default class MyApplication extends Application {
  /**
   * 
   * @param param
   * @returns {boolean} true:以Enter模式进入；false：根据情况获取进入模式
   */
    forceEnter(param) {
        var flag = false;
        if (param.enter) {//当参数中key为enter有值时，以具体情况为准
            flag = true;
        }
        return flag;
    }
}


```