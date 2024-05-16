prefers-reduced-transparency
============================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `prefers-reduced-transparency`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](using_media_queries.md#media_features) is
used to detect if a user has enabled a setting on their device to reduce
the transparent or translucent layer effects used on the device.
Switching on such a setting can help improve contrast and readability
for some users.

Syntax
------

[`no-preference`](#no-preference)

:   Indicates that a user has made no preference known on the device.
    This keyword value evaluates as false in the boolean context.

[`reduce`](#reduce)

:   Indicates that a user has enabled the setting on their device to
    minimize the amount of transparent or translucent layer effects.

User preferences
----------------

Various operating systems provide a preference for reducing
transparency, and user agents are likely to rely on these system
settings. They may also rely on less explicit signals on platforms which
don\'t offer a specific setting.

- In Windows 10/11: Settings \> Personalization \> Colors \>
    Transparency effects.
- In macOS: System Preferences \> Accessibility \> Display \> Reduce
    transparency.
- In iOS: Settings \> Accessibility \> Display & Text Size \> Reduce
    Transparency.

Examples
--------

This example has a translucent box by default. If the setting to reduce
transparency is enabled in the accessibility preferences on your device,
the translucent box becomes more opaque.

### HTML

[html]

```html
<div class="translucent">translucent box</div>
```

### CSS

[css]

```css
.translucent {
  opacity: 0.4;
}

@media (prefers-reduced-transparency) {
  .translucent {
    opacity: 0.8;
  }
}
```

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------

  [Media Queries Level 5\
  [\#
  prefers-reduced-transparency]](https://drafts.csswg.org/mediaqueries-5/#prefers-reduced-transparency)

  ---------------------------------------------------------------------------------------------------------------

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

`prefers-reduced-transparency`

118

118

113

No

104

No

118

118

No

No

No

No

See also
--------

- CSS [prefers-reduced-motion](prefers-reduced-motion.md) media query
- [Using media queries](using_media_queries.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-transparency>
