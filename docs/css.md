CSS 备忘清单
===

这是一份关于 CSS 优点的快速参考备忘单，列出了选择器语法、属性、单位和其他有用的信息

入门
------------

### 介绍
<!--rehype:wrap-class=row-span-3-->

CSS 功能丰富，不仅仅是布局页面

#### 外部样式表

```html
<link
  href="./path/to/stylesheet/style.css"
  rel="stylesheet"
  type="text/css"
>
```
<!--rehype:className=wrap-text -->

#### 内部样式表

```html
<style>
  body {
    background-color: linen;
  }
</style>
```

#### 内联样式

```html
<h2 style="text-align: center;">
  居中文本
</h2>
<p style="color: blue; font-size: 18px;">
  蓝色，18像素文本
</p>
```
<!--rehype:className=wrap-text -->

### 添加 class 类

```html
<div class="classname"></div>
<div class="class1 ... classn"></div>
```

支持一个元素上的多个类

### !important

```css
.post-title {
    color: blue !important;
}
```

覆盖所有以前的样式规则

### 选择器

```css
h1 { } 
#job-title { }
div.hero { }
div > p { }
```

查看: [CSS 选择器](#css-选择器)

### 文本颜色

```css
color: #2a2aff;
color: green;
color: rgb(34, 12, 64, 0.6);
color: hsla(30 100% 50% / 0.6);
```

查看: [Colors](#css-颜色)

### 背景

```css
background-color: blue;
background-image: url("nyan-cat.gif");
background-image: url("../image.png");
```

查看: [Backgrounds](#css-背景)

### 字体

```css
.page-title {
  font-weight: bold;
  font-size: 30px;
  font-family: "Courier New";
}
```

查看: [Fonts](#css-字体)

### 定位

```css
.box {
  position: relative;
  top: 20px;
  left: 20px;
}
```

另见: [Position](https://learn-the-web.algonquindesign.ca/topics/css-layout-cheat-sheet/)

### 动画

```css
animation: 300ms linear 0s infinite;
animation: bounce 300ms linear infinite;
```

查看: [Animation](#css-动画)

### 注释

```css
/* 这是一行注释 */
/* 这是
   多行注释 */
```

### Flex 布局

```css
div {
  display: flex;
  justify-content: center;
}
div {
  display: flex;
  justify-content: flex-start;
}
```

查看: [Flexbox](#css-flexbox) | [Flex Tricks](#css-flexbox-tricks)

### Grid 布局

```css
#container {
  display: grid;
  grid: repeat(2, 60px) / auto-flow 80px;
}
#container > div {
  background-color: #8ca0ff;
  width: 50px;
  height: 50px;
}
```

查看: [Grid Layout](#css-grid-layout)

### 变量和计数器

```css
counter-set: subsection;
counter-increment: subsection;
counter-reset: subsection 0;
:root {
  --bg-color: brown;
}
element {
  background-color: var(--bg-color);
}
```

查看: [动态内容](#css-动态内容)

CSS 选择器
-----------

### 示例
<!--rehype:wrap-class=row-span-2-->

#### 组选择器

```css
h1, h2 {
    color: red;
}
```

#### 链选择器

```css
h3.section-heading {
    color: blue;
}
```

#### 属性选择器

```css
div[attribute="SomeValue"] {
    background-color: red;
}
```

#### 第一个子选择器

```css
p:first-child {
    font-weight: bold;
}
```

#### 无子选择器

```css
.box:empty {
  background: lime;
  height: 80px;
  width: 80px;
}
```

### 基础

选择器 | 说明
:- | :-
`*`          | 所有元素
`div`        | 所有 div 标签
`.classname` | 具有类的所有元素
`#idname`    | 带 ID 的元素
`div,p`      | 所有 div 和段落
`#idname *`  | #idname 中的所有元素

另见: [元素](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Type_selectors) / [类](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Class_selectors) / [ID](https://developer.mozilla.org/zh-CN/docs/Web/CSS/ID_selectors) / [通配](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Universal_selectors) 选择器


### 组合器

选择器 | 说明
:- | :-
`div.classname` | 具有特定类名的 div
`div#idname`    | 具有特定 ID 的 div
`div p`         | div 中的段落
`div > p`       | div 子节点中的所有 `P` 标签
`div + p`       | div 之后的 `P` 标签
`div ~ p`       | div 前面的 `P` 标签

另见: [相邻兄弟](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Adjacent_sibling_combinator) / [通用兄弟](https://developer.mozilla.org/zh-CN/docs/Web/CSS/General_sibling_combinator) / [子](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Child_combinator) 选择器

### 属性选择器

选择器 | 说明
:- | :-
`a[target]`          | 带有 <yel>target</yel> 属性 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Attribute_selectors#attr)
`a[target="_blank"]` | 在新标签中打开 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Attribute_selectors#attrvalue)
`a[href^="/index"]`  | 以 <yel>/index</yel> 开头 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Attribute_selectors#attrvalue_4)
`[class\|="chair"]`   | 以<yel>chair</yel>开头 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Attribute_selectors#attrvalue_3)
`[class*="chair"]`   | 包含<yel>chair</yel> [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Attribute_selectors#attrvalue_6)
`[title~="chair"]`   | 包含单词 <yel>chair</yel> [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Attribute_selectors#attrvalue_2)
`a[href$=".doc"]`    | 以 <yel>.doc</yel> 结尾 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Attribute_selectors#attrvalue_5)
`[type="button"]`    | 指定类型 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Attribute_selectors#attrvalue)

另见: [属性选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Attribute_selectors)

### 用户操作伪类

选择器 | 说明
:- | :-
`a:link    ` | 链接正常 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:link)
`a:active  ` | 链接处于点击状态 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:active)
`a:hover   ` | 鼠标悬停链接 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:hover)
`a:visited ` | 访问链接 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:visited)

---

```css
/* 未访问链接 */
a:link { color: blue; }        
/* 已访问链接 */
a:visited { color: purple; }   
/* 用户鼠标悬停 */
a:hover { background: yellow; }
/* 激活链接 */
a:active { color: red; }       
```

### 伪类

选择器 | 说明
:- | :-
`p::after`        | 在 p 之后添加内容 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::after)
`p::before`       | 在 p 之前添加内容 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::before)
`p::first-letter` | p中的第一个字母 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::first-letter)
`p::first-line`   | p 中的第一行 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::first-line)
`::selection`     | 由用户选择 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::selection)
`::placeholder`   | [占位符](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::placeholder) 属性 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::placeholder)
`:root`           | 文档根元素 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:root)
`:target`         | 突出显示活动锚点 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:target)
`div:empty`       | 没有子元素的元素 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:empty)
`p:lang(en)`      | 带有 en 语言属性的 P [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:lang)
`:not(span)`      | 不是跨度的元素 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:not)
`:host`           | shadowDOM 中选择自定义元素 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:root)
`::backdrop`      | 处于全屏模式的元素样式 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::backdrop)
`::marker`        | `li` 项目符号或者数字 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::marker)
`::file-selector-button`      | type="file" `input` 按钮 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::file-selector-button)

