prefers-contrast
================

The `prefers-contrast`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](@media.md#media_features) is used to detect whether the user
has requested the web content to be presented with a lower or higher
contrast.

Syntax
------

[`no-preference`](#no-preference)

:   Indicates that the user has made no preference known to the system.
    This keyword value evaluates as false in the Boolean context.

[`more`](#more)

:   Indicates that user has notified the system that they prefer an
    interface that has a higher level of contrast.

[`less`](#less)

:   Indicates that user has notified the system that they prefer an
    interface that has a lower level of contrast.

[`custom`](#custom)

:   Indicates that user has notified the system for using a specific set
    of colors, and the contrast implied by these colors matches neither
    `more` nor `less`. This value will match the color palette specified
    by users of [`forced-colors: active`](forced-colors.md).

User preferences
----------------

Various operating systems do support such preferences and user agents
are likely to rely on the settings provided by the operating system.

Examples
--------

This example has an annoying low contrast by default.

### HTML

[html]

```html
<div class="contrast">low contrast box</div>
```

### CSS

[css]

```css
.contrast {
  width: 100px;
  height: 100px;
  outline: 2px dashed black;
}

@media (prefers-contrast: more) {
  .contrast {
    outline: 2px solid black;
  }
}
```

### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------

  [Media Queries Level 5\
  [\#
  prefers-contrast]](https://drafts.csswg.org/mediaqueries-5/#prefers-contrast)

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

`prefers-contrast`

96

96

101

No

82

14.1

96

96

101

No

14.5

17.0

See also
--------

- CSS [forced-colors](forced-colors.md) media query

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-contrast>
