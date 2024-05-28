::cue-region
============

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `::cue-region`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-element](pseudo-elements.md) matches
[WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
cues within a selected element. This can be used to [style captions and
other
cues](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API#styling_webvtt_cues)
in media with VTT tracks.

[css]

```css
::cue-region {
  color: yellow;
  font-weight: bold;
}
```

The properties are applied to the entire set of cues as if they were a
single unit. The only exception is that `background` and its longhand
properties apply to each cue individually, to avoid creating boxes and
obscuring unexpectedly large areas of the media.

Syntax
------

[css]

```css
::cue-region | ::cue-region(<selector>) {
  /* ... */
}
```

Permitted properties
--------------------

Rules whose selectors include this element may only use the following
CSS properties:

- [`background`](background.md)
- [`background-attachment`](background-attachment.md)
- [`background-clip`](background-clip.md)
- [`background-color`](background-color.md)
- [`background-image`](background-image.md)
- [`background-origin`](background-origin.md)
- [`background-position`](background-position.md)
- [`background-repeat`](background-repeat.md)
- [`background-size`](background-size.md)
- [`color`](_Resources/Markup%20And%20Styling/css/color.md)
- [`font`](font.md)
- [`font-family`](_Resources/Markup%20And%20Styling/css/font-family.md)
- [`font-size`](font-size.md)
- [`font-stretch`](_Resources/Markup%20And%20Styling/css/font-stretch.md)
- [`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md)
- [`font-variant`](font-variant.md)
- [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md)
- [`line-height`](line-height.md)
- [`opacity`](_Resources/Markup%20And%20Styling/css/opacity.md)
- [`outline`](outline.md)
- [`outline-color`](outline-color.md)
- [`outline-style`](outline-style.md)
- [`outline-width`](outline-width.md)
- [`ruby-position`](ruby-position.md)
- [`text-combine-upright`](text-combine-upright.md)
- [`text-decoration`](text-decoration.md)
- [`text-decoration-color`](text-decoration-color.md)
- [`text-decoration-line`](text-decoration-line.md)
- [`text-decoration-style`](text-decoration-style.md)
- [`text-decoration-thickness`](text-decoration-thickness.md)
- [`text-shadow`](text-shadow.md)
- [`visibility`](visibility.md)
- [`white-space`](white-space.md)

Specifications
--------------

**No specification found**

No specification data found for `css.selectors.cue-region`.\
[Check for problems with this page](#on-github) or contribute a missing
`spec_url` to
[mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).
Also make sure the specification is included in
[w3c/browser-specs](https://github.com/w3c/browser-specs).

Browser compatibility
---------------------

See also
--------

- Other
    [WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
    selectors:
  - [`::cue`](::cue)
  - [`:past`](:past)
  - [`:future`](:future)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/::cue-region>
