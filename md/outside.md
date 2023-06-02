## 与外部交互

#### 进入app

获取信息（设备型号、盒子账号等）
* 参数在地址栏中，view会自动解析，调用app.urlParam获取
* 从关键字中获取
  * 与Android交互，使用Android提供的关键字+具体的调用获取
  * 从Authentication中获取，这种方式是iptv的规范，一般都有对应文档
* 保存返回地址，如果退出app时需要

#### 跳转到外部

返回时会自动跳转到原来页面

* 跳到其他应用（专区）
* 跳转到订购页

示例

```javascript

var onClickListener = function (view) {
    var url = "http://kanchenai.gitee.io/launcher_page";
    url += "?backUrl=" + encodeURIComponent(location.href);

    this.application.gotoOutside(url);
}
```

#### 正常退出

* 使用进入时保存的返回地址
* 默认返回地址
* 默认的退出方法

示例

```javascript
export default class MyApplication extends Application {
    onDestroy() {
        // console.log("MyApplication onDestroy")
        // 如果是app+epg，在这里（或exitUrl()）调用退出app的方法
    }

    exitUrl() {
        var url = this.urlParam.backUrl;
        if (!url) {//如果在地址栏中没有返回地址
            url = LocalData.getData("backUrl");//取保存的
        }

        if (!url || url == "undefined") {//如果都没有
            url = "";//默认的地址
        }
        return url;
    }
}

```