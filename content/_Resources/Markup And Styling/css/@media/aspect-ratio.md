aspect-ratio
============

The `aspect-ratio`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](@media.md#media_features) can be used to test the aspect ratio
of the
[viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport).

Syntax
------

The `aspect-ratio` feature is specified as a [`<ratio>`](ratio.md) value
representing the width-to-height aspect ratio of the viewport. It is a
range feature, meaning you can also use the prefixed `min-aspect-ratio`
and `max-aspect-ratio` variants to query minimum and maximum values,
respectively.

Examples
--------

The example below is contained in an
[`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe),
which creates its own viewport. Resize the `<iframe>` to see
`aspect-ratio` in action.

Note that, when none of the media query conditions are true, the
background will turn white because none of the below rules will be
applied to the `<div>` inside the `<iframe>`. See if you can find which
width and height values trigger this!

### HTML

[html]

```html
<div id="inner">
  Watch this element as you resize your viewport's width and height.
</div>
```

### CSS

```css
[css]

```css

/*Minimum aspect ratio */
@media (min-aspect-ratio: 8/5) {
  div {
    background: #9af; /* blue*/
  }
}

/*Maximum aspect ratio */
@media (max-aspect-ratio: 3/2) {
  div {
    background: #9ff; /* cyan*/
  }
}

/*Exact aspect ratio, put it at the bottom to avoid override*/
@media (aspect-ratio: 1/1) {
  div {
    background: #f9a; /*red*/
  }
}

```

### Result

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [Media Queries Level 4\
  [\#
  aspect-ratio]](https://drafts.csswg.org/mediaqueries/#aspect-ratio)

  -----------------------------------------------------------------------------

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

`aspect-ratio`

3

12

3.5

9

10

5

≤37

18

4

10.1

4.2

1.0

See also
--------

- [Using Media Queries](using_media_queries.md)
- [\@media](@media.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/aspect-ratio>
