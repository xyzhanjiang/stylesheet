# My CSS Style Guide {

For my work

## Table of contents

* [Comments](#comments)
* [Formatting](#formatting)
* [Selectors](#selectors)
* [Declaration](#declaration)
* [Value](#value)
* [Vendor Prefixes](#vendor-prefixes)
* [ClassName](#classname)
* [Hacks](#hacks)

## Comments

``` css
/* ======================================================================
   大块 多行 组件注释
   大块 多行 组件注释
   ====================================================================== */

/* 小块 单行注释
   ====================================================================== */

/* 单行注释 */

.selector {
  margin: .5em; /* Inline comment */
}
```

## Formatting

1. 缩进 2 个空格
2. utf-8
3. 使用群组选择器的时候每条选择器单独一行，并且逗号 `,` 放在行末

``` css
@charset "utf-8"; /* 2 */

@media (min-width: 992px) {
  .selector-1, /* 3 */
  .selector-2 {
    color: rgba(0, 0, 0, .5);
  }

  .selector-3 {
    padding: 10px;
  }
}
```

## Selectors

1. 不在选择器里面直接使用 `div` 和 `span` 等元素
2. 不建议使用 ID 选择器
3. 当使用属性选择器的时候添加双引号

``` css
/* bad */
div,
a span { /* 1 */
  display: none;
}

#id { /* 2 */
  font-size: 14px;
}

/* good */
label + input[type="radio"] { /* 3 */
  /* ^_^ */
}
```

当使用后代元素选择器的时候，嵌套层级不宜超过 3 级，保持样式的独立性以及降低选择器权重，同时也出于性能考量

``` css
/* bad */
.selector-a .selector-b .selector-c .selector-d {
  margin: 0;
}

/* good */
.selector-a .selector-d {
  margin: 0;
}

.selector-d {
  margin: 0;
}
```

链接伪类选择器应同时指定 hover 和 focus 样式

``` css
a:hover,
a:focus {
  color: red;
}
```

对列表元素使用子元素选择器以免样式影响更深层级的后代

``` css
.list > li {
  margin-bottom: 2px;
}
```

## Declaration

1. 每条声明单独一行
2. 声明块中最后一条声明不要省略分号 `;`

``` css
.selector {
  box-sizing: border-box; /* 1 */
  color: #666;
  display: inline-block;
  padding: 10px; /* 2 */
}
```

## Value

1. 当需要使用引号的时候使用双引号
2. url 值不需要添加引号
3. 值为 0 的时候去掉单位，除非是时间值或者百分比值
4. 省略绝对值小于 1 的值前面的 0
5. 16 进制颜色值使用缩写形式

``` css
.selector {
  background-image: url(i/bg.gif); /* 2 */
  color: #f00; /* 5 */
  font-family: "Microsoft Yahei", sans-serif; /* 1 */
  margin: -.25em; /* 4 */
  transition: all 0s; /* 3 */
}

.selector: before {
  content: "\00a0"; /* 1 */
}
```

## Vendor prefixes

使用 [Autoprefixer](https://twitter.com/autoprefixer) 自动添加浏览器厂商前缀

直接这样写

``` css
.selector {
  display: flex;
}
```

会根据需要兼容的浏览器编译成如下所示

``` css
.selector {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex
}
```

## ClassName

1. 使用小写字母和数字，不使用大写字母或者下划线以及其它特殊符号
2. 使用连字符 `-` 分割单词
3. 使用语义化的命名方式

``` css
/* bad */
.MB_5 { /* 12 */
  margin-bottom: 5px;
}

/* good */
.margin-bottom-5 { /* 12 */
  margin-bottom: 5px;
}

.btn-primary { /* 3 */
  margin: 0;
}
```

active, disabled, first, last, item, left, right, on, off 不单独给这些类指定任何样式，配合使用多类，子元素等其它类型的选择器

``` css
/* bad */
.active {
  color: blue;
}

.disabled {
  background-color: #eee;
}

/* good */
.btn.disabled { /* 表示按钮禁用状态 */
  background-color: #eee;
}

.list > .item { /* 表示列表的每一条 */
  margin-bottom: 2px;
}
```

### JavaScript hooks

给 JavaScript 钩子添加 `js-*` 前缀用以区别，这些类名不添加任何样式，只提供给 JavaScript 代码使用

``` html
<div class="js-box"></div>
```

## 样式分离

将呈现类样式与定位类样式分离

``` css
/* bad */
.btn {
  background-color: #efefef;
  border: 1px solid #ccc;
  color: #36f;
  display: block;
  height: 24px;
  line-height: 24px;
  margin-left: 8px;
  padding: 0 12px;
}

/* good */
.btn {
  background-color: #efefef;
  border: 1px solid #ccc;
  color: #36f;
  display: block;
  height: 24px;
  line-height: 24px;
  padding: 0 12px;
}

.margin-left-8 {
  margin-left: 8px;
}
```

## Hacks

IE 浏览器统一使用 hacks

``` css
.selector {
  _color: #666;  /* IE 6 */
  *color: #999;  /* IE 6, 7 */
  color: #333\9; /* IE 6, 7, 8, 9, 10 */
}
```

# }
