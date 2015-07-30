# My CSS Style Guide {

## 字符集

```
@charset "utf-8";
```

## 缩进

* 使用两个空格来缩进代码

``` css
.selector {
  color: #666;
}
```

## 规则

每条规则之间插入一个空行：

``` css
.selector-1 {
  color: #666;
}

.selector-2 {
  color: #999;
}
```

## 选择器

* 每个选择器单独成行
* 使用小写字母
* 选择器和左花括号 `{` 之间插入一个空格
* 右花括号 `}` 单独成行

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

```
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

带浏览器前缀的属性按由多到少的原则垂直对齐：

``` css
.selector {
  -webkit-user-select: none;
     -moz-user-select: none;
      -ms-user-select: none;
          user-select: none;
}
```

## 属性值

需要使用引号的地方使用双引号：

``` css
.selector {
  content: "\00a0";
}
```

逗号 `,` 后面插入一个空格：

``` css
.selector {
  color: rgba(0, 0, 0, .5);
}
```

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

省略绝对值小于 1 的数值小数点前面的 0：

``` css
.selector {
  margin: .5em;
}
```

16 进制颜色值使用小写字母，能简写的时候使用简写形式：

```
.selector {
  color: #fff;
}
```

边框的值按照 -width, -style, -color 的顺序书写：

``` css
.selector {
  border: 1px solid #ccc;
}
```

# }
