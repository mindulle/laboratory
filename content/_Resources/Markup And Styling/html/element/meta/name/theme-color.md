theme-color
===========

The `theme-color` value for the [`name`](../../meta#name) attribute of
the [`<meta>`](../../meta) element indicates a suggested color that user
agents should use to customize the display of the page or of the
surrounding user interface. If specified, the
[`content`](../../meta#content) attribute must contain a valid CSS
[`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value).

Example
-------

[html]

```html
<meta name="theme-color" content="#4285f4" />
```

The following image shows the effect that the [`<meta>`](../../meta)
element above will have on a document displayed in Chrome running on an
Android mobile device.

![Image showing the effect of using
theme-color]

*Image credit: from [Icons & Browser
Colors](https://web.dev/icons-and-browser-colors/), created and shared
by Google and used according to terms described in the [Creative Commons
4.0 Attribution License](https://creativecommons.org/licenses/by/4.0/).*

You can provide a media type or query inside the
[`media`](../../meta#media) attribute; the color will then only be set
if the media condition is true. For example:

[html]

```html
<meta name="theme-color" media="(prefers-color-scheme: light)" content="cyan" />
<meta name="theme-color" media="(prefers-color-scheme: dark)" content="black" />
```

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  meta-theme-color]](https://html.spec.whatwg.org/multipage/semantics.html#meta-theme-color)

  ----------------------------------------------------------------------------------------------------

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

`theme-color`

73Chrome uses the color only on installed progressive web apps.

39--72Chrome reports support, but does not actually use the color
anywhere.

79Edge uses the color only on installed progressive web apps.

No

No

No

15

No

80Chrome for Android does not use the color on devices with native dark
mode enabled.

No

No

15

6.2

See also
--------

- [`color-scheme`](https://developer.mozilla.org/en-US/docs/Web/CSS/color-scheme)
    CSS property
- [`prefers-color-scheme`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme)
    media query

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta/name/theme-color>>
