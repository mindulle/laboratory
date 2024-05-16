overflow-block
==============

The `overflow-block`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](@media.md#media_features) can be used to test how the output
device handles content that overflows the initial [](containing_block.md) along the block axis.

Syntax
------

The `overflow-block` feature is specified as a keyword value chosen from
the list below.

[`none`](#none)

:   Content that overflows the block axis is not displayed.

[`scroll`](#scroll)

:   Content that overflows the block axis can be seen by scrolling to
    it.

[`optional-paged`](#optional-paged)

:   Content that overflows the block axis can be seen by scrolling to
    it, but page breaks can be manually triggered (such as via
    [`break-inside`](break-inside.md), etc.) to cause the following
    content to display on the following page.

[`paged`](#paged)

:   Content is broken up into discrete pages; content that overflows one
    page in the block axis is displayed on the following page.

Examples
--------

### HTML

[html]

```html
<p>
  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam ac turpis
  eleifend, fringilla velit ac, aliquam tellus. Vestibulum ante ipsum primis in
  faucibus orci luctus et ultrices posuere cubilia Curae; Nunc velit erat,
  tempus id rutrum sed, dapibus ut urna. Integer vehicula nibh a justo imperdiet
  rutrum. Nam faucibus pretium orci imperdiet sollicitudin. Nunc id facilisis
  dui. Proin elementum et massa et feugiat. Integer rutrum ullamcorper eleifend.
  Proin sit amet tincidunt risus. Sed nec augue congue eros accumsan tincidunt
  sed eget ex.
</p>
```

### CSS

[css]

```css
@media (overflow-block: scroll) {
  p {
    color: red;
  }
}
```

### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------

  [Media Queries Level 4\
  [\#
  mf-overflow-block]](https://drafts.csswg.org/mediaqueries/#mf-overflow-block)

  ---------------------------------------------------------------------------------------

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

`overflow-block`

113

113

66

No

99

17

113

113

66

No

17

No

See also
--------

- [Using Media Queries](using_media_queries.md)
- [\@media](@media.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/overflow-block>
