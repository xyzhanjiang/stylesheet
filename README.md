# My CSS Style Guide {

## 唯一指导准则

自律，至少让我过一段时间后再回过头来看这段代码知道自己到底写的是什么！

## Comments 注释

1. 行内注释和代码之间插入一个空格。
2. 注释内容两端都插入一个空格。

``` css
.selector {
  margin: .5em; /* comment */
}
```

## Format 格式

1. 使用2个空格来作为缩进层级，千万不要混合使用空格和制表符。
2. 使用空行分隔规则集。
3. 左大括弧 `{` 前面插入一个空格。
4. 右大括弧 `}` 单独一行。
5. 属性和属性值之间的冒号 `:` 后面插入一个空格。
6. 逗号 `,` 后面插入一个空格，但当逗号位于一行末尾时除外。
7. 使用 utf-8 字符集，并且该声明位于样式文件第一行。
8. 使用群组选择器时每个选择器独立一行，逗号 `,` 放在每行末尾。

``` css
@charset "utf-8";

@media (min-width: 992px) {
  .selector-1,
  .selector-2 {
    color: rgba(0, 0, 0, .5);
  }
}
```

## Selectors 选择器

1. 尽量不在选择器中使用 `div` 和 `span` 元素。
2. 不使用 ID 选择器。
3. 关系选择器的符号两边都插入一个空格。
4. 属性选择器中的属性值使用双引号引用起来，虽然这不是必须的。

``` css
label + input[type="radio"] {
  /* ^_^ */
}
```

## Declaration 声明

1. 每条声明单独一行。
2. 声明按属性名的首写字母顺序排列。
3. 不要省略最后一个声明的结束分号。
4. 带浏览器前缀的声明在垂直方向对齐。

``` css
.selector {
  -webkit-box-sizing: border-box;
     -moz-box-sizing: border-box;
          box-sizing: border-box;
  color: #666;
  display: inline-block;
  padding: 10px; /* 这个分号不要省略掉了 */
}
```

尽量合并声明，简化代码，不过合并时需要注意缺省值的影响。

``` css
.selector {
  margin-top: 10px;
  margin-right: 20px;
  margin-bottom: 10px;
  margin-left: 20px;
}

/* 合并后 */
.selector {
  margin: 10px 20px 10px 20px;
}

/* 使用缺省值 */
.selector {
  margin: 10px 20px;
}
```

## Value 属性值

1. 当必须使用引号的时候一律使用双引号。
2. 颜色值使用 16 进制的小写字母。
3. URL 值建议省略引号，但是当值内有空格时除外，所以为了一致性，不要在文件夹或文件名中使用空格。

``` css
.selector {
  background-image: url(i/bg.gif);
  color: #fff;
  content: "\00a0";
  font-family: "Microsoft Yahei", sans-serif;
}
```

当属性值为多值列表的时候按照一致的顺序书写。

``` css
.selector {
  border: 1px solid #ccc;
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

带有浏览器前缀按照 `-webkit-`, `-moz-`, `-ms-`, `-o-` 的顺序书写，并且仅考虑这4种前缀，标准放在最后。

``` css
@-webkit-keyframes animation-name {
  from {
    -webkit-transform: scale(1);
            transform: scale(1);
  }

  to {
    -webkit-transform: scale(1.1);
            transform: scale(1.1);
  }
}

@keyframes animation-name {
  from {
    -webkit-transform: scale(1);
        -ms-transform: scale(1);
            transform: scale(1);
  }

  to {
    -webkit-transform: scale(1.1);
        -ms-transform: scale(1.1);
            transform: scale(1.1);
  }
}
```

## Name 命名

使用具有意义的单词、小写字符、连字符来命名。

``` css
.class-name {
  /* ^_^ */
}
```

使用单独的 `active` 类或者 `-active` 类后缀表示当前、激活等状态。

``` html
<ul>
  <li>Option 1</li>
  <li class="active">Option 2</li>
</ul>
```

### JavaScript hooks

Use `js-*` classes to denote behavior (as opposed to style), but keep these classes out of your CSS.

``` html
<div class="js-box"></div>
```

## Hacks

使用一致的 Hacks 方式。

``` css
.selector {
  _color: #666;  /* IE 6 */
  *color: #999;  /* IE 6, 7 */
  color: #333\9; /* IE 6, 7, 8, 9, 10 */
}
```

## Snippet

使用一致的方式来解决各种问题，让代码一目了然。

### 水平居中

固定宽度块级元素水平居中。

``` css
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 800px;
}
```

### Clearfix 清除浮动

``` css
.clearfix {
  *zoom: 1;
}

.clearfix:before,
.clearfix:after {
  content: " ";
  display: table;
}

.clearfix:after {
  clear: both;
}
```

### 单行文本溢出省略

``` css
.selector {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
```

### 不透明度

``` css
.selector {
  filter: alpha(opacity=30);
  opacity: .3;
}
```

# }
