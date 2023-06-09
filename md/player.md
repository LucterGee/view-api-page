## 播放器对接

* 框架提供了一个RealPlayer的空实现父类，需要在对接实际播放器时，继承并实现必要的方法

```javascript
/**
 * 对接播放器时，需要继承这个类，并重写所有方法
 */
export default class RealPlayer{
    constructor() {
        this.playInfo = null;
    }

    play(startTime, playInfo){

    }

    playByTime(time){

    }

    mute(flag){

    }

    pause(){}

    resume(){}

    stop(){}

    destroy(){}

    get position(){
        return 0;
    }

    get duration(){
        return 0;
    }

    get volume(){
        return 0;
    }

    set volume(value){
    }

    get isMute(){
        return false;
    }

}

```

* 选择播放器，在不同环境使用的实际播放器是不同的，所以需要配置：

MyApplication.js中实现

```javascript
export default class MyApplication extends Application {
    getPlayerInstance() {
        var player = {};
        try {
            player = new IptvPlayer();//盒子原生播放器
        } catch (e) {
            player = new AliWebPlayer();//开发调试功能时用的阿里web播放器
        }
        return player;
    }
}

```

#### 播放器调教

* 在View中已对播放器做了一定程度的调教，在绝大多数情况可以有较好的体验
* 如果确实需要调整，需要了解VideoPlayer的工作机制
* 在@src/util/AliWebPlayer是使用阿里h5播放器实现的，具体对接可以参考这个

