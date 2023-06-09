## 扩展控件

* 根据业务定制相关功能的控件，比如ItemView可以扩展为按钮、海报（可点击的）
  * 按钮：带有样式、焦点、图标的可点击的控件
  * 海报：带有内容图片，内容名的可点击控件

## html编译

#### 使用控件

* id与基础控件一起被编译
* view-type
  * 由于view-type未定义在view loader中，所以view-type的转化在设置html时转化


示例

编码部分

```html
    <button id="button"></button>
```

编译之后的
```html
    <button view-id="view"></button>
```

设置html，转化之后的
```html
    <div view-type="button" view-id="button"></div>
```


#### 编写控件

扩展控件编写时，规则略有不同
* html文件中
  * id、基础控件的view-type在编译时转化
  * 扩展控件的view-type在设置html时转化
* js文件中
  * 扩展控件的view-type在设置html时转化
  * 基础控件的view-type不会转化，只能写成编译后的形式
  * id不会转化，只能写成编译后的形式


## 编写扩展控件的模式

例如需要创建<span style="color:red;">Button</span>扩展控件

* 1.在/src/custom-view文件夹中创建Button文件夹
* 2.在/src/custom-viewButton/下创建Button.js
```javascript
export default class Button extends ItemView{
    //...
    //其他功能性代码省略
    //...

  static parseByEle(ele, viewManager, listenerLocation) {
    var button = new Button(viewManager, listenerLocation);
    button.ele = ele;
    return button;
  }
}
```

* 3.在Button.js中定义一个继承ViewBuilder的class
```javascript
export class ButtonBuilder extends ViewBuilder {
  constructor() {
    super();
    this.viewType = "button";
  }

  buildView(ele, viewManager, listenerLocation) {
    return Button.parseByEle(ele, viewManager, listenerLocation);
  }
}
```

* 4.在main.js的application.launch()方法执行之前调用
```javascript
window.onload = function () {
  ViewManager.addCustomViewBuilder([ButtonBuilder]);//ButtonBuilder为对应的扩展控件

  //...
  //其他代码省略
  //...
}
```

## 其他

```javascript
export default class Button extends ItemView {
    constructor(viewManager, listenerLocation) {
        super(viewManager, listenerLocation);
        
        //Button特有的标签属性
        this.props.concat({
            "value": "",//Button的文字
          //...
          //其他标签名代码省略
          //...
        })
    }

  setAttributeParam() {
    var firstFocus = super.setAttributeParam();//必须在第一行调用
    //读取并设置Button的标签属性
    var sizeType = this.props["size-type"];
    if (!sizeType) {
      sizeType = "small";
    }

    this.sizeType = sizeType;

    //...
    //其他设置代码省略
    //...

    return firstFocus;
  }

}
```