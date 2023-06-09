## CountdownView 倒计时

* 父类：View

示例

```html

<countdown></countdown>
```

#### 标签属性

| index | name         | description | value             | comment         |
|-------|--------------|-------------|-------------------|-----------------|
| 1     | size-type    | 大小类型        | medium/small/mini | 默认small         |
| 2     | size         | 大小          | width,height      | 例如：200,100 英文逗号 |
| 3     | count        | 倒数开始的数字     |                   | 默认3             |
| 4     | count-change | 倒数监听        |                   |                 |

#### 方法

| index | name  | description |
|-------|-------|-------------|
| 1     | start | 开始倒数        |
| 2     | stop  | 停止          |

#### 定制化

* 定制背景

在countdown中定义一个<span style="color:red;">id为bg</span>的子节点，这个子节点会替代默认的背景

示例

```html

<countdown style="color:black;">
    <div style="background: white;border-radius: 25px;" id="bg"></div>
</countdown>
```

