prefers-color-scheme
====================

The `prefers-color-scheme`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](using_media_queries.md#targeting_media_features)
is used to detect if a user has requested light or dark color themes. A
user indicates their preference through an operating system setting
(e.g. light or dark mode) or a user agent setting.

Embedded elements
-----------------

For SVG and iframes, `prefers-color-scheme` lets you set a CSS style for
the SVG or iframe based on the [`color-scheme`](color-scheme.md) of the
parent element in the web page. SVGs must be used embedded (i.e.,
`<img src="circle.svg" alt="circle" />`) as opposed to [inlined in
HTML](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/SVG_In_HTML_Introduction#basic_example).
An example of using `prefers-color-scheme` in SVGs can be found in the
[Color scheme inheritance](#color_scheme_inheritance) section.

Using `prefers-color-scheme` is allowed in
[cross-origin](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy#cross-origin_network_access)
`<svg>` and `<iframe>` elements. Cross-origin elements are elements
retrieved from a different host than the page that is referencing them.
To learn more about SVGs, see the [SVG
documentation](https://developer.mozilla.org/en-US/docs/Web/SVG) and for
more information about iframes, see the [iframe
documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe).

Syntax
------

[`light`](#light)

:   Indicates that user has notified that they prefer an interface that
    has a light theme, or has not expressed an active preference.

[`dark`](#dark)

:   Indicates that user has notified that they prefer an interface that
    has a dark theme.

Examples
--------

### Detecting a dark or light theme

A common usage is to use a light color scheme by default, and then use
`prefers-color-scheme: dark` to override the colors to a darker variant.
It is also possible to do it the other way around.

This example shows both options: Theme A uses light colors, but can be
overridden to dark colors. Theme B uses dark colors, but can be
overridden to light colors. In the end, if the browser supports
`prefers-color-scheme`, both themes will be light or dark.

#### HTML

[html]

```html
<div class="box theme-a">Theme A (initial)</div>
<div class="box theme-a adaptive">Theme A (changed if dark preferred)</div>
<br />

<div class="box theme-b">Theme B (initial)</div>
<div class="box theme-b adaptive">Theme B (changed if light preferred)</div>
```

#### CSS

Theme A (brown) uses a light color scheme by default, but will switch to
a dark scheme based on the media query:

[css]

```css
.theme-a {
  background: #dca;
  color: #731;
}
@media (prefers-color-scheme: dark) {
  .theme-a.adaptive {
    background: #753;
    color: #dcb;
    outline: 5px dashed #000;
  }
}
```

Theme B (blue) uses a dark color scheme by default, but will switch to a
light scheme based on the media query:

[css]

```css
.theme-b {
  background: #447;
  color: #bbd;
}
@media (prefers-color-scheme: light) {
  .theme-b.adaptive {
    background: #bcd;
    color: #334;
    outline: 5px dotted #000;
  }
}
```

#### Result

The left boxes shows Theme A and Theme B as they would appear without
the `prefers-color-scheme` media query. The right boxes show the same
themes, but one of them will be changed to a darker or lighter variant
based on the user\'s active color scheme. The outline of one box will be
dashed or dotted if it was changed based on your browser or operating
systems settings.

### Color scheme inheritance

The following example shows how to use `prefers-color-scheme` with the
[`color-scheme` property](color-scheme.md) inherited from a parent
element. A script is used to set the source of the `<img>` elements and
their `alt` attributes. This would normally be done in HTML as
`<img src="circle.svg" alt="circle" />`.

You should see three circles, with one drawn in a different color. The
first circle inherits the `color-scheme` from the OS and can be toggled
using the system OS\'s theme switcher.

The second and third circles inherit the `color-scheme` from the
embedding element; the `@media` query allows setting styles of the SVG
content based on the parent element\'s `color-scheme`. In this case, the
parent element with a `color-scheme` CSS property is a `<div>`.

[html]

```html
<div>
  <img />
</div>

<div style="color-scheme: light">
  <img />
</div>
<div style="color-scheme: dark">
  <img />
</div>

<!-- Embed an SVG for all <img> elements -->
<script>
  for (let img of document.querySelectorAll("img")) {
    img.alt = "circle";
    img.src =
      "data:image/svg+xml;base64," +
      btoa(`
      <svg width="32" height="32" viewBox="0 0 32 32" xmlns="http://www.w3.org/2000/svg">
        <style>
          :root 
          @media (prefers-color-scheme: dark) {
            :root 
          }
        </style>
        <circle fill="currentColor" cx="16" cy="16" r="16"/>
      </svg>
    `);
  }
</script>
```

Specifications
--------------

  -----------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------

  [Media Queries Level 5\
  [\#
  prefers-color-scheme]](https://drafts.csswg.org/mediaqueries-5/#prefers-color-scheme)

  -----------------------------------------------------------------------------------------------

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

`prefers-color-scheme`

76

79

67

No

62

12.1

76

76

67

54

13

14.2

`no-preference`

76--80

79--80

67--79

No

62--71

12.1

76--80

76--80

67--79

54

13

14.2

`respects-inherited-scheme`

No

No

105

No

No

No

No

No

105

No

No

No

See also
--------

- [`color-scheme`](color-scheme.md) CSS property
- [`Sec-CH-Prefers-Color-Scheme`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-Prefers-Color-Scheme)
    HTTP Header [User Agent Client
    Hint](https://developer.mozilla.org/en-US/docs/Web/HTTP/Client_hints#user-agent_client_hints)
- [Simulate prefers-color-scheme in
    Firefox](https://firefox-source-docs.mozilla.org/devtools-user/page_inspector/how_to/examine_and_edit_css/index.html#view-media-rules-for-prefers-color-scheme)
    (Firefox Page Inspector \> Examine and edit CSS)
- [Video tutorial: Coding a Dark Mode for your
    Website](https://www.youtube.com/watch?v=jmepqJ5UbuM)
- [Redesigning your product and website for dark
    mode](https://stuffandnonsense.co.uk/blog/redesigning-your-product-and-website-for-dark-mode)
- Changing color schemes in
    [Windows](https://blogs.windows.com/windowsexperience/2019/04/01/windows-10-tip-dark-theme-in-file-explorer/),
    [macOS](https://developer.apple.com/design/human-interface-guidelines/macos/visual-design/dark-mode/),
    [Android](https://www.theverge.com/2019/5/7/18530599/google-android-q-features-hands-on-dark-mode-gestures-accessibility-io-2019),
    or [other
    platforms](https://support.mozilla.org/en-US/questions/1271928).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme>
