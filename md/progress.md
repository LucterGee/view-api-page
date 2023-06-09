## Progress 进度条

* 父类：GroupView
* 不可上焦

#### 写法

```html

<progress style="width: 1000px;height: 15px;top: 60px;" id="progress"></progress>
```

#### 标签属性

| index | name            | description | value | comment   |
|-------|-----------------|-------------|-------|-----------|
| 1     | total           | 总进度值        | 最小5   | 默认100     |
| 2     | progress-color  | 进度条颜色       |       | 默认#de2910 |
| 3     | bg-color        | 进度条背景颜色     |       | 默认gray    |
| 4     | point-color     | 进度条上的圆点颜色   |       | 默认#ffde00 |
| 5     | progress-change | 进度条变化监听     |       |           |

#### 定制化

* 定制背景

在progress中定义一个<span style="color:red;">id为bg</span>的子节点，这个子节点会替代默认的背景

示例
```html

<progress style="width: 1000px;height: 15px;top: 60px;">
    <div style="background: white;border-radius: 7px;" id="bg"></div>
</progress>
```

* 定制进度

在progress中定义一个<span style="color:red;">id为progress_bg</span>的子节点，这个子节点会替代默认的进度

示例
```html

<progress style="width: 1000px;height: 15px;top: 60px;">
    <img style="border-radius: 7px;" src="../images/progress_bg.png" id="progress_bg">
</progress>
```

* 定制圆点

在progress中定义一个<span style="color:red;">id为point</span>的子节点，这个子节点会替代默认的圆点

示例
```html

<progress style="width: 1000px;height: 15px;top: 60px;">
    <div style="background: #409eff;" id="point"></div>
</progress>
```