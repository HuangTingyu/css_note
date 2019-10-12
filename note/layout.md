### body样式

```css
body{
    max-width: 640px;
    margin: 0 auto;
    background: #f8f8f8;
    overflow-x: hidden;
    -webkit-overflow-scrolling: touch;
}
```

- max-width:640px

  设置body最宽只能640px，这是为了在一些超宽的屏幕(如：横屏的ipad)，页面不至于被撑得太宽。当屏幕像素大于640px的时候，也只能显示到640px

- margin: 0 auto

  当屏幕超宽的时候，保证内容区能水平居中

- overflow-x:hidden

  横轴方向如果出现了超宽的元素，设为隐藏，防止x轴方向出现滚动条

- -webkit-overflow-scolling:touch

  ios系统上，可以让滚动元素有弹性，滚动更顺滑。只对webkit内核的浏览器生效。

## dom结构

顶部+尾部

```html
<!-- html -->
<div class="bacra-header">标题栏</div>
<div class="bacra-navbar">导航栏</div>
```

```css
// css
.bacra-header {
    position: fixed;
    box-sizing: border-box;
    width: 100%;
    max-width: 640px;
    height: 2.3rem;
    top: 0;
    z-index: 200;
    border-bottom: 1px solid #ddd;
}

.bacra-navbar {
    position: fixed;
    box-sizing: border-box;
    bottom: 0;
    width: 100%;
    max-width: 640px;
    height: 2.5rem;
    border-top: 1px solid #ddd;
    z-index: 200;
}
```

内容部分

```html
<!-- html -->
<div class="bacra-content">内容区</div>
```

```css
// css
.bacra-content {
    box-sizing: border-box;
    position: relative;
    overflow-y: auto;
}


/* 根据header和navbar自动适应内容区高度 */

.bacra-header~.bacra-content {
    padding-top: 2.3rem;
}

.bacra-navbar~.bacra-content {
    padding-bottom: 2.5rem;
}
```

- overflow-y: auto;内容超出高度，自动出现滚动条
- padding-top，padding-bottom，只有当标题和底部导航显示的时候，内容区会有padding。否则，就不显示padding