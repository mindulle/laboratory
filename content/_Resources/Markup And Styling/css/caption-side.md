caption-side
============

The `caption-side`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property puts
the content of a table\'s
[`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption)
on the specified side. The values are relative to the
[`writing-mode`](writing-mode.md) of the table.

Try it
------

Syntax
------

[css]

```css
/* Directional values */
caption-side: top;
caption-side: bottom;

/* Logical values */
caption-side: block-start;
caption-side: block-end;
caption-side: inline-start;
caption-side: inline-end;

/* Global values */
caption-side: inherit;
caption-side: initial;
caption-side: revert;
caption-side: revert-layer;
caption-side: unset;
```

The `caption-side` property is specified as one of the keyword values
listed below.

### Values

[`top`](#top)

:   The caption box should be positioned above the table.

[`bottom`](#bottom)

:   The caption box should be positioned below the table.

[`block-start`](#block-start)

:   The caption box should be positioned at the block start edge of the
    table.

[`block-end`](#block-end)

:   The caption box should be positioned at the block end edge of the
    table.

[`inline-start`](#inline-start)

:   The caption box should be positioned at the inline start edge of the
    table.

[`inline-end`](#inline-end)

:   The caption box should be positioned at the inline end edge of the
    table.

Formal definition
-----------------

  ---------------------------------- ------------------------
  [Initial value](initial_value.md)     `top`
  Applies to                         table-caption elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ------------------------

Formal syntax
-------------

```
caption-side = 
  top     |
  bottom  
```

Examples
--------

### Setting captions above and below

#### HTML

[html]

```html
<table class="top">
  <caption>
    Caption ABOVE the table
  </caption>
  <tr>
    <td>Some data</td>
    <td>Some more data</td>
  </tr>
</table>

<br />

<table class="bottom">
  <caption>
    Caption BELOW the table
  </caption>
  <tr>
    <td>Some data</td>
    <td>Some more data</td>
  </tr>
</table>
```

#### CSS

[css]

```css
.top caption {
  caption-side: top;
}

.bottom caption {
  caption-side: bottom;
}

table {
  border: 1px solid red;
}

td {
  border: 1px solid blue;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------

  [Cascading Style Sheets Level 2 Revision 2 (CSS 2.2) Specification\
  [\#
  propdef-caption-side]](https://drafts.csswg.org/css2/#propdef-caption-side)

[CSS Logical Properties and Values Level 1\
  [\# caption-side]](https://drafts.csswg.org/css-logical/#caption-side)
  -------------------------------------------------------------------------------------

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

`caption-side`

1

12

1

8

4

1

≤37

18

4

14

1

1.0

`non_standard_values`

No

No

1--87

No

No

preview

No

No

4--87

No

No

No

`writing-mode_relative_values`

No

No

42

No

No

No

No

No

42

No

No

No

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/caption-side>
