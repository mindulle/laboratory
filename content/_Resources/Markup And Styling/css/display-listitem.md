\<display-listitem\>
====================

The `list-item` keyword causes the element to generate a `::marker`
pseudo-element with the content specified by its
[`list-style`](list-style.md) properties (for example a bullet point)
together with a principal box of the specified type for its own
contents.

Syntax
------

A single value of `list-item` will cause the element to behave like a
list item. This can be used together with
[`list-style-type`](list-style-type.md) and
[`list-style-position`](list-style-position.md).

`list-item` can also be combined with any
[`<display-outside>`](display-outside.md) keyword and the `flow` or
`flow-root` [`<display-inside>`](display-inside.md) keywords.

**Note:** In browsers that support the two-value syntax, if no inner
value is specified it will default to `flow`. If no outer value is
specified, the principal box will have an outer display type of `block`.

Formal syntax
-------------

```
<display-listitem> = 
  <display-outside>?     &&
  [ flow | flow-root ]?  &&
  list-item              

<display-outside> = 
  block   |
  inline  |
  run-in  
```

Examples
--------

### HTML

[html]

```html
<div class="fake-list">I will display as a list item</div>
```

### CSS

[css]

```css
.fake-list {
  display: list-item;
  list-style-position: inside;
}
```

### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [CSS Display Module Level 3\
  [\#
  typedef-display-listitem]](https://drafts.csswg.org/css-display/#typedef-display-listitem)

  ----------------------------------------------------------------------------------------------------

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`display-listitem`

1

12

1

6

7

1

≤37

18

4

14

1

1.0

`legend-support`

71

79

64

No

58

No

71

71

64

50

No

10.0

See also
--------

- [`display`](display.md)
  - [`<display-outside>`](display-outside.md)
  - [`<display-inside>`](display-inside.md)
  - [`<display-internal>`](display-internal.md)
  - [`<display-box>`](display-box.md)
  - [`<display-legacy>`](display-legacy.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/display-listitem>
