# My CSS Style Guide {

For my work

## Table of contents

* [Comments](#comments)
* [Formatting](#formatting)
* [Selectors](#selectors)
* [Declarations](#declarations)
* [Values](#values)
* [Vendor Prefixes](#vendor-prefixes)
* [ClassName](#classname)
* [Split](#split)
* [Hacks](#hacks)
* [Vertical Centering](#vertical-centering)

## Comments

``` css
/* ======================================================================
   Block comment
   Block comment
   ====================================================================== */

/* Block comment
   ====================================================================== */

/* Inline comment */

.selector {
  margin: .5em; /* Inline comment */
}
```

## Formatting

1. 2 spaces.

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

1. No `div` or `span`.
2. No ID selectors.

``` css
/* bad */
div,
a span {
  display: none;
}

#id {
  font-size: 14px;
}

.selector-a .selector-b .selector-c .selector-d {
  margin: 0;
}

/* good */
a:hover,
a:focus {
  color: red;
}

label + input[type="radio"] {
  /* ^_^ */
}

.list > li {
  margin-bottom: 2px;
}
```

## Declarations

1. Give each declaration its own line.
1. Put a space after the : character.
1. Make sure the declarations are in alphabetical order by the property.
1. Don't omit the semi-colon at the end of the last declaration in a declaration block.

``` css
.selector {
  box-sizing: border-box;
  color: #666;
  display: inline-block;
  padding: 10px;
}
```

## Values

1. Double quotes.
1. Lowercase.

``` css
.selector {
  background-image: url(i/bg.gif);
  color: #f00;
  font-family: "Microsoft Yahei", sans-serif;
  margin: -.25em;
  transition: all 0s;
}

.selector: before {
  content: "\00a0";
}
```

## Vendor prefixes

Use [Autoprefixer](https://twitter.com/autoprefixer) to add vendor prefixes to rules.

``` css
.selector {
  display: flex;
}
```

will compile to

``` css
.selector {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex
}
```

## ClassName

1. Lowercase and dashes.
1. Meaningful names.

``` css
.btn-primary {
  margin: 0;
}
```

### JavaScript hooks

Use js-* classes to denote behavior (as opposed to style), but keep these classes out of your CSS.

``` html
<div class="js-box"></div>
```

## Split

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

No IE 10-

## Vertical Centering

``` css
.selector {
  position: fixed;
  top: 50%;
  transform: translateY(-50%);
}
```

# }