### 输入伪类

选择器 | 说明
:- | :-
`input:checked`       | 检查 `input` [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:checked)
`input:disabled`      | 禁用 `input` [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:disabled)
`input:enabled`       | 启用的 `input` [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:enabled)
`input:default`       | 有默认值的元素 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:default)
`input:blank`         | 空的输入框 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:blank)
`input:focus`         | `input` 有焦点 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:focus)
`input:in-range`      | 范围内的值 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:in-range)
`input:out-of-range`  | `input` 值超出范围 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:out-of-range)
`input:valid`         | `input` 有效值 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:valid)
`input:invalid`       | `input` 无效值 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:invalid)
`input:optional`      | 没有必需的属性 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:optional)
`input:required`      | 带有必需属性的 `input` [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:required)
`input:read-only`     | 具有只读属性 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:read-only)
`input:read-write`    | 没有只读属性 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:read-write)
`input:indeterminate` | 带有 [indeterminate](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:indeterminate) 状态 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:indeterminate)

### 结构伪类

选择器 | 说明
:- | :-
`p:first-child`         | 第一个孩子 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:first-child)
`p:last-child`          | 最后一个孩子 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:last-child)
`p:first-of-type`       | 首先是某种类型 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:first-of-type)
`p:last-of-type`        | 某种类型的最后一个 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:last-of-type)
`p:nth-child(2)`        | 其父母的第二个孩子 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:nth-child)
`p:nth-child(3n42)`     | Nth-child(an + b) 公式 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:nth-child)
`p:nth-last-child(2)`   | 后面的二孩 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:nth-last-child)
`p:nth-of-type(2)`      | 其父级的第二个 p [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:nth-of-type)
`p:nth-last-of-type(2)` | ...从后面 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:nth-last-of-type)
`p:only-of-type`        | 其父级的唯一性 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:only-of-type)
`p:only-child`          | 其父母的唯一孩子 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:only-child)
`:is(header, div) p`    | 可以选择的元素 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:is)
`:where(header, div) p` | 与 `:is` 相同 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:where)
`a:has(> img)`          | 包含 `img` 元素的 `a` 元素 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:has)
`::first-letter`        | 第一行的第一个字母 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:first-letter)
`::first-line`          | 第一行应用样式 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:first-line)

CSS 字体
------

### 属性
<!--rehype:wrap-class=row-span-3-->

属性 | 说明
:- | :-
`font-family:`    | 字体族名或通用字体族名 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-family)
`font-size:`      | 字体的大小 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-size)
`letter-spacing:` | 文本字符的间距 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/letter-spacing)
`line-height:`    | 多行文本间距 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/line-height)   
`font-weight:`     | 粗细程度 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-weight)   
`font-style:`      | 字体样式 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-style)   
`text-decoration:` | 文本的修饰线外观 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-decoration)   
`text-align:`      | 相对它的块父元素对齐 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-align)   
`text-transform:`  | 指定文本大小写 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-transform) 

另见: [Font](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font)

### 速记
<!--rehype:wrap-class=col-span-2&style=background:#ffeb3bcf;color:#333;-->

