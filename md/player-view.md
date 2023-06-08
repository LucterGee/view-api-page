## PlayerView

* 父类：View
* 内置一个播放器
* 通过在Application子类中选择真实的播放器来调用

#### 写法

```html

<player id="player"></player>
```

#### 监听

| index | name                     | description |
|-------|--------------------------|-------------|
| 1     | onPositionChangeListener | 进度变化监听      |
| 2     | onVolumeChangeListener   | 音量变化监听      |
| 3     | onPlayStart              | 播放开始监听      |
| 4     | onPlayComplete           | 完成播放监听      |
| 5     | onPlayPause              | 暂停播放监听      |
| 6     | onPlayResume             | 继续播放监听      |
| 7     | onPlayStop               | 停止播放监听      |
| 8     | onPlayError              | 播放异常监听      |
| 9     | onPlayByTime             | 断点播放监听      |

#### 属性

| index | name            | description | value | comment |
|-------|-----------------|-------------|-------|---------|
| 1     | isPlaying       | 是否在播放       |       |         |
| 2     | currentPosition | 当前播放进度      |       | 只读      |
| 3     | duration        | 当前视频总时长     |       | 只读      |

#### 方法

| index | name       | description |
|-------|------------|-------------|
| 1     | play       | 播放          |
| 2     | replay     | 重新播放        |
| 3     | playByTime | 断点播放        |
| 4     | pause      | 暂停          |
| 5     | resume     | 继续          |
| 6     | stop       | 停止          |
| 7     | destroy    | 销毁          |


#### 注意点

* destroy只在离开app时调用
* Page跳转或Fragment切换时，自动暂停，回来时，自动继续，除非主动stop
* 对应节点的宽高为播放窗口的默认宽高
* 对应播放相关的监听默认调用page或fragment中定义的
* 音量调节默认使用音量按键触发，不需要调用方法
