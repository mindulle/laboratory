HTML attribute: elementtiming
=============================

The `elementtiming` attribute is used to indicate that an element is
flagged for tracking by
[`PerformanceObserver`](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserver)
objects using the `"element"` type. For more details, see the
[`PerformanceElementTiming`](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming)
interface.

This attribute may be applied to [`<img>`](../element/img),
[`<image>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/image)
elements inside an
[`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg),
poster images of [`<video>`](../element/video) elements, elements which
have a
[`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image),
and elements containing text nodes, such as a [`<p>`](../element/p).

In the DOM, this attribute is reflected as
[`Element.elementTiming`](https://developer.mozilla.org/en-US/docs/Web/API/Element/elementTiming).

Usage
-----

The value given for `elementtiming` becomes an identifier for the
observed element.

[html]

```html
<img alt="alt" src="img.jpg" elementtiming="label for element" />
```

Good contenders for elements you might want to observe are:

- The main image for an article.
- A blog post title
- Images in a carousel for a shopping site.
- The poster image for the main video on a page.

Examples
--------

[html]

```html
<img alt="Alt for a main blog post image" src="my-massive-image.jpg" elementtiming="Main image">

<p elementtiming="important-text">Some very important information.</p">
```

See also
--------

- [`PerformanceElementTiming`](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming)
- [`Element.elementTiming`](https://developer.mozilla.org/en-US/docs/Web/API/Element/elementTiming)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/elementtiming>>
