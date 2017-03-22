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

1. Use space.

``` css
/* Block comment
   ========================================================================== */

.selector {
  margin: .5em; /* Inline comment */
}
```

## Formatting

1. Use 2 spaces for indentation, never mix spaces and tabs.
2. Put a blank line between rule declarations.
3. Put a space before the opening brace `{` in rule declarations.
4. Put closing braces `}` of rule declarations on a new line.
5. Use utf-8.
6. When using multiple selectors in a rule declaration, give each selector its own line, and put the `,` character at the end of line.

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

1. Don't use `div` or `span` elements in selectors.
2. Don't use ID selectors.
3. Quote attribute values in selectors.

``` css
label + input[type="radio"] {
  /* ^_^ */
}
```

## Declaration

1. Give each declaration its own line.
2. Put a space after the `:` character.
3. Make sure the declarations are in alphabetical order by the property.
4. Don't omit the semi-colon at the end of the last declaration in a declaration block.

``` css
.selector {
  box-sizing: border-box;
  color: #666;
  display: inline-block;
  padding: 10px;
}
```

## Value

1. Use double quotes.
2. Use lowercase and shorthand hex color values.

``` css
.selector {
  background-image: url(i/bg.gif);
  color: #fff;
  content: "\00a0";
  font-family: "Microsoft Yahei", sans-serif;
}
```

### Units

Where allowed, avoid specifying units for zero-values.

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

except time and percent.

``` css
.selector {
  animation-delay: 0s;
  color: rgba(100%, 0%, 0%, .5);
}
```

Don't prefix property values or color parameters with a leading zero.

``` css
.selector {
  margin: .5em;
}
```

## Vendor prefixes

Use [Autoprefixer](https://twitter.com/autoprefixer) to add vendor prefixes to rules.

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

1. Use lowercase and dashes.
2. Use meaningful names.

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

Use `active` class.

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

### Line height

Add no unit `line-height` to the `body` element.

``` css
body {
  line-height: 1.5;
}
```

### No border

Use 0 instead of none to specify that a style has no border.

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

# }