```css
font: italic    400     14px    /     1.5        sans-serif
      ┈┈┬┈┈┈    ┈┬┈     ┈┬┈┈          ┈┬┈        ┈┬┈┈┈┈┈┈┈┈
       样式      粗细    大小(必需的)    行高        字体(必需的)
```

### 示例

```css
font-family: Arial, sans-serif;
font-size: 12pt;
letter-spacing: 0.02em;
```

### 大小写
<!--rehype:wrap-class=row-span-2-->

```css
div {
  /* 首字母大写 Hello */
  text-transform: capitalize;
  /* 字母大写 HELLO */
  text-transform: uppercase;
  /* 字母小写 hello */
  text-transform: lowercase;
}
```

### @font-face

```css
@font-face {
  font-family: 'Glegoo';
  src: url('../Glegoo.woff');
}
```

CSS 颜色
------------

### 命名颜色

```css
color: red;
color: orange;
color: tan;
color: rebeccapurple;
```

更多标准[颜色名称](./colors-named.md)

### 十六进制颜色

```css
color: #090;
color: #009900;
color: #090a;
color: #009900aa;
```

### rgb() 颜色

```css
color: rgb(34, 12, 64, 0.6);
color: rgba(34, 12, 64, 0.6);
color: rgb(34 12 64 / 0.6);
color: rgba(34 12 64 / 0.3);
color: rgb(34.0 12 64 / 60%);
color: rgba(34.6 12 64 / 30%);
```

### HSL 颜色

```css
color: hsl(30, 100%, 50%, 0.6);
color: hsla(30, 100%, 50%, 0.6);
color: hsl(30 100% 50% / 0.6);
color: hsla(30 100% 50% / 0.6);
color: hsl(30.0 100% 50% / 60%);
color: hsla(30.2 100% 50% / 60%);
```

### 其它

```css
color: inherit;
color: initial;
color: unset;
color: transparent;
color: currentcolor; /* 关键字 */
```

### 全局值

```css
/* 全局值 */
color: inherit;
color: initial;
color: unset;
```

CSS 背景
----------

### 属性
<!--rehype:wrap-class=row-span-2-->

