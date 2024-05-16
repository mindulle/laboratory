any-hover
=========

The `any-hover` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[media feature](@media.md#media_features) can be used to test whether
*any* available input mechanism can hover over elements.

Syntax
------

The `any-hover` feature is specified as a keyword value chosen from the
list below.

[`none`](#none)

:   None of the available input mechanism(s) can hover conveniently, or
    there is no pointing input mechanism.

[`hover`](#hover)

:   One or more available input mechanisms can conveniently hover over
    elements.

Examples
--------

### Testing whether input methods can hover

#### HTML

[html]

```html
<a href="#">Try hovering over me!</a>
```

#### CSS

```css

[css]

```css

@media (any-hover: hover) {
  a:hover {
    background: yellow;
  }
}

```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Media Queries Level 4\
  [\#
  any-input]](https://drafts.csswg.org/mediaqueries/#any-input)

  -----------------------------------------------------------------------

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

`any-hover`

41

16

64

No

28

9

41

41

64

28

9

5.0

See also
--------

- [the `hover` media feature](hover.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/any-hover>
