# My CSS Style Guide {

For my work

## Table of contents

* [Comments](#comments)
* [Formatting](#formatting)
* [Selectors](#selectors)
* [Declaration](#declaration)
* [Value](#value)
* [Units](#units)
* [Prefix](#prefix)
* [Name](#name)
* [Hacks](#hacks)
* [Tips](#tips)

## Comments

1. Use space

``` css
.selector {
  margin: .5em; /* comment */
}
```

## Formatting

1. Use 2 spaces for indentation, never mix spaces and tabs
2. Put a blank line between rule declarations
3. Put a space before the opening brace `{` in rule declarations
4. Put closing braces } of rule declarations on a new line
5. Use utf-8
6. When using multiple selectors in a rule declaration, give each selector its own line, and put the `,` character at the end of line

``` css
@charset "utf-8";

@media (min-width: 992px) {
  .selector-1,
  .selector-2 {
    color: rgba(0, 0, 0, .5);
  }
}
```

## Selectors

1. Do not use `div` and `span` elements in selectors
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
  -webkit-box-sizing: border-box;
     -moz-box-sizing: border-box;
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

## Prefix

`-webkit-`, `-moz-`, `-ms-`, `-o-`

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

## Name

1. Use lowercase and dashes
2. Use meaningful names

``` css
.class-name {
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

### No border

Use 0 instead of none to specify that a style has no border:

``` css
.selector {
  border: 0;
}
```

### Block center

``` css
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 800px;
}
```

### Clearfix

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

### Text overflow

``` css
.selector {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
```

### Opacity

``` css
.selector {
  filter: alpha(opacity=30);
  opacity: .3;
}
```

# }
