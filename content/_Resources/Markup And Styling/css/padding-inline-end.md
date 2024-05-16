padding-inline-end
==================

The `padding-inline-end`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the logical inline end padding of an element, which maps to a physical
padding depending on the element\'s writing mode, directionality, and
text orientation.

Try it
------

Syntax
------

[css]

```css
/* <length> values */
padding-inline-end: 10px; /* An absolute length */
padding-inline-end: 1em; /* A length relative to the text size */

/* <percentage> value */
padding-inline-end: 5%; /* A padding relative to the block container's width */

/* Global values */
padding-inline-end: inherit;
padding-inline-end: initial;
padding-inline-end: revert;
padding-inline-end: revert-layer;
padding-inline-end: unset;
```

### Values

[`<length>`](length.md)

:   The size of the padding as a fixed value. Must be nonnegative.

[`<percentage>`](percentage.md)

:   The size of the padding as a percentage, relative to the
    [inline-size](block_and_inline_layout_in_normal_flow.md)
    (*width* in a horizontal language) of the [](containing_block.md). Must be nonnegative.

Description
-----------

The `padding-inline-end` property is defined in the specification as
taking the same values as the [`padding-top`](padding-top.md) property.
However, the physical property it maps to depends on the values set for
[`writing-mode`](writing-mode.md), [`direction`](direction.md), and
[`text-orientation`](text-orientation.md). Therefore, it could map to
[`padding-bottom`](padding-bottom.md), [`padding-right`](padding-right.md), or
[`padding-left`](padding-left.md).

It relates to [`padding-block-start`](padding-block-start.md),
[`padding-block-end`](padding-block-end.md), and
[`padding-inline-start`](padding-inline-start.md), which define the other
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
padding-inline-end = 
  <'padding-top'>  
```

Examples
--------

### Setting inline end padding for vertical text

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
  padding-inline-end: 20px;
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

`padding-inline-end`

692

7979

413

No

5615

12.13

872

6918

414

4814

12.23

10.01.0

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
https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline-end>
