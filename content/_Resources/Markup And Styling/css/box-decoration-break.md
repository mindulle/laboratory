box-decoration-break
====================

The `box-decoration-break`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies how an element\'s [fragments](css_fragmentation.md) should be
rendered when broken across multiple lines, columns, or pages.

Try it
------

The specified value will impact the appearance of the following
properties:

- [`background`](background.md)
- [`border`](border.md)
- [`border-image`](border-image.md)
- [`box-shadow`](box-shadow.md)
- [`clip-path`](clip-path.md)
- [`margin`](margin.md)
- [`padding`](padding.md)

Syntax
------

[css]

```css
/* Keyword values */
box-decoration-break: slice;
box-decoration-break: clone;

/* Global values */
box-decoration-break: inherit;
box-decoration-break: initial;
box-decoration-break: revert;
box-decoration-break: revert-layer;
box-decoration-break: unset;
```

The `box-decoration-break` property is specified as one of the keyword
values listed below.

### Values

[`slice`](#slice)

:   The element is initially rendered as if its box were not fragmented,
    after which the rendering for this hypothetical box is sliced into
    pieces for each line/column/page. Note that the hypothetical box can
    be different for each fragment since it uses its own height if the
    break occurs in the inline direction, and its own width if the break
    occurs in the block direction. See the CSS specification for
    details.

[`clone`](#clone)

:   Each box fragment is rendered independently with the specified
    border, padding, and margin wrapping each fragment. The
    [`border-radius`](border-radius.md), [`border-image`](border-image.md),
    and [`box-shadow`](box-shadow.md) are applied to each fragment
    independently. The background is also drawn independently for each
    fragment, which means that a background image with
    [`background-repeat`](background-repeat.md)`: no-repeat` may
    nevertheless repeat multiple times.

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `slice`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
box-decoration-break = 
  slice  |
  clone  
```

Examples
--------

### Inline box fragments

An inline element that contains line breaks styled with:

[html]

```html
<style>
  .example {
    background: linear-gradient(to bottom right, yellow, green);
    box-shadow:
      8px 8px 10px 0px deeppink,
      -5px -5px 5px 0px blue,
      5px 5px 15px 0px yellow;
    padding: 0em 1em;
    border-radius: 16px;
    border-style: solid;
    margin-left: 10px;
    font: 24px sans-serif;
    line-height: 2;
  }
</style>
…
<span class="example">The<br />quick<br />orange fox</span>
```

This results in:

Adding `box-decoration-break: clone` to the above styles:

[css]

```css
-webkit-box-decoration-break: clone;
box-decoration-break: clone;
```

This one results in:

You can [try the two inline examples
above](https://mdn.dev/archives/media/attachments/2014/07/12/8179/df096e9eb57177d8b7fdcd0c8f64ef18/box-decoration-break-inline.html)
in your browser.

Here\'s an example of an inline element using a large `border-radius`
value. The second `"iM"` has a line-break between the `"i"` and the
`"M"`. For comparison, the first `"iM"` is without line breaks. Note
that if you stack the rendering of the two fragments horizontally next
to each other it will result in the non-fragmented rendering.

[Try the above
example](https://mdn.dev/archives/media/attachments/2014/07/12/8191/7a067e5731355081e856ea02b978ea2e/box-decoration-break-inline-extreme.html)
in your browser.

### Block box fragments

A block element with similar styles as above and no fragmentation
results in:

Fragmenting the above block into three columns results in:

Note that stacking these pieces vertically will result in the
non-fragmented rendering.

Now, the same example but styled with `box-decoration-break: clone`
results in:

Note here that each fragment has an identical replicated border,
box-shadow, and background.

You can [try the block examples
above](https://mdn.dev/archives/media/attachments/2014/07/12/8187/6288bde9d276d78e203c9f8b9a26ff65/box-decoration-break-block.html)
in your browser.

Specifications
--------------

  ----------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------

  [CSS Fragmentation Module Level 3\
  [\#
  break-decoration]](https://drafts.csswg.org/css-break/#break-decoration)

  ----------------------------------------------------------------------------------

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

`box-decoration-break`

22This property is only supported for inline elements.

79This property is only supported for inline elements.

321--32

No

1511.5--15

7This property is only supported for inline elements.

≤37This property is only supported for inline elements.

18This property is only supported for inline elements.

324--32

1411.5--14

7This property is only supported for inline elements.

1.0This property is only supported for inline elements.

See also
--------

- [`break-after`](break-after.md), [`break-before`](break-before.md),
    [`break-inside`](break-inside.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/box-decoration-break>
