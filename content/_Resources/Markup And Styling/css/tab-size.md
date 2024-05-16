tab-size
========

The `tab-size` CSS property is used to customize the width of tab
characters (U+0009).

Try it
------

Syntax
------

[css]

```css
/* <integer> values */
tab-size: 4;
tab-size: 0;

/* <length> values */
tab-size: 10px;
tab-size: 2em;

/* Global values */
tab-size: inherit;
tab-size: initial;
tab-size: revert;
tab-size: revert-layer;
tab-size: unset;
```

### Values

[`<integer>`](integer.md)

:   A multiple of the advance width of the space character (U+0020) to
    be used as the width of tabs. Must be nonnegative.

[`<length>`](length.md)

:   The width of tabs. Must be nonnegative.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------
  [Initial value](initial_value.md)     `8`
  Applies to                         block containers
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   the specified integer or an absolute length
  Animation type                     a [length](length.md#interpolation)
  ---------------------------------- ---------------------------------------------

Formal syntax
-------------

```
tab-size = 
  <number>  |
  <length>  
```

Examples
--------

### Expanding by character count

[css]

```css
pre {
  tab-size: 4; /* Set tab size to 4 characters wide */
}
```

### Collapse tabs

[css]

```css
pre {
  tab-size: 0; /* Remove indentation */
}
```

### Comparing to the default size

This example compares a default tab size with a custom tab size. Note
that [`white-space`](white-space.md) is set to `pre` to prevent the tabs
from collapsing.

#### HTML

[html]

```html
<p>no tab</p>
<p>&#0009;default tab size of 8 characters wide</p>
<p class="custom">&#0009;custom tab size of 3 characters wide</p>
<p>&nbsp;&nbsp;&nbsp;3 spaces, equivalent to the custom tab size</p>
```

#### CSS

[css]

```css
p {
  white-space: pre;
}

.custom {
  tab-size: 3;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------

  [CSS Text Module Level 3\
  [\#
  tab-size-property]](https://drafts.csswg.org/css-text/#tab-size-property)

  -----------------------------------------------------------------------------------

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

`tab-size`

21This property is not yet animatable.

79This property is not yet animatable.

91

4Before Firefox 53, this property was not animatable.

No

1510.5--15

7

4.4

25This property is not yet animatable.

91

4Before Firefox 53, this property was not animatable.

1411--14

7

1.5This property is not yet animatable.

`length`

42

79

53

No

29

13.1

56

42

53

29

13.4

4.0

See also
--------

- [`white-space`](white-space.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/tab-size>
