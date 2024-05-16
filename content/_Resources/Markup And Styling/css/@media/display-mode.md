display-mode
============

The `display-mode`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](@media.md#media_features) can be used to test the display mode
of an application. You can use it to provide a consistent user
experience between launching a site from a URL and launching it from a
desktop icon.

This feature corresponds to the Web app manifest\'s
[`display`](https://developer.mozilla.org/en-US/docs/Web/Manifest#display)
member. Both apply to the top-level browsing context and any child
browsing contexts. The feature query applies regardless of whether a web
app manifest is present.

Syntax
------

The `display-mode` feature is specified as a keyword value chosen from
the list below.

  Display mode                Description                                                                                                                                                                                                                                                                                                              Fallback display mode
  --------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ -----------------------
  `fullscreen`                All of the available display area is used and no user agent [chrome](https://developer.mozilla.org/en-US/docs/Glossary/Chrome) is shown.                                                                                                                                                                                 `standalone`
  `standalone`                The application will look and feel like a standalone application. This can include the application having a different window, its own icon in the application launcher, etc. In this mode, the user agent will exclude UI elements for controlling navigation, but can include other UI elements such as a status bar.   `minimal-ui`
  `minimal-ui`                The application will look and feel like a standalone application, but will have a minimal set of UI elements for controlling navigation. The elements will vary by browser.                                                                                                                                              `browser`
  `browser`                   The application opens in a conventional browser tab or new window, depending on the browser and platform.                                                                                                                                                                                                                (none)
  `window-controls-overlay`   In this mode, the application looks and feels like a standalone desktop application, and the [Window Controls Overlay](https://developer.mozilla.org/en-US/docs/Web/API/Window_Controls_Overlay_API) feature is enabled.                                                                                                 (none)

Examples
--------

### The CSS is used if the device is at fullscreen

[css]

```css
@media all and (display-mode: fullscreen) {
  body {
    margin: 0;
    border: 5px solid black;
  }
}
```

Specifications
--------------

  -------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------

  [Media Queries Level 5\
  [\#
  display-mode]](https://drafts.csswg.org/mediaqueries-5/#display-mode)

  -------------------------------------------------------------------------------

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

`display-mode`

42

79

47Firefox 47 and later support `display-mode` values `fullscreen` and
`browser`. Firefox 57 added support for `minimal-ui` and `standalone`
values.

No

29

13

42

42

47Only supports the `browser` value, which always reports `true`.

29

12.2

4.0

See also
--------

- [Using Media Queries](using_media_queries.md)
- [\@media](@media.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/display-mode>
