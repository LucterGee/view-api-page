## FrameView、Fragment 配合使用

* 父类都是：GroupView
* Fragment需要依赖FrameView

#### 写法

* Fragment
```html
    <button></button>

```

```javascript
export default class Fragment_0 extend Fragment{
    onCreate(){
        this.html = "<button></button>";//fragment 的布局
    }
}
```


* FrameView在Page中对应的代码片段
```html

<frame id="frame"></frame>
```

```javascript
    var frame = this.findViewById("frame");
    frame.addFragments([new Fragment_0(this.viewManager)]);
```


#### Fragment的html、css规则

* html：在/src/html路径下新建fragment文件夹，将html文件放在这个文件夹中
* css：在/src/css路径下新建fragment文件夹，将html文件放在这个文件夹中
* 如果一个app有多个FrameView对应的Fragment，可以在fragment文件夹下继续分类，但是必须保证<span style="color:red;">html和css的文件路径及文件名是对应的</span>


#### 注意点

* Fragment内部使用方式，介于Page和GroupView之间
* Fragment的生命周期依赖FrameView及Page
* 在当前版本之前，Fragment内部不能套用FrameView