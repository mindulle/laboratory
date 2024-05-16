\<display-legacy\>
==================

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

CSS 2 used a single-keyword syntax for the `display` property, requiring
separate keywords for block-level and inline-level variants of the same
layout mode. This page details those values.

Syntax
------

Valid `<display-legacy>` values:

[`inline-block`](#inline-block)

:   The element generates a block element box that will be flowed with
    surrounding content as if it were a single inline box (behaving much
    like a replaced element would).

    It is equivalent to `inline flow-root`.

[`inline-table`](#inline-table)

:   The `inline-table` value does not have a direct mapping in HTML. It
    behaves like an HTML
    [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
    element, but as an inline box, rather than a block-level box. Inside
    the table box is a block-level context.

    It is equivalent to `inline table`.

[`inline-flex`](#inline-flex)

:   The element behaves like an inline element and lays out its content
    according to the flexbox model.

    It is equivalent to `inline flex`.

[`inline-grid`](#inline-grid)

:   The element behaves like an inline element and lays out its content
    according to the grid model.

    It is equivalent to `inline grid`.

Formal syntax
-------------

```
<display-legacy> = 
  inline-block  |
  inline-table  |
  inline-flex   |
  inline-grid   
```

Examples
--------

In the below example, we are creating an inline flex container with the
legacy keyword inline-flex.

### HTML

[html]

```html
<div class="container">
  <div>Flex Item</div>
  <div>Flex Item</div>
</div>

Not a flex item
```

### CSS

[css]

```css
.container {
  display: inline-flex;
}
```

### Result

In the new syntax the inline flex container would be created using two
values, inline for the outer display type, and flex for the inner
display type.

[css]

```css
.container {
  display: inline flex;
}
```

Specifications
--------------

  ------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------

  [CSS Display Module Level 3\
  [\#
  typedef-display-legacy]](https://drafts.csswg.org/css-display/#typedef-display-legacy)

  ------------------------------------------------------------------------------------------------

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

`display-legacy`

57

1612

52

10Internet Explorer implements an older version of the specification.

44

10.1

57

57

52

43

10.3

6.0Samsung Internet added this earlier than the corresponding Chrome
version would indicate.

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

`display-legacy`

2921

12

20Firefox 28 added multi-line flexbox support.

118

1615

97

≤374.4

2925

20Firefox 28 added multi-line flexbox support.

1614

97

2.01.5

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

`display-legacy`

1

12

3

8

7

1

≤37

18

4

14

1

1.0

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

`display-legacy`

1

12

1

8

6Until Internet Explorer 8, `inline-block` is only for natural inline
elements.

7

1

≤37

18

4

14

1

1.0

### css.properties.display.inline-block

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.properties.display.inline-table

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.properties.display.inline-flex

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.properties.display.inline-grid

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

See also
--------

- [`display`](display.md)
  - [`<display-outside>`](display-outside.md)
  - [`<display-inside>`](display-inside.md)
  - [`<display-listitem>`](display-listitem.md)
  - [`<display-internal>`](display-internal.md)
  - [`<display-box>`](display-box.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/display-legacy>
