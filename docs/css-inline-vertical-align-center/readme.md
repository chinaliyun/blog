<!-- Date: 2017-05-07 09:22 -->

# css 内联元素上下居中

如果需要多个内联元素上下居中，`vertical-align:center`要写在每一个内联元素的样式上，而不是写在他们的父级样式中,比如：

```html
<div>
    <span>1</span>
    <span>2</span>
    <span>3</span>
</div>
```

```css
div {
    span {
        vertiacl-alicn: center;
    }
}
```
