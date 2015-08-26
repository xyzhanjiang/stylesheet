# My CSS Style Guide {

## 唯一指导标准

让多人协作的代码看上去像一个人写的一样

## Indentation

* Use 2 spaces
* Never mix spaces and tabs for indentation

``` css
.selector {
  color: #666;
}
```

## Rule

* Put a blank line between rules
* Put a space before the opening brace `{` in rules
* Put closing braces } of rules on a new line

``` css
.selector-1 {
  color: #666;
}

.selector-2 {
  color: #999;
}
```

### @ rule

Use utf-8

``` css
@charset "utf-8";
```

## Selectors

* When using multiple selectors in a rule declaration, give each selector its own line
* 逗号写在每一行末尾
* 选择器中尽量不要出现 `div` 和 `span` 等元素 / Do not use `div` & `span` element selector
* 不要使用 ID 选择器 / Do not use ID selector

``` css
.selector-1,
.selector-2 {
  /* ^_^ */
}
```

关系选择器的符号两边都插入一个空格：

``` css
ul > li {
  /* ^_^ */
}
```

超链接状态伪类选择器的顺序为：

``` css
a:link,
a:visited,
a:focus,
a:hover,
a:active {
  /* ^_^ */
}
```

Quote attribute values in selectors.

``` css
input[type="radio"] {
  /* ^_^ */
}
```

## Declaration

* Give each declaration its own line.
* Put a space after the `:` character.
* Make sure the declarations are in alphabetical order by the property.
* Do not omit the semi-colon at the end of the last declaration in a declaration block.

``` css
.selector {
  color: #666;
  display: inline-block;
  padding: 10px;
}
```

合并申明，简化代码：

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

## Value

* Use double quotes.

``` css
.selector {
  content: "\00a0";
  font-family: "Microsoft Yahei";
}
```

Put a space after the `,` character

``` css
.selector {
  color: rgba(0, 0, 0, .5);
}
```

属性值可以省略的时候尽量省略：

``` css
.selector {
  margin: 10px 20px 10px 20px;
}

.selector {
  margin: 10px 20px;
}
```

### Colors

Use lowercase and shorthand hex color values.

``` css
.selector {
  color: #fff;
}
```

Use `rgba()` if need.

``` css
.selector {
  color: #f00;
  color: rgba(255, 0, 0, .5);
}
```

### URL

URL 值省略引号，当有空格时除外，所以为了一致性，不要在文件夹或文件名中使用空格

``` css
.selector {
  background-image: url(i/bg.gif);
}
```

### 部分属性值的书写顺序

边框的值按照 -width, -style, -color 的顺序书写：

``` css
.selector {
  border: 1px solid #ccc;
}
```

过渡值按照 -property, -duration, -timing-function, -delay 的顺序书写

``` css
.selector {
  transition: all .2s ease-in-out .5s;
}
```

### 单位

Where allowed, avoid specifying units for zero-values.

``` css
.selector {
  margin: 0;
}
```

如果是时间值为 0 则不要省略单位：

``` css
.selector {
  transition: all 0s;
}
```

当使用百分比颜色函数时，值为 0 的时候不要省略百分号：

``` css
.selector {
  color: rgba(100%, 0%, 0%, .5);
}
```

省略绝对值小于 1 的数值小数点前面的 0：

``` css
.selector {
  margin: .5em;
}
```

## Prefix

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

## Comments

* 注释和代码之间插入一个空格
* 注释内容两端都插入一个空格

``` css
.selector {
  margin: .5em; /* comment */
}
```

## 命名

* Use lowercase.
* 使用连字符分隔单词
* 使用有意义的单词

``` css
.class-name {
  /* ^_^ */
}
```

# }
