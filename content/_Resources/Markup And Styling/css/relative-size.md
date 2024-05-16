\<relative-size\>
=================

The `<relative-size>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](css_types.md) describes relative size keywords. The `<relative-size>`
keywords define a size relative to the computed size of the parent
element. This data type is used in the [`font`](font.md) shorthand and
[`font-size`](font-size.md) properties.

Syntax
------

```
<relative-size> = smaller | larger
```

### Values

The `<relative-size>` data type is defined using a keyword value chosen
from the list below.

[`smaller`](#smaller)

:   A relative size one size smaller than the inherited size.

[`bigger`](#bigger)

:   A relative size one size larger than the inherited size.

Description
-----------

The `<relative-size>` keywords are relative to the current size of the
element. If the inherited size is defined using an
[`<absolute-size>`](absolute-size.md) keyword, the `<relative-size>` value
equates to the adjacent size in the [](absolute-size.md#description). Otherwise, the relative increase or
decrease in size is between 120% and 150%.

Examples
--------

### Comparing the keyword values

[html]

```html
<ul>
  <li class="smaller">font-size: smaller;</li>
  <li>font-size is not specified</li>
  <li class="larger">font-size: larger;</li>
</ul>
```

[css]

```css
li {
  margin-bottom: 0.3em;
}
.smaller {
  font-size: smaller;
}
.larger {
  font-size: larger;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  valdef-font-size-relative-size]](https://drafts.csswg.org/css-fonts/#valdef-font-size-relative-size)

  --------------------------------------------------------------------------------------------------------------

See also
--------

- CSS [`<absolute-size>`](absolute-size.md) data type
- CSS [`font`](font.md) and [`font-size`](font-size.md) properties
- [CSS fonts](css_fonts.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/relative-size>
