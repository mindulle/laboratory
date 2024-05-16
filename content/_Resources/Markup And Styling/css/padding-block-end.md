padding-block-end
=================

The `padding-block-end`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the logical block end padding of an element, which maps to a physical
padding depending on the element\'s writing mode, directionality, and
text orientation.

Try it
------

Syntax
------

[css]

```css
/* <length> values */
padding-block-end: 10px; /* An absolute length */
padding-block-end: 1em; /* A length relative to the text size */

/* <percentage> value */
padding-block-end: 5%; /* A padding relative to the block container's width */

/* Global values */
padding-block-end: inherit;
padding-block-end: initial;
padding-block-end: revert;
padding-block-end: revert-layer;
padding-block-end: unset;
```

### Values

[`<length>`](length.md)

:   The size of the padding as a fixed value. Must be nonnegative.

[`<percentage>`](percentage.md)

:   The size of the padding as a percentage, relative to the inline size
    (*width* in a horizontal language, defined by
    [`writing-mode`](writing-mode.md)) of the [](containing_block.md). Must be nonnegative.

Description
-----------

The `padding-block-end` property is defined in the specification as
taking the same values as the [`padding-top`](padding-top.md) property.
However, the physical property it maps to depends on the values set for
[`writing-mode`](writing-mode.md), [`direction`](direction.md), and
[`text-orientation`](text-orientation.md). Therefore, it could map to
[`padding-bottom`](padding-bottom.md), [`padding-right`](padding-right.md), or
[`padding-left`](padding-left.md).

It relates to [`padding-block-start`](padding-block-start.md),
[`padding-inline-start`](padding-inline-start.md), and
[`padding-inline-end`](padding-inline-end.md), which define the other
paddings of the element.

Formal definition
-----------------

  ---------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         all elements, except `table-row-group`, `table-header-group`, `table-footer-group`, `table-row`, `table-column-group` and `table-column`
  [Inherited](inheritance.md)           no
  Percentages                        logical-width of containing block
  [Computed value](computed_value.md)   as [`<length>`](length.md)
  Animation type                     a [length](length.md#interpolation)
  ---------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
padding-block-end = 
  <'padding-top'>  
```

Examples
--------

### Setting block end padding for vertical text

#### HTML

[html]

```html
<div>
  <p class="exampleText">Example text</p>
</div>
```

#### CSS

[css]

```css
div {
  background-color: yellow;
  width: 120px;
  height: 120px;
}

.exampleText {
  writing-mode: vertical-lr;
  padding-block-end: 20px;
  background-color: #c8c800;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  padding-properties]](https://drafts.csswg.org/css-logical/#padding-properties)

  ----------------------------------------------------------------------------------------

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

`padding-block-end`

69

79

41

No

56

12.1

69

69

41

48

12.2

10.0

See also
--------

- [](css_logical_properties_and_values.md)
- The mapped physical properties: [`padding-top`](padding-top.md),
    [`padding-right`](padding-right.md),
    [`padding-bottom`](padding-bottom.md), and
    [`padding-left`](padding-left.md)
- [`writing-mode`](writing-mode.md), [`direction`](direction.md),
    [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/padding-block-end>
