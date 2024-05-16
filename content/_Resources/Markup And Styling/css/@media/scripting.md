scripting
=========

The `scripting` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[media feature](@media.md#media_features) can be used to test whether
scripting (such as JavaScript) is available.

Syntax
------

The `scripting` feature is specified as a keyword value chosen from the
list below.

[`none`](#none)

:   Scripting is completely unavailable on the current document.

[`initial-only`](#initial-only)

:   Scripting is enabled during the initial page load, but not
    afterwards.

[`enabled`](#enabled)

:   Scripting is supported and active on the current document.

Examples
--------

### HTML

[html]

```html
<p class="script-none">You do not have scripting available. :-(</p>
<p class="script-initial-only">
  Your scripting is only enabled during the initial page load. Weird.
</p>
<p class="script-enabled">You have scripting enabled! :-)</p>
```

### CSS

[css]

```css
p {
  color: lightgray;
}

@media (scripting: none) {
  .script-none {
    color: red;
  }
}

@media (scripting: initial-only) {
  .script-initial-only {
    color: red;
  }
}

@media (scripting: enabled) {
  .script-enabled {
    color: red;
  }
}
```

### Result

Specifications
--------------

  -------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------

  [Media Queries Level 5\
  [\#
  scripting]](https://drafts.csswg.org/mediaqueries-5/#scripting)

  -------------------------------------------------------------------------

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

`scripting`

120

120

113

No

No

17

No

No

113

No

17

No

See also
--------

- [\@media](@media.md)
- [Using media queries](using_media_queries.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/scripting>
