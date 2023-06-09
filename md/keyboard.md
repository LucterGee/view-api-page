## Keyboard 键盘

* 父类：RevycleView
* 26个字母、0-9的10个数字

#### 写法

```html

<keyboard></keyboard>
```

#### 标签属性

| index | name        | description    | value             | comment         |
|-------|-------------|----------------|-------------------|-----------------|
| 1     | size-type   | 大小类型           | medium/small/mini | 默认small         |
| 2     | size        | 大小             | width,height      | 例如：200,100 英文逗号 |
| 3     | focus-color | 字母默认焦点/背景边框的颜色 |                   | 默认#de2910       |
| 4     | value-color | 字母文字颜色         |                   | 默认#dcdfe6       |

#### 定制化

keyboard的定制，其实就是对内部button的定制，这个可以参考button

```html

<keyboard>
    <button value-color="black" id="button">
        <div style="background: white;border-radius: 7px;" id="bg"></div>
    </button>
</keyboard>
```

<span style="color:red;">注：这里内部的id必须时button</span>