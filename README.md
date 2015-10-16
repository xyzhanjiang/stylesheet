# My CSS Style Guide {

## 唯一指导准则

自律

## 缩进

使用2个空格来作为缩进层级，千万不要混合使用空格和制表符。

``` css
.selector {
  color: #666;
}
```

## Rules 规则集

1. 使用空行分隔规则集。
2. 左大括弧 `{` 前面插入一个空格。
3. 右大括弧 `}` 单独一行。

``` css
.selector-1 {
  color: #666;
}

.selector-2 {
  color: #999;
}
```

### @ 规则

使用 utf-8 字符集。

``` css
@charset "utf-8";
```

## Selectors 选择器

1. 每个选择器独立一行，逗号 `,` 放在每行末尾。
2. 不在选择器中使用 `div` 和 `span` 元素。
3. 不使用 ID 选择器。

``` css
.selector-1,
.selector-2 {
  /* ^_^ */
}
```

### Combinators 关系选择器

关系选择器的符号两边都插入一个空格：

``` css
ul > li {
  /* ^_^ */
}
```

### 属性选择器

属性选择器中的属性值使用双引号引用起来，虽然这不是必须的。

``` css
input[type="radio"] {
  /* ^_^ */
}
```

## Declaration 声明

1. 每条声明单独一行。
2. 冒号 `:` 后面插入一个空格。
3. 声明按属性名的首写字母顺序排列。
4. 不要省略最后一个声明的结束分号。

``` css
.selector {
  color: #666;
  display: inline-block;
  padding: 10px;
}
```

尽量合并声明，简化代码：

``` css
.selector {
  margin-top: 10px;
  margin-right: 20px;
  margin-bottom: 30px;
  margin-left: 40px;
}

.selector {
  margin: 10px 20px 30px 40px;
}
```

## Value 属性值

* 需要使用引号的时候一律使用双引号。

``` css
.selector {
  content: "\00a0";
  font-family: "Microsoft Yahei";
}
```

逗号 `,` 后面插入一个空格。

``` css
.selector {
  color: rgba(0, 0, 0, .5);
}
```

使用简写形式的属性值。

``` css
.selector {
  margin: 10px 20px 10px 20px;
}

.selector {
  margin: 10px 20px;
}
```

### Colors 颜色值

使用 16 进制的小写颜色值。

``` css
.selector {
  color: #fff;
}
```

使用 `rgba()` 函数。

``` css
.selector {
  color: #f00;
  color: rgba(255, 0, 0, .5);
}
```

### URL

URL 值省略引号，但是当值内有空格时除外，所以为了一致性，不要在文件夹或文件名中使用空格。

``` css
.selector {
  background-image: url(i/bg.gif);
}
```

### 部分属性值按照固定的顺序书写

border 的值按照 -width, -style, -color 的顺序书写：

``` css
.selector {
  border: 1px solid #ccc;
}
```

transition 的值按照 -property, -duration, -timing-function, -delay 的顺序书写

``` css
.selector {
  transition: all .2s ease-in-out .5s;
}
```

### Units 单位

在允许的情况下省略值为 0 的单位。

``` css
.selector {
  margin: 0;
}
```

如果是时间值为 0 则不要省略单位。

``` css
.selector {
  transition: all 0s;
}
```

当使用百分比颜色函数时，值为 0 的时候不要省略百分号。

``` css
.selector {
  color: rgba(100%, 0%, 0%, .5);
}
```

当属性值的数字部分绝对值小于 1 时省略前置的数字 0。

``` css
.selector {
  margin: .5em;
}
```

## Prefix 前缀

* 带有浏览器前缀按照 `-webkit-`, `-moz-`, `-ms-`, `-o-` 的顺序书写
* 带有浏览器前缀的属性或者属性值使用空格在垂直方向上对齐，标准属性写在最后

``` css
@-webkit-keyframes animation-name {
}

@-o-keyframes animation-name {
}

@keyframes animation-name {
}

.selector {
  -webkit-user-select: none;
     -moz-user-select: none;
      -ms-user-select: none;
          user-select: none;
}
```

## Comments 注释

1. 注释和代码之间插入一个空格
2. 注释内容两端都插入一个空格

``` css
.selector {
  margin: .5em; /* comment */
}
```

## Name 命名

1. 使用小写字母和连字符。
2. 使用有意义的单词。

``` css
.class-name {
  /* ^_^ */
}
```

使用有意义的单词、小写字符、连字符来命名。

### JavaScript hooks

Use `js-*` classes to denote behavior (as opposed to style), but keep these classes out of your CSS.

``` html
<div class="js-box"></div>
```

# }
