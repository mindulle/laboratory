page-break-inside
=================

**Warning:** This property has been replaced by the
[`break-inside`](break-inside.md) property.

The `page-break-inside` CSS property adjusts page breaks *inside* the
current element.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
page-break-inside: auto;
page-break-inside: avoid;

/* Global values */
page-break-inside: inherit;
page-break-inside: initial;
page-break-inside: revert;
page-break-inside: revert-layer;
page-break-inside: unset;
```

### Values

[`auto`](#auto)

:   Initial value. Automatic page breaks (neither forced nor forbidden).

[`avoid`](#avoid)

:   Avoid page breaks inside the element.

Page break aliases
------------------

The `page-break-inside` property is now a legacy property, replaced by
[`break-inside`](break-inside.md).

For compatibility reasons, `page-break-inside` should be treated by
browsers as an alias of `break-inside`. This ensures that sites using
`page-break-inside` continue to work as designed. A subset of values
should be aliased as follows:

  page-break-inside   break-inside
  ------------------- --------------
  `auto`              `auto`
  `avoid`             `avoid`

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         block-level elements in the normal flow of the root element. User agents may also apply it to other elements like `table-row` elements.
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
page-break-inside = 
  avoid    |
  auto     |
  inherit  
```

Examples
--------

### Avoiding page breaks inside elements

#### HTML

[html]

```html
<div class="page">
  <p>This is the first paragraph.</p>
  <section class="list">
    <span>A list</span>
    <ol>
      <li>one</li>
      <!-- <li>two</li> -->
    </ol>
  </section>
  <ul>
    <li>one</li>
    <!-- <li>two</li> -->
  </ul>
  <p>This is the second paragraph.</p>
  <p>This is the third paragraph, it contains more text.</p>
  <p>
    This is the fourth paragraph. It has a little bit more text than the third
    one.
  </p>
</div>
```

#### CSS

[css]

```css
.page {
  background-color: #8cffa0;
  height: 90px;
  width: 200px;
  columns: 1;
  column-width: 100px;
}

.list,
ol,
ul,
p {
  break-inside: avoid;
}

p {
  background-color: #8ca0ff;
}

ol,
ul,
.list {
  margin: 0.5em 0;
  display: block;
  background-color: orange;
}

p:first-child {
  margin-top: 0;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------

  [CSS Paged Media Module Level 3\
  [\#
  page-break-inside]](https://drafts.csswg.org/css-page/#page-break-inside)

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

`page-break-inside`

1

12

19Until Firefox 25, `page-break-inside: avoid` did not work with the
height of a block.

8

7

1.3

37

18

19Until Firefox 25, `page-break-inside: avoid` did not work with the
height of a block.

14

1

1.0

See also
--------

- [`break-before`](break-before.md), [`break-after`](break-after.md),
    [`break-inside`](break-inside.md)
- [`page-break-after`](page-break-after.md),
    [`page-break-before`](page-break-before.md)
- [`orphans`](orphans.md), [`widows`](widows.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/page-break-inside>
