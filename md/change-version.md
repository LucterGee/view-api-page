### 版本注意点

* 0.3.* -> 0.4.*及以上版本，需要新增page配置文件（view.config.js）,该配置可以在继承Page时，不用写构造方法，在继承Application中不用写构造方法
* 0.4.1及以上版本不需要在webpack.config.js中切换环境，只需执行不同的命令即可