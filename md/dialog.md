## Dialog 弹窗

* 父类：GroupView
* 显示之后，返回默认关闭，焦点回到原来显示之前的焦点

#### 写法

* 布局集成在html中

布局中
```html

<dialog id="dialog">
    <button value="按钮"></button>
</dialog>
```

在Page或Fragment中
```javascript
    var dialog = this.findViewById("dialog");
    dialog.show();//显示弹窗
```

* 独立布局的弹窗
    * 默认全屏的

在ExitDialog.js
```javascript
export default class ExitDialog extends LoneDialog {
    constructor(viewManager) {
        super(viewManager);
        this.html = require("@html/dialog/exit_dialog.html");
    }
}
```

在Page或Fragment中
```javascript
    var dialog = new ExitDialog(this.viewManager);
    dialog.show();//显示弹窗
```

exit_dialog.html的代码
```html

<template>
    <div class="contain">
        <div class="title">是否确认</div>
        <div class="item" style="top: 180px;left: 80px;" view-type="item" id="confirm">确认</div>
        <div class="item" style="top: 180px;left: 250px;" view-type="item" id="cancel">取消</div>
    </div>
</template>    
```

#### 方法

| index | name | description |
|-------|------|-------------|
| 1     | show | 显示弹窗        |
| 2     | hide | 隐藏弹窗        |

#### 独立布局Dialog的html、css规则

* html：在/src/html路径下新建fragment文件夹，将html文件放在这个文件夹中
* css：在/src/css路径下新建fragment文件夹，将html文件放在这个文件夹中
* 独立布局Dialog可以在多个Page或Fragment中使用，耦合较低