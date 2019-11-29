详细代码 —— `code\testFlex`

## 弹性布局

### 弹性容器

详细代码见 —— `code\demo\flex.html`

设置弹性容器的方式

```
display:flex
```

### 弹性盒子

当容器被指定为弹性容器后，里面的盒子就是弹性盒子。

1.弹性容器默认宽度为100%

2.弹性容器中的盒子不再独占一行，而是像float元素一样按一个方向排列

3.弹性盒子尺寸随容器大小变化

### flex属性

flex属性实际上是，flex-grow，flex-shrink，flex-basis三个属性的合集。

默认情况下，flex的值是，`flex:0 1 auto`

`flex:none` —— flex的值为none时，表示`flex: 0 0 auto`，这个盒子既不伸展也不收缩

`flex:auto` —— flex的值为auto时，表示`flex:1 1 auto` ，这个盒子既能伸展也能收缩

`flex:1` —— flex值为1时，表示`flex:1 1 0` ，容器内的盒子将平分空间

- #### flex-grow

详细代码见 —— `code\demo\flex-grow.html`

当一行内弹性盒子不能充满整行时，用这个属性去分配空闲空间。

当flex-grow为0，不占用空间

当flex-grow非0，对弹性盒子进行拉伸，即对剩下空白空间进行分配

```html
<!-- HTML -->
<div class="flex-box">
  <span class="box box1">1/3空白空间</span>
  <span class="box box2">0</span>
  <span class="box box3">2/3空白空间</span>
</div>
```

```css
//css
.flex-box {
    display: flex;
}

.flex-box>.box {
    width: 50px;
    height: 100px;
}

.flex-box>.box1 {
    flex-grow: 1;
    background: red;
}

.flex-box>.box2 {
    background: green;
}

.flex-box>.box3 {
    flex-grow: 2;
    background: yellow;
}
```

容器宽度300px，盒子每个宽度50px，剩下50px剩余空间。

box1的flex-grow设置为1，占据剩下1/3空白空间，同理box2占据剩下2/3空白空间。

- #### flex-shrink

详细代码见 —— `code\demo\flex-shrink.html`

```css
.flex-box {
    display: flex;
}

.flex-box>.box {
    width: 150px;
    height: 100px;
}

.flex-box>.box1 {
    flex-shrink: 1;
    background: red;
}

.flex-box>.box2 {
    flex-shrink: 0;
    background: green;
}

.flex-box>.box3 {
    flex-shrink: 2;
    background: yellow;
}
```

容器宽度300px，每个盒子宽度150px，超出50px，如果不设置flex-shrink，那么每个盒子宽度将变成100px。

设置flex-shrink以后，box2将不收缩，box1收缩超出部门的1/3，box3收缩超出部分的2/3。

- #### flex-basis

详细代码见 —— `code\demo\flex-basis.html`

flex-basis是用来指定盒子基准宽度的。

弹性布局中，盒子最终的宽度通常不是width指定的，所以flex-basis来指定宽度，flex-basis的属性优先级要高于width。无论使用什么样的选择器，只要两个属性同时作用在一个盒子上，都是以flex-basis为准。

```css
.flex-box {
    display: flex;
}

.flex-box>.box1 {
    flex-basis: 80px;
    background: red;
}

.flex-box>.box2 {
    flex-basis: 80px;
    background: green;
}

.flex-box>.box3 {
    flex-basis: 120px;
    background: yellow;
}

.flex-box>.box {
    width: 50px;
    height: 100px;
}
```

使用上面的样式之后，发现width并没有生效。

### flex-direction

默认值是row，改成column，盒子将在竖直方向排列

## demo

微信顶部导航，详见 `code\demo\flex_layout.html` ，`code\src\layout\header.css`