属性 | 说明
:- | :-
`background:` | _([速记](#速记-1))_ 
`background-color:`      | 查看: [Colors](#css-颜色)                                
`background-image:`      | 一个或者多个背景图像
`background-position:`   | 背景图片设置初始位置
`background-size:`       | 背景图片大小
`background-clip:`       | 背景(图片或颜色)是否延伸到边框、内边距盒子、内容盒子下面
`background-repeat:`     | 图像重复方式
`background-attachment:` | `scroll`/`fixed`/`local`

### 速记
<!--rehype:wrap-class=col-span-2&style=background:#ffeb3bcf;color:#333;-->

```css
background: #ff0   url(a.jpg)   left     top    /  100px auto   no-repeat   fixed;
            #abc   url(b.png)   center   center /  cover        repeat-x    local;
            ┈┬┈┈    ┈┬┈┈┈┈┈┈┈   ┈┬┈┈     ┈┬┈       ┈┈┬┈┈┈┈┈┈┈   ┈┈┬┈┈┈┈┈┈   ┈┈┬┈┈┈
            颜色     图片         位置x    位置x       图片大小     图像重复方式  位置是在视口内固定
```

### 示例
<!--rehype:wrap-class=col-span-2-->

```css
background: url(img_flwr.gif) right bottom no-repeat, url(paper.gif) left top repeat;
background: url(img_man.jpg) no-repeat center;
background: rgb(2,0,36);
background: linear-gradient(90deg, rgba(2,0,36,1) 0%,
  rgba(13,232,230,1) 35%,
  rgba(0,212,255,1) 100%);
```

CSS 盒子模型
--------

### 最大值/最小值

```css
.column {
  max-width: 200px; /* 最大宽度 200 像素 */
  width: 500px;     /* 宽度 500 像素 */
}
```

另见: [max-width](https://developer.mozilla.org/zh-CN/docs/Web/CSS/max-width) / [min-width](https://developer.mozilla.org/zh-CN/docs/Web/CSS/min-width) /  [max-height](https://developer.mozilla.org/zh-CN/docs/Web/CSS/max-height) / [min-height](https://developer.mozilla.org/zh-CN/docs/Web/CSS/min-height)

### 边距/补白

```css
.block-one {
  margin: 20px;  /* 边距 20 像素 */
  padding: 10px; /* 补白 10 像素 */
}
```

另见: [边距(margin)](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin) / [补白(padding)](https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding)

### Box-sizing

```css
.container {
  /* 设置的边框和补白的值是包含在 width 内的 */
  box-sizing: border-box;
}
```

另见: [box-sizing](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Box-sizing)

### 能见度 

```css
.invisible-elements {
  visibility: hidden; /* 隐藏元素 */
}
```

另见: [Visibility](https://developer.mozilla.org/zh-CN/docs/Web/CSS/visibility)


### Auto 关键字

```css
div {
  /* 览器自己选择一个合适的外边距 */
  margin: auto;
}
```

另见: [边距(margin)](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin)


### 溢出(Overflow)

```css
.small-block {
  /* 浏览器总是显示滚动条 */
  overflow: scroll;
}
```

另见: [溢出(overflow)](https://developer.mozilla.org/zh-CN/docs/Web/CSS/overflow)

CSS 动画
---------
<!--rehype:wrap-class=col-5-->

### 速记
<!--rehype:wrap-class=col-span-5&style=background:#ffeb3bcf;color:#333;-->

```css
animation:  bounce   300ms      linear     100ms    infinite   alternate-reverse  both                   reverse  
            ┈┬┈┈     ┈┬┈┈┈      ┈┬┈┈┈┈     ┈┈┬┈┈    ┈┈┈┬┈┈┈┈   ┈┈┬┈┈┈┈┈┈┈┈┈┈┈┈┈┈  ┈┈┬┈┈┈                 ┈┈┬┈┈┈
            动画名    动画时间     缓动函数    延迟     运行的次数   动画是否反向播放      如何将样式应用于其目标    是否运行或者暂停
```

### 属性
<!--rehype:wrap-class=row-span-2 col-span-3-->

属性 | 说明
:- | :-
`animation:`                 |  _([速记](#速记-2))_    
`animation-name:`            | 动画名 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/animation-name)
`animation-duration:`        | 动画周期的时长 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/animation-duration)
`animation-timing-function:` | 缓动函数 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/animation-timing-function)
`animation-delay:`           | 延迟 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/animation-delay)
`animation-iteration-count:` | 运行的次数 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/animation-iteration-count)
`animation-direction:`       | 动画是否反向播放 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/animation-direction)
`animation-fill-mode:`       | 如何将样式应用于其目标 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/animation-fill-mode)
`animation-play-state:`      | 是否运行或者暂停 [#](https://developer.mozilla.org/zh-CN/docs/Web/CSS/animation-play-state)

另见: [动画(Animation)](https://developer.mozilla.org/zh-CN/docs/Web/CSS/animation)

### 示例
<!--rehype:wrap-class=col-span-2-->

```css
/* @keyframes duration | timing-function | delay |
   iteration-count | direction | fill-mode | play-state | name */
animation: 3s ease-in 1s 2 reverse both paused slidein;
/* @keyframes duration | timing-function | delay | name */
animation: 3s linear 1s slidein;
/* @keyframes duration | name */
animation: 3s slidein;
animation: 4s linear 0s infinite alternate move_eye;
animation: bounce 300ms linear 0s infinite normal;
animation: bounce 300ms linear infinite;
animation: bounce 300ms linear infinite alternate-reverse;
animation: bounce 300ms linear 2s infinite alternate-reverse forwards normal;
```

### Javascript 事件
<!--rehype:wrap-class=col-span-2-->

```js
.one('webkitAnimationEnd oanimationend msAnimationEnd animationend')
```

CSS Flexbox
-------
<!--rehype:body-class=cols-2-->

### 简单实例

```css
.container {
  display: flex;
}
```

```css
.container > div {
  flex: 1 1 auto;
}
```

### 容器
<!--rehype:wrap-class=row-span-2-->

```css {2-3,5-8,10-11,13-16,18-23}
.container {
  display: flex;
  display: inline-flex;
  
  flex-direction: row;            /* ltr - 行(左向右) ▶ */
  flex-direction: row-reverse;    /* rtl - 行(右向左) ◀ */
  flex-direction: column;         /* top-bottom ▼ */
  flex-direction: column-reverse; /* bottom-top ▲ */
  
  flex-wrap: nowrap;       /* 摆放到一行 */
  flex-wrap: wrap;         /* 被打断到多个行中 */
  
  align-items: flex-start; /* 垂直对齐 - 顶部 */
  align-items: flex-end;   /* 垂直对齐 - 底部 */
  align-items: center;     /* 垂直对齐 - 中间 */
  align-items: stretch;    /* 所有人都一样的高度 (默认) */
  
  justify-content: flex-start;    /* [◀◀◀        ] */
  justify-content: center;        /* [    ■■■    ] */
  justify-content: flex-end;      /* [        ▶▶▶] */
  justify-content: space-between; /* [◀    ■    ▶] */
  justify-content: space-around;  /* [ ■   ■   ■ ] */
  justify-content: space-evenly;  /* [  ■  ■  ■  ] */
}
```

### 子元素

```css
.container > div {

  /* 这个: */
  flex: 1 0 auto;
  /* 相当于这个： */
  flex-grow: 1;
  flex-shrink: 0;
  flex-basis: auto;

  order: 1;

  align-self: flex-start;  /* left */
  margin-left: auto;       /* right */
}
```

### justify-content
<!--rehype:wrap-class=row-span-2-->

```css
justify-content: flex-start | flex-end | center | space-between
```

`flex-start`：左对齐(默认值)

```bash
╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮
┆╭┈┈╮╭┈╮╭┈┈┈╮                     ┆
┆╰┈┈╯╰┈╯╰┈┈┈╯                     ┆
╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯
```

`flex-end`：右对齐

```bash
╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮
┆                     ╭┈┈╮╭┈╮╭┈┈┈╮┆
┆                     ╰┈┈╯╰┈╯╰┈┈┈╯┆
╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯
```

`center`： 居中

```bash
╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮
┆          ╭┈┈╮╭┈╮╭┈┈┈╮           ┆
┆          ╰┈┈╯╰┈╯╰┈┈┈╯           ┆
╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯
```

`space-between`：两端对齐，项目之间的间隔都相等

```bash
╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮
┆╭┈┈╮           ╭┈╮          ╭┈┈┈╮┆
┆╰┈┈╯           ╰┈╯          ╰┈┈┈╯┆
╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯
```

`space-around`：每个项目两侧的间隔相等，项目之间的间隔比项目与边框的间隔大一倍

```bash
╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮
┆   ╭┈┈╮        ╭┈╮       ╭┈┈┈╮   ┆
┆   ╰┈┈╯        ╰┈╯       ╰┈┈┈╯   ┆
╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯
```

上面示例，假设主轴为从左到右

### flex-wrap

```css
flex-wrap: nowrap | wrap | wrap-reverse;
```

`nowrap`：不换行(默认)

```css
╭1╮╭2╮╭3╮╭4╮╭5╮╭6╮╭7╮╭8╮╭9╮╭10╮
╰┈╯╰┈╯╰┈╯╰┈╯╰┈╯╰┈╯╰┈╯╰┈╯╰┈╯╰┈┈╯
```

`wrap`：换行，第一行在 **`上方`**

```css
╭1┈╮ ╭2┈╮ ╭3┈╮ ╭4┈╮ ╭5┈╮ ╭6┈╮ ╭7┈╮
╰┈┈╯ ╰┈┈╯ ╰┈┈╯ ╰┈┈╯ ╰┈┈╯ ╰┈┈╯ ╰┈┈╯
╭8┈╮ ╭9┈╮ ╭10╮
╰┈┈╯ ╰┈┈╯ ╰┈┈╯
```

`wrap-reverse`：换行，第一行在 **`下方`**

```css
╭8┈╮ ╭9┈╮ ╭10╮
╰┈┈╯ ╰┈┈╯ ╰┈┈╯
╭1┈╮ ╭2┈╮ ╭3┈╮ ╭4┈╮ ╭5┈╮ ╭6┈╮ ╭7┈╮
╰┈┈╯ ╰┈┈╯ ╰┈┈╯ ╰┈┈╯ ╰┈┈╯ ╰┈┈╯ ╰┈┈╯
```

项目都排在一条线（又称"轴线"）上

### flex-direction

```css
flex-direction: row | row-reverse | column | column-reverse;
```

----

```bash
╭┈┈╮  ▲         ╭┈┈╮  ┆
╰┈┈╯  ┆         ╰┈┈╯  ┆
╭┈┈╮  ┆         ╭┈┈╮  ┆
╰┈┈╯  ┆         ╰┈┈╯  ┆     ┈┈┈┈┈┈┈┈┈┈┈▶    ◀┈┈┈┈┈┈┈┈┈┈┈
╭┈┈╮  ┆         ╭┈┈╮  ┆    ╭┈┈╮ ╭┈┈╮ ╭┈┈╮  ╭┈┈╮ ╭┈┈╮ ╭┈┈╮
╰┈┈╯  ┆         ╰┈┈╯  ▼    ╰┈┈╯ ╰┈┈╯ ╰┈┈╯  ╰┈┈╯ ╰┈┈╯ ╰┈┈╯
┈┬┈┈┈┈┈┈        ┈┬┈┈┈┈┈┈    ┈┬┈┈┈┈┈┈┈┈┈┈┈   ┈┬┈┈┈┈┈┈┈┈┈┈┈ 
column-reverse  column       row             row-reverse
```

属性决定主轴的方向（即项目的排列方向）

### align-items

```css
align-items: flex-start | flex-end | center | baseline | stretch;
```

----

```css
  ▶ flex-start(起点对齐)    ▶ flex-end(终点对齐)
╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮  ╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮
┆ ╭┈┈╮ ╭┈┈╮ ╭┈┈╮ ╭┈┈╮ ┆  ┆                     ┆
┆ ┆  ┆ ┆  ┆ ╰┈┈╯ ┆  ┆ ┆  ┆      ╭┈┈╮           ┆
┆ ╰┈┈╯ ┆  ┆      ╰┈┈╯ ┆  ┆ ╭┈┈╮ ┆  ┆      ╭┈┈╮ ┆
┆      ╰┈┈╯           ┆  ┆ ┆  ┆ ┆  ┆ ╭┈┈╮ ┆  ┆ ┆
┆                     ┆  ┆ ╰┈┈╯ ╰┈┈╯ ╰┈┈╯ ╰┈┈╯ ┆
╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯  ╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯
  ▶ center(中点对齐)        ▶ stretch(占满整个容器的高度)
╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮  ╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮
┆      ╭┈┈╮           ┆  ┆ ╭┈┈╮ ╭┈┈╮ ╭┈┈╮ ╭┈┈╮ ┆
┆ ╭┈┈╮ ┆  ┆      ╭┈┈╮ ┆  ┆ ┆  ┆ ┆  ┆ ┆  ┆ ┆  ┆ ┆
┆ ┆  ┆ ┆  ┆ ╭┈┈╮ ┆  ┆ ┆  ┆ ┆  ┆ ┆  ┆ ┆  ┆ ┆  ┆ ┆
┆ ┆  ┆ ┆  ┆ ╰┈┈╯ ┆  ┆ ┆  ┆ ┆  ┆ ┆  ┆ ┆  ┆ ┆  ┆ ┆
┆ ╰┈┈╯ ┆  ┆      ╰┈┈╯ ┆  ┆ ┆  ┆ ┆  ┆ ┆  ┆ ┆  ┆ ┆
┆      ╰┈┈╯           ┆  ┆ ╰┈┈╯ ╰┈┈╯ ╰┈┈╯ ╰┈┈╯ ┆
╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯  ╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯
  ▶ baseline(第一行文字的基线对齐)
╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮
┆  ╭┈┈┈┈┈┈╮               ╭┈┈┈┈┈┈╮             ┆
┆  ┆      ┆ ╭┈┈┈┈╮ ╭┈┈┈┈╮ ┆      ┆ ╭┈┈┈┈╮╭┈┈┈┈╮┆
┆  ┆ text ┆ ┆text┆ ┆text┆ ┆ text ┆ ┆text┆┆text┆┆
┆  ┆      ┆ ╰┈┈┈┈╯ ┆    ┆ ┆      ┆ ╰┈┈┈┈╯┆    ┆┆
┆  ╰┈┈┈┈┈┈╯        ╰┈┈┈┈╯ ╰┈┈┈┈┈┈╯       ╰┈┈┈┈╯┆
┆                                              ┆
╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯
```

### align-content

```css
align-content: flex-start | flex-end | center | space-between | space-around | stretch;
```
<!--rehype:className=wrap-text -->

----

```css
 ▶ flex-start(起点对齐)     ▶ flex-end(终点对齐)
╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮  ╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮
┆ ╭┈┈╮╭┈╮╭┈┈┈╮╭╮╭┈┈┈┈╮ ┆  ┆                      ┆
┆ ╰┈┈╯╰┈╯╰┈┈┈╯╰╯╰┈┈┈┈╯ ┆  ┆ ╭┈┈╮╭┈╮╭┈┈┈╮╭╮╭┈┈┈┈╮ ┆
┆ ╭┈┈┈╮╭╮              ┆  ┆ ╰┈┈╯╰┈╯╰┈┈┈╯╰╯╰┈┈┈┈╯ ┆
┆ ╰┈┈┈╯╰╯              ┆  ┆ ╭┈┈┈╮╭╮              ┆
┆                      ┆  ┆ ╰┈┈┈╯╰╯              ┆
╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯  ╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯
 ▶ center(中点对齐)         ▶ stretch(满整个交叉轴)
╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮  ╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮
┆                      ┆  ┆ ╭┈┈╮╭┈╮╭┈┈┈╮╭╮╭┈┈┈┈╮ ┆
┆ ╭┈┈╮╭┈╮╭┈┈┈╮╭╮╭┈┈┈┈╮ ┆  ┆ ┆  ┆┆ ┆┆   ┆┆┆┆    ┆ ┆
┆ ╰┈┈╯╰┈╯╰┈┈┈╯╰╯╰┈┈┈┈╯ ┆  ┆ ╰┈┈╯╰┈╯╰┈┈┈╯╰╯╰┈┈┈┈╯ ┆
┆ ╭┈┈┈╮╭╮              ┆  ┆ ╭┈┈┈╮╭╮╭┈╮           ┆
┆ ╰┈┈┈╯╰╯              ┆  ┆ ┆   ┆┆┆┆ ┆           ┆
┆                      ┆  ┆ ╰┈┈┈╯╰╯╰┈╯           ┆
╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯  ╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯
 ▶ space-between(两端对齐)  ▶ space-around(均匀分布项目)
╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮  ╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮ 
┆ ╭┈┈╮╭┈┈╮╭┈┈╮╭┈┈╮╭┈┈╮ ┆  ┆                      ┆ 
┆ ╰┈┈╯╰┈┈╯╰┈┈╯╰┈┈╯╰┈┈╯ ┆  ┆ ╭┈┈╮╭┈┈╮╭┈┈╮╭┈┈╮╭┈┈╮ ┆ 
┆                      ┆  ┆ ╰┈┈╯╰┈┈╯╰┈┈╯╰┈┈╯╰┈┈╯ ┆ 
┆                      ┆  ┆                      ┆ 
┆                      ┆  ┆ ╭┈┈╮                 ┆ 
┆ ╭┈┈╮                 ┆  ┆ ╰┈┈╯                 ┆ 
┆ ╰┈┈╯                 ┆  ┆                      ┆ 
╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯  ╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯ 
```

### order

```css
.item {
  order: <integer>;
}
```

----

```css
╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮ ╭┈┈┈┈┈┈┈┈┈╮
┆ ╭1┈╮ ╭1┈┈╮ ╭1┈╮ ╭2┈╮ ╭3┈┈┈┈┈┈╮ ┆ ┆ ╭2┈┈┈┈╮ ┆
┆ ╰┈┈╯ ╰┈┈┈╯ ╰┈┈╯ ╰┈┈╯ ╰┈┈┈┈┈┈┈╯ ┆ ┆ ╰┈┈┈┈┈╯ ┆
╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯ ┆ ╭2┈┈┈┈╮ ┆
╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮ ┆ ╰┈┈┈┈┈╯ ┆
┆ ╭-┈┈╮ ╭┈┈┈╮ ╭┈┈┈┈┈┈┈┈╮ ╭┈┈┈╮   ┆ ┆ ╭99┈┈┈╮ ┆
┆ ┆-1 ┆ ┆ 1 ┆ ┆ 2      ┆ ┆ 5 ┆   ┆ ┆ ┆     ┆ ┆
┆ ╰┈┈┈╯ ╰┈┈┈╯ ╰┈┈┈┈┈┈┈┈╯ ╰┈┈┈╯   ┆ ┆ ╰┈┈┈┈┈╯ ┆
╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯ ╰┈┈┈┈┈┈┈┈┈╯
```

属性 [order](https://developer.mozilla.org/zh-CN/docs/Web/CSS/order) 定义项目的排列顺序。数值越小，排列越靠前，默认为 `0`

### flex-grow

```css
.item {
  flex-grow: <number>; /* default 0 */
}
```

----

```css
╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮
┆ ╭┈┈1┈┈╮╭┈┈2┈┈╮╭┈┈1┈┈╮ ┆
┆ ╰┈┈┈┈┈╯╰┈┈┈┈┈╯╰┈┈┈┈┈╯ ┆
╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯
╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮
┆ ╭┈1┈╮╭┈┈┈┈2┈┈┈┈╮╭┈1┈╮ ┆
┆ ╰┈┈┈╯╰┈┈┈┈┈┈┈┈┈╯╰┈┈┈╯ ┆
╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╯
```

属性 [flex-grow](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex-grow) 定义项目的放大比例，默认为`0`，即如果存在剩余空间，也不放大

CSS Flexbox 技巧
--------------

### 垂直中心

```css
.container {
  display: flex;
}
.container > div {
  width: 100px;
  height: 100px;
  margin: auto;
}
```

### 垂直中心 (2)

```css
.container {
  display: flex;
  /* 垂直的 */
  align-items: center; 
  /* 水平的 */
  justify-content: center;
}
```

### 重新排序

```css
.container > .top {
 order: 1;
}
.container > .bottom {
 order: 2;
}
```

### 移动布局


```css
.container {
  display: flex;
  flex-direction: column;
}
.container > .top {
  flex: 0 0 100px;
}
.container > .content {
  flex: 1 0 auto;
}
```

一个固定高度的顶部栏和一个动态高度的内容区域

### Table-like 像表格
<!--rehype:wrap-class=col-span-2-->

```css
.container {
  display: flex;
}
/* 这里的“px”值只是建议的百分比 */
.container > .checkbox { flex: 1 0 20px; }
.container > .subject  { flex: 1 0 400px; }
.container > .date     { flex: 1 0 120px; }
```

这会创建具有不同宽度的列，但会根据情况相应地调整大小

### Vertical 垂直的

```css
.container {
  align-items: center;
}
```

垂直居中所有项目

### 左和右
<!--rehype:wrap-class=col-span-2-->

```css
.menu > .left  { align-self: flex-start; }
.menu > .right { align-self: flex-end; }
```

CSS Grid 网格布局
------------

### 网格模板列

```css
#grid-container {
  display: grid;
  width: 100px;
  grid-template-columns: 20px 20% 60%;
}
```

### fr 相对单位

```css
.grid {
  display: grid;
  width: 100px;
  grid-template-columns: 1fr 60px 1fr;
}
```

### Grid Gap 网格间隙

```css
/* 行间距为 20px */
/* 列之间的距离是 10px */
#grid-container {
  display: grid;
  grid-gap: 20px 10px;
}
```

### CSS 网格行
<!--rehype:wrap-class=row-span-2-->

CSS 语法: 

- grid-row: grid-row-start / grid-row-end;

#### 实例

```css
.item {
  grid-row: 1 / span 2;
}
```

### CSS 块级网格

```css
#grid-container {
    display: block;
}
```

### CSS 内联级别网格

```css
#grid-container {
  display: inline-grid;
}
```

### CSS 网格行间隙

```css
grid-row-gap: length;
```

任何合法的长度值，例如 `px` 或 `%`。`0` 是默认值

### CSS 网格区域

```css
.item1 {
  grid-area: 2 / 1 / span 2 / span 3;
}
```

### minmax() 函数
<!--rehype:wrap-class=col-span-2-->

```css
.grid {
  display: grid;
  grid-template-columns: 100px minmax(100px, 500px) 100px; 
}
```
<!--rehype:className=wrap-text -->

定义了一个长宽范围的闭区间

### grid-row-start & grid-row-end

CSS 语法: 

- grid-row-start: auto|row-line;
- grid-row-end: auto|row-line|span n;

#### 实例

```css
grid-row-start: 2;
grid-row-end: span 2;
```

### 对齐项目

```css
#container {
  display: grid;
  justify-items: center;
  grid-template-columns: 1fr;
  grid-template-rows: 1fr 1fr 1fr;
  grid-gap: 10px;
}
```

### CSS 网格模板区域

```css
.item {
  grid-area: nav;
}
.grid-container {
  display: grid;
  grid-template-areas:
  'nav nav . .'
  'nav nav . .';
}
```


### Justify Self

```css
#grid-container {
  display: grid;
  justify-items: start;
}
.grid-items {
  justify-self: end;
}
```

网格项目位于行的右侧（末尾）

### 对齐项目

```css
#container {
  display: grid;
  align-items: start;
  grid-template-columns: 1fr;
  grid-template-rows: 1fr 1fr 1fr;
  grid-gap: 10px;
}
```

CSS 动态内容
------------

### 变量

定义 CSS 变量

```css
:root {
  --first-color: #16f;
  --second-color: #ff7;
}
```

变量用法

```css
#firstParagraph {
  background-color: var(--first-color);
  color: var(--second-color);
}
```

另见: [CSS Variable](https://developer.mozilla.org/zh-CN/docs/Web/CSS/--*)

### 计数器

```css
/* Set "my-counter" to 0 */
counter-set: my-counter;
```

```css
/* Increment "my-counter" by 1 */
counter-increment: my-counter;
```

```css
/* Decrement "my-counter" by 1 */
counter-increment: my-counter -1;
```

```css
/* Reset "my-counter" to 0 */
counter-reset: my-counter;
```

另见: [Counter set](https://developer.mozilla.org/en-US/docs/Web/CSS/counter-set)

### 使用计数器

```css
body { counter-reset: section; }
h3::before {
  counter-increment: section; 
  content: "Section." counter(section);
}
```

```css
ol {
  counter-reset: section;   
  list-style-type: none;
}
li::before {
  counter-increment: section;
  content: counters(section, ".") " "; 
}
```

Css 3 技巧
------------

### 滚动条平滑

```css
html {
  scroll-behavior: smooth;
}
```

[点击我](#入门)页面会平滑滚动到入门

### 忽略用作间距的换行符 \<br />

```css
br + br {
  display: none;
}
```

### 使用 :empty 隐藏空 HTML 元素

```css
:empty {
  display: none;
}
```

### CSS 重置

```css
html {
  box-sizing: border-box;
}
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

有助于在不同的浏览器之间强制样式一致性，并为样式元素提供干净的盒子

### 使用图像作为光标

```css
div {
  cursor: url('path-to-image.png'), url('path-to-fallback-image.png'), auto;
  /* 表情符号作为光标 */
  cursor: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg'  width='40' height='48' viewport='0 0 100 100' style='fill:black;font-size:24px;'><text y='50%'>🚀</text></svg>"), auto;
}
```
<!--rehype:className=wrap-text -->

### 文本溢出显示省略号

```css
.overflow-ellipsis {
  width: 200px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
```

一行文本截断显示省略号 _(...)_

### 将文本截断到特定的行数

```css
.overflow-truncate {
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 3;
  overflow: hidden;
}
```

多行文本截断到特定的行数，末尾显示省略号 _(...)_

### 计算函数

```css
div {
  width: calc(100% - 30px);
  height: calc(100% - 30px);
}
```

[`calc()`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/calc) CSS 函数允许您在指定 CSS 属性值时执行计算

### 粘性定位元素

```css
.sticky {
  position: sticky;
  top: 0;
}
```

属性 [sticky](https://developer.mozilla.org/zh-CN/docs/Web/CSS/position#sticky) 能在滚动到顶部的位置固定住元素

### 使用带有空链接的属性选择器

```css
a[href^="http"]:empty::before {
  content: attr(href);
}
```

如果你的 `<a>` 标签里面没有内容，将 `href` 的值作为内容展示


### 使用 :root 表示灵活类型

响应式布局中的字体大小应该能够根据每个视口进行调整，您可以使用 `:root` 根据视口高度和宽度计算字体大小

```css
:root {
  font-size: calc(1vw + 1vh + .5vmin);
}
```

现在您可以根据 `:root` 计算的值使用根 `em` 单位：

```css
body {
  font: 1rem/1.6 sans-serif;
}
```

另见
---------

- [CSS selectors cheatsheet](https://frontend30.com/css-selectors-cheatsheet/) _(frontend30.com)_
- [MDN: Using CSS flexbox](https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Flexible_boxes)
- [Ultimate flexbox cheatsheet](http://www.sketchingwithcss.com/samplechapter/cheatsheet.html)
- [GRID: A simple visual cheatsheet](http://grid.malven.co/)
- [CSS Tricks: A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Browser support](https://caniuse.com/#feat=css-grid)
- [Flex 布局教程：语法篇](https://www.ruanyifeng.com/blog/2015/07/flex-grammar.html?utm_source=tuicool)
- [CSS 专业技巧](https://github.com/AllThingsSmitty/css-protips/tree/master/translations/zh-CN)