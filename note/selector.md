详细代码见 —— `code\demo\selector.html`

## 选择器

快速创建html结构 —— `html:5`

### 属性选择器

- #### 属性选择器用 `[]` 

  带有href属性的标签

```css
a[href]{
  color:red;
}
```

- #### `[attr=xxx]` 

  选择有attr属性且属性等于xxx的元素

```css
<!-- HTML： -->
<input type="text" value="大花碗里扣个大花活蛤蟆"/>

// CSS：
input[type=text]{
    color: red;
}
```

注意xxx和html中属性的值必须一致，下面的例子是不能选中input标签的

```css
<!-- HTML： -->
<input class="input text" type="text" value="大花碗里扣个大花活蛤蟆"/>

// CSS：
input[class=input]{
    color: red;
}
```

要选中该input标签的话，

1.第一种改法——

```css
input[class="input text"] {
    color: red;
}
```

- #### `[attr~=xxx]` 

  只要有一个属性值相等就可以

2.第二种改法——

```css
input[class~="text"] {
  color: red;
}
```

- #### `[attr|=xxx]`

  选择属性值为xxx，或者以xxx开头的元素

```css
<!-- HTML： -->
<div class="bacra">我是bacra</div>
<div class="bacra-title">我是bacra-title</div>
<div class="bacra-content">我是bacra-content</div>
<div class="sakura_footer">我是sakura_footer，不是以bacra开头的</div>

// CSS：
div[class|=bacra] {
   color: red;
}
```

- #### `[attr^=xxx]`

  匹配属性以xxx开头的元素

- #### `[attr$=xxx]`

  匹配属性以xxx结尾的元素

- #### `[attr*=xxx]`

  匹配属性值中包含xxx的元素



