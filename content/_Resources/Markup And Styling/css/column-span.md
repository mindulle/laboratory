column-span
===========

The `column-span`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property makes
it possible for an element to span across all columns when its value is
set to `all`.

Try it
------

An element that spans more than one column is called a **spanning
element**.

Syntax
------

[css]

```css
/* Keyword values */
column-span: none;
column-span: all;

/* Global values */
column-span: inherit;
column-span: initial;
column-span: revert;
column-span: revert-layer;
column-span: unset;
```

The `column-span` property is specified as one of the keyword values
listed below.

### Values

[`none`](#none)

:   The element does not span multiple columns.

[`all`](#all)

:   The element spans across all columns. Content in the normal flow
    that appears before the element is automatically balanced across all
    columns before the element appears. The element establishes a new
    block formatting context.

Formal definition
-----------------

  ---------------------------------- ------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         in-flow block-level elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ------------------------------

Formal syntax
-------------

```
column-span = 
  none  |
  all   
```

Examples
--------

### Making a heading span columns

In this example, the heading is made to span across all the columns of
the article.

#### HTML

[html]

```html
<article>
  <h2>Header spanning all of the columns</h2>
  <p>
    The h2 should span all the columns. The rest of the text should be
    distributed among the columns.
  </p>
  <p>
    This is a bunch of text split into three columns using the CSS `columns`
    property. The text is equally distributed over the columns.
  </p>
  <p>
    This is a bunch of text split into three columns using the CSS `columns`
    property. The text is equally distributed over the columns.
  </p>
  <p>
    This is a bunch of text split into three columns using the CSS `columns`
    property. The text is equally distributed over the columns.
  </p>
  <p>
    This is a bunch of text split into three columns using the CSS `columns`
    property. The text is equally distributed over the columns.
  </p>
</article>
```

#### CSS

[css]

```css
article {
  columns: 3;
}

h2 {
  column-span: all;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------

  [CSS Multi-column Layout Module Level 1\
  [\#
  column-span]](https://drafts.csswg.org/css-multicol/#column-span)

  ---------------------------------------------------------------------------

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

`column-span`

506

1212

71

10

1511.1

95.1

50≤37

5018

79

1411.1

95

5.01.0

See also
--------

- [](spanning_balancing_columns.md)
- [Inline-level
    elements](https://developer.mozilla.org/en-US/docs/Glossary/Inline-level_content)
- [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/column-span>
