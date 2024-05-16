CSS media queries
=================

**CSS media queries** are a key component of [responsive
design](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)
that allow you to apply CSS styles depending on the presence or value of
device characteristics.

It\'s common to apply a media query based on the
[viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport)
size so that layout choices can be made for devices with different
screen sizes. For example, you may have a smaller font size for devices
with small screens, increase the padding between paragraphs when a page
is viewed in portrait mode, or increase the size of buttons on
touchscreens.

In [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS), use the
[`@media`](@media.md) [at-rule](at-rule.md) to conditionally apply part of a
style sheet based on the result of a media query. To conditionally apply
an entire style sheet, use [`@import`](@import.md).

When designing reusable HTML components, you may also use [](css_container_queries.md), which allow you to apply styles based
on the size of a containing element rather than the viewport or other
device characteristics.

### Media queries in HTML

In [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML), media
queries can be applied to various elements:

- In the
    [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link)
    element\'s
    [`media`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link#media)
    attribute, they define the media to which a linked resource
    (typically CSS) should be applied.
- In the
    [`<source>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source)
    element\'s
    [`media`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source#media)
    attribute, they define the media to which that source should be
    applied. (This is only valid inside
    [`<picture>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture)
    elements.)
- In the
    [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style)
    element\'s
    [`media`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style#media)
    attribute, they define the media to which the style should be
    applied.

### Media queries in JavaScript

In
[JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript),
you can use the
[`Window.matchMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/matchMedia)
method to test the window against a media query. You can also use
[`MediaQueryList.addListener()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList/addListener)
to be notified whenever the state of a query changes. With this
functionality, your site or app can respond to changes in the device
configuration, orientation, or state.

You can learn more about programmatically using media queries in
[Testing media queries](testing_media_queries.md).

Reference
---------

### At-rules

- [`@import`](@import.md)
- [`@media`](@media.md)

Guides
------

[Using media queries](using_media_queries.md)

:   Introduces media queries, their syntax, and the operators and media
    features which are used to construct media query expressions.

[Testing media queries programmatically](testing_media_queries.md)

:   Describes how to use media queries in your JavaScript code to
    determine the state of a device, and to set up listeners that notify
    your code when the results of media queries change (such as when the
    user rotates the screen or resizes the browser).

[Using media queries for accessibility](using_media_queries_for_accessibility.md)

:   Learn how Media Queries can help users understand your website
    better.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Media Queries Level 4\
  ](https://drafts.csswg.org/mediaqueries/)

[CSS Conditional Rules Module Level 3\
  ](https://drafts.csswg.org/css-conditional/)
  -----------------------------------------------------------------------

See also
--------

- [Container queries](css_container_queries.md)
- Use [`@supports`](@supports.md) to apply styles that depend on browser
    support for various CSS technologies.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries>
