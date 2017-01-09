# My CSS Style Guide {

For my work

## Table of contents

* [Comments](#comments)
* [Formatting](#formatting)
* [Selectors](#selectors)
* [Declaration](#declaration)
* [Value](#value)
* [Units](#units)
* [Vendor Prefixes](#vendor-prefixes)
* [ClassName](#classname)
* [Hacks](#hacks)
* [Tips](#tips)

## Comments

1. Use space

``` css
/* Block comment
   ========================================================================== */

.selector {
  margin: .5em; /* Inline comment */
}
```

## Formatting

1. Use 2 spaces for indentation, never mix spaces and tabs
2. Put a blank line between rule declarations
3. Put a space before the opening brace `{` in rule declarations
4. Put closing braces `}` of rule declarations on a new line
5. Use utf-8
6. When using multiple selectors in a rule declaration, give each selector its own line, and put the `,` character at the end of line

``` css
@charset "utf-8";

@media (min-width: 992px) {
  .selector-1,
  .selector-2 {
    color: rgba(0, 0, 0, .5);
  }

  .selector-3 {
    padding: 10px;
  }
}
```

## Selectors

1. Do not use `div` or `span` elements in selectors
2. Do not use ID selectors
3. Quote attribute values in selectors

``` css
label + input[type="radio"] {
  /* ^_^ */
}
```

## Declaration

1. Give each declaration its own line
2. Put a space after the `:` character
3. Make sure the declarations are in alphabetical order by the property
4. Do not omit the semi-colon at the end of the last declaration in a declaration block

``` css
.selector {
  box-sizing: border-box;
  color: #666;
  display: inline-block;
  padding: 10px;
}
```

## Value

1. Use double quotes
2. Use lowercase and shorthand hex color values

``` css
.selector {
  background-image: url(i/bg.gif);
  color: #fff;
  content: "\00a0";
  font-family: "Microsoft Yahei", sans-serif;
}
```

### Units

Where allowed, avoid specifying units for zero-values

``` css
/* bad */
.selector {
  margin: 0px;
}

/* good */
.selector {
  margin: 0;
}
```

except time:

``` css
.selector {
  transition: all 0s;
}
```

or percent:

``` css
.selector {
  color: rgba(100%, 0%, 0%, .5);
}
```

Don't prefix property values or color parameters with a leading zero

``` css
.selector {
  margin: .5em;
}
```

## Vendor prefixes

Use [Autoprefixer](https://twitter.com/autoprefixer) to add vendor prefixes to rules:

``` css
.selector {
  display: flex;
}
```

will compile to:

``` css
.selector {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex
}
```

## ClassName

1. Use lowercase and dashes
2. Use meaningful names

``` css
/* bad */
.mb {
  /* ^_^ */
}

/* good */
.btn-primary {
  /* ^_^ */
}
```

Use `active` class:

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

IE

``` css
.selector {
  _color: #666;  /* IE 6 */
  *color: #999;  /* IE 6, 7 */
  color: #333\9; /* IE 6, 7, 8, 9, 10 */
}
```

## Tips

### 列表分割线

列表与列表之间有一根分割线

结构：

``` html
<ul>
  <li>List 1</li>
  <li>List 2</li>
  <li>List 3</li>
</ul>
```

1. first-child 伪类

  ``` css
  li {
    border-top: 1px solid #ccc;
  }

  li:first-child {
    border-top: 0;
  }
  ```

  IE 7+ 支持

2. last-child 伪类

  ``` css
  li {
    border-bottom: 1px solid #ccc;
  }

  li:last-child {
    border-bottom: 0;
  }
  ```

  IE 9+ 支持

3. adjacent sibling selector

  ``` css
  li + li {
    border-top: 1px solid #ccc;
  }
  ```

  IE 7+ 支持

### Line height

Add no unit `line-height` to the `body` element:

``` css
body {
  line-height: 1.5;
}
```

### No border

Use 0 instead of none to specify that a style has no border:

``` css
/* bad */
.selector {
  border: none;
}

/* good */
.selector {
  border: 0;
}
```

### 水平居中

1. 固定宽度块级元素

  ``` css
  .selector {
    display: block;
    margin-left: auto;
    margin-right: auto;
    width: 800px;
  }
  ```

2. 行内元素

  ``` css
  .selector {
    text-align: center;
  }
  ```

### 垂直居中

1. 真表格布局

  ``` css
  td {
    height: 200px;
    vertical-align: middle;
  }
  ```

  表格结构：

  ``` html
  <table>
    <tbody>
      <tr><td><div>center</div></td></tr>
    </tbody>
  </table>
  ```

2. 伪表格布局

  使用 `display: table-cell;` 使元素像表格一样呈现，和表格布局相比省掉了很多无聊的元素：

  ``` css
  .selector {
    display: table-cell; /* IE 8+ */
    height: 200px;
    vertical-align: middle;
  }
  ```

3. 行内块级元素

  ``` css
  .wrap {
    height: 200px;
    white-space: nowrap;
  }

  .wrap:before {
    content: " ";
    display: inline-block;
    height: 100%;
    margin-right: -0.25em;
    vertical-align: middle;
  }

  .selector {
    display: inline-block;
    vertical-align: middle;
  }
  ```

  将需要居中的元素包裹起来：

  ``` html
  <div class="wrap"><div class="selector">center</div></div>
  ```

  IE 8+ 支持生成内容伪元素

4. 元素固定高度 50% 定位+负外边距

  ``` css
  .selector {
    height: 200px;
    margin-top: -100px; /* 高度的一半 */
    position: absolute;
    top: 50%;
  }
  ```

5. 元素固定高度零距离定位+自动边距

  ``` css
  .selector {
    bottom: 0;
    height: 200px;
    margin: auto;
    position: absolute;
    top: 0;
  }
  ```

6. 元素不定高度 50% 定位+负位移

  ``` css
  .selector {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
  }
  ```

  IE 9+ 支持 2D 变形

7. 视口高度一半+负位移

  ``` css
  .selector {
    margin-top: 50vh;
    transform: translateY(-50%);
  }
  ```

  IE 9+ 支持 vh 单位

8. Flexbox

  ``` css
  .wrap {
    display: flex;
    height: 200px;
  }

  .selector {
    margin: auto;
  }
  ```

  将需要居中的元素包裹起来：

  ``` html
  <div class="wrap"><div class="selector">center</div></div>
  ```
  
  IE 10+ 支持 flexbox

### 清除浮动

``` css
.clearfix {
  *zoom: 1; /* 如果需要兼容 IE 7- */
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

使用时包裹浮动元素：

``` html
<div class="clearfix">
  <div class="float-left"></div>
  <div class="float-right"></div>
</div>
```

### 单行文本超出显示省略号

``` css
.selector {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
  width: 200px; /* IE 6 */
  word-wrap: normal; /* 如果父元素有设置 word-wrap: break-word; 则需要 */
}
```

### 不透明度

``` css
.selector {
  filter: alpha(opacity=30); /* IE 8- */
  opacity: .3;
}
```

# }
