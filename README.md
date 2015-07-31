# My CSS Style Guide {

## 缩进

* 使用两个空格来缩进代码

``` css
.selector {
  color: #666;
}
```

## 规则

* 每条规则之间插入一个空行
* 左花括号 `{` 之前插入一个空格
* 右花括号 `}` 单独成行

``` css
.selector-1 {
  color: #666;
}

.selector-2 {
  color: #999;
}
```

### @规则

字符集使用 utf-8

``` css
@charset "utf-8";
```

## 选择器

* 使用群组选择器的时候每个选择器单独成行
* 使用小写字母以及连字符，不使用大写字母、下划线等
* 选择器中不要出现 `div` 和 `span` 等元素

``` css
.selector-1,
.selector-2 {
}
```

关系选择器的符号两边都插入一个空格：

``` css
ul > li {
}
```

超链接状态伪类选择器的顺序为：

``` css
a:link,
a:visited,
a:focus,
a:hover,
a:active {
}
```

属性选择器应该将选择器中的属性值用双引号括起来：

``` css
input[type="radio"] {
}
```

## 声明

* 每条声明语句单独成行
* 冒号 `:` 后插入一个空格
* 声明按首字母顺序排列
* 最后一条声明的结束分号 `;` (右花括号之前)不要省略

``` css
.selector {
  color: #666;
  display: inline-block;
  padding: 10px;
}
```

## 属性

带浏览器前缀的属性按照 `-webkit-`, `-moz-`, `-ms-`, `-o-` 的顺序垂直对齐：

``` css
.selector {
  -webkit-user-select: none;
     -moz-user-select: none;
      -ms-user-select: none;
          user-select: none;
}
```

## 属性值

* 当需要使用引号的时候一律使用双引号
* 当属性值内存在空格时也使用引号括起来

``` css
.selector {
  content: "\00a0";
  font-family: "Microsoft Yahei";
}
```

每个逗号 `,` 后面插入一个空格：

``` css
.selector {
  color: rgba(0, 0, 0, .5);
}
```

### 单位

省略属性值为 0 的单位：

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

### 颜色值

* 统一使用十六进制颜色值
* 使用小写字母
* 当能缩写的时候使用缩写形式：

``` css
.selector {
  color: #fff;
}
```

当颜色值需要不透明度的时候使用 `rgba` 函数，并且指定一个十六进制的颜色值做为后备

``` css
.selector {
  color: #f00;
  color: rgba(255, 0, 0, .5);
}
```

### URL

URL 值省略引号

``` css
background-image: url(i/bg.gif);
```

### 其它

边框的值按照 -width, -style, -color 的顺序书写：

``` css
.selector {
  border: 1px solid #ccc;
}
```

# }
