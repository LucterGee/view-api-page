#### 0.1.0 基本功能

* 在该版本中，基本功能已完成，对于实际开发基本满足要求，部分功能可以在简单变形之后实现
* 开始积累special_view，和业务结合较为紧密的控件，新的属性也需要支持标签
* 虚拟节点优化，在后续版本中需要调研，得到对性能提升程度

#### 0.1.1 findViewById改写，控件向内部迭代到有id对应的控件

* 把控件绑定在viewManager的map中，不利于控件的特殊操作

#### 0.2.0 拓展组件-可循环列表RecycleView

* 节点可循环使用
* 滚动效果循环

#### 0.2.1 dialog组件布局分离，规范组件的自定义布局形式,并完善已知问题（缺陷）

* 将布局文件等同于page
* css和html文件可以使用文件夹区分，在loader中处理
* 尝试将html和css写在一个文件中，更加清晰的关联布局和样式
* RecycleView默认设置adapter，加载标签属性，默认上焦，focusable也需要加入
* 新增气泡控件，是否可以看作自动消失的dialog

#### 0.2.2 完善各个组件标签属性

* 除了基础属性之外的属性还没有写
* GroupView、RecycleView等

#### 0.2.3 替换Map类，及修复一些问题

* 将Map替换为VMap（自定义类），避免出现Map不适配
* 修复0.2.2中属性获取配置后设置错误

#### 0.2.4 将播放器耦合进Page/Fragment中

* 不同Page或Fragment的Player对应的监听所在位置是不同的，需要触发各自的事件

#### 0.2.5 解决初始焦点问题

* 在使用fragment时，初始焦点在fragment中，需要在业务层特殊处理
* 当应用跳转到外部返回时，使用page的param获取焦点id，恢复

#### 0.3.0 拓展组件-Toast组件

* 继承可以自定义，任意地方可调用、显示位置
* 时间可设定
* 样式可调整（可使用template布局）
* 并开始支持只带布局的组件

#### 0.3.1 html loader优化

* 解析tagName，将tagName解析到属性中的view-type
* 解析id，将id解析到属性中view-id
* 可以使用buildView方法和loader结合的方式

#### 0.3.2 盒子兼容

* 引入@babel/polyfill，兼容新api在编译过程中无法处理
* 优化打包，在打包之前，删除老的文件，并且不使用箭头函数

#### 0.4.0 页面配置

* 在view.config.js中配置及注册页面

```javascript
  /**
   * 定义PageName对应的Page，舍去在Page子类中赋值pageName步骤
   */
  export var PageConfig = {
            "HomePage": HomePage,
            "ListPage": ListPage,
            "FramePage": FramePage,
            "TestPage": TestPage,
            "PlayerPage": PlayerPage
          }
  
  /**
   * 默认的page
   * 当未获取到第一个页面时，会使用该页面
   * @type {string}
   */
  export var LaunchPage = "HomePage";
```

#### 0.4.1 优化运行及打包配置

* 在打包中不需要切换运行环境，只需执行不同的命令即可
    * 开发换进
  ```
  npm run build-dev
  ```
    * 生产环境
  ```
  npm run build
  或
  npm run start
  或
  npm run build-pro
  ```

* 自动识别package.json中的name作为页面标题
* 配置标题icon，在打包中也会带着，路径为./public/logo.png

#### 0.5.0 拓展播放器-Android、Web播放器，
使用控件位置来决定播放器位置及宽高

* 对接Android播放器，使用特定关键字调用相关播放方法，实现Android原生和H5交互
* 对接Web播放器(阿里h5播放器)
* 将iptv播放器起到框架之外
* 使用自定义控件形式在业务层添加

#### 0.5.1 自定义控件开发模式

* 形成自定义控件开发模式

#### 0.5.2 将PlayerView移入框架

* PlayerView作为比较通用的控件，属于框架级别的
* 内部的播放器的对接由业务层处理

#### 0.6.0 添加小组件

* 信息打印小组件
    * 绑定在page中，直接使用方法打印
    * npm run build:正式打包时,默认隐藏
    * npm run build-dev:开发打包时，默认显示
  ```javascript
     var mode = process.env.NODE_ENV || "production";//获取当前的模式,development:开发模式；production：生产模式
  ```

#### 0.6.1 优化控件获取节点属性

* 单独布局的设置布局中，需要转化自定义控件的tagName、id，改变html（adapter、LoneDialog）
* 优化RecycleView的margin功能

#### 0.6.2 自定义小组件

使用自定义组件方式，提供一些常用的固定场景的控件。由于场景固定但风格不同，所以在业务曾添加

#### 0.6.3 View新增props变量

* 根据props中的变量名，获取节点中对应属性的值，在基类View中调用
* 在子类中添加子类需要的属性
* 通过this.props["@{key值}"]获取

#### 0.6.4 再新增一些自定义组件

* 海报：不同样式的
* 按钮
* 完善控件demo

#### 0.6.5 进入app时，根据情况返回之前页面

* 存在异常退出app，cookie中保留了一些page信息，导致重新进入app时默认回到page
* 在外部进入app时，往往都是指定页面，所以需要根据实际情况来判断

#### 0.6.6 在page中集成一个toast

* 类似LogView,在每个Page实例中自带一个Toast