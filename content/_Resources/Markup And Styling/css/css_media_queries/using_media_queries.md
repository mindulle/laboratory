Using media queries
===================

**Media queries** allow you to apply CSS styles depending on a device\'s
general type (such as print vs. screen) or other characteristics such as
screen resolution or browser
[viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport)
width. Media queries are used for the following:

- To conditionally apply styles with the
    [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
    [`@media`](@media.md) and [`@import`](@import.md)
    [at-rules](at-rule.md).
- To target specific media for the
    [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style),
    [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link),
    [`<source>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source),
    and other [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
    elements with the `media=` attribute.
- To [test and monitor media states](testing_media_queries.md) using the
    [`Window.matchMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/matchMedia)
    and
    [`EventTarget.addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
    methods.

**Note:** The examples on this page use CSS\'s `@media` for illustrative
purposes, but the basic syntax remains the same for all types of media
queries.

Syntax
------

A media query is composed of an optional *media type* and any number of
*media feature* expressions, which may optionally be combined in various
ways using *logical operators*. Media queries are case-insensitive.

- [Media types](@media.md#media_types) define the broad category of
    device for which the media query applies: `all`, `print`, `screen`.
    The type is optional (assumed to be `all`) except when using the
    `not` or `only` logical operators.
- [Media features](@media.md#media_features) describe a specific
    characteristic of the [user
    agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent),
    output device, or environment:
  - [`any-hover`](any-hover.md)
  - [`any-pointer`](any-pointer.md)
  - [`aspect-ratio`](_Resources/Markup%20And%20Styling/css/@media/aspect-ratio.md)
  - [`color`](_Resources/Markup%20And%20Styling/css/@media/color.md)
  - [`color-gamut`](color-gamut.md)
  - [`color-index`](color-index.md)
  - [`device-aspect-ratio`](device-aspect-ratio.md)
        [Deprecated]
  - [`device-height`](device-height.md)
        [Deprecated]
  - [`device-width`](device-width.md)
        [Deprecated]
  - [`display-mode`](display-mode.md)
  - [`dynamic-range`](dynamic-range.md)
  - [`forced-colors`](forced-colors.md)
  - [`grid`](_Resources/Markup%20And%20Styling/css/@media/grid.md)
  - [`height`](_Resources/Markup%20And%20Styling/css/@media/height.md)
  - [`hover`](hover.md)
  - [`inverted-colors`](inverted-colors.md)
  - [`monochrome`](monochrome.md)
  - [`orientation`](orientation.md)
  - [`overflow-block`](_Resources/Markup%20And%20Styling/css/@media/overflow-block.md)
  - [`overflow-inline`](_Resources/Markup%20And%20Styling/css/@media/overflow-inline.md)
  - [`pointer`](pointer.md)
  - [`prefers-color-scheme`](prefers-color-scheme.md)
  - [`prefers-contrast`](prefers-contrast.md)
  - [`prefers-reduced-motion`](prefers-reduced-motion.md)
  - [`prefers-reduced-transparency`](prefers-reduced-transparency.md)
        [Experimental]
  - [`resolution`](_Resources/Markup%20And%20Styling/css/@media/resolution.md)
  - [`scripting`](scripting.md)
  - [`update`](update.md)
  - [`video-dynamic-range`](video-dynamic-range.md)
  - [`width`](_Resources/Markup%20And%20Styling/css/@media/width.md).

    For example, the [`hover`](hover.md) feature allows a query
    to test against whether the device supports hovering over elements.
    Media feature expressions test for their presence or value, and are
    entirely optional. Each media feature expression must be surrounded
    by parentheses.
- [Logical operators](@media.md#logical_operators) can be used to
    compose a complex media query: `not`, `and`, and `only`. You can
    also combine multiple media queries into a single rule by separating
    them with commas.

A media query computes to `true` when the media type (if specified)
matches the device on which a document is being displayed *and* all
media feature expressions compute as true. Queries involving unknown
media types are always false.

**Note:** A style sheet with a media query attached to its
[`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link)
tag [will still
download](https://scottjehl.github.io/CSS-Download-Tests/) even if the
query returns `false`, the download will happen but the priority of
downloading will be much lower. Nevertheless, its contents will not
apply unless and until the result of the query changes to `true`. You
can read why this happens in Tomayac\'s blog [Why Browser Download
Stylesheet with Non-Matching Media
Queries](https://medium.com/@tomayac/why-browsers-download-stylesheets-with-non-matching-media-queries-eb61b91b85a2).

Targeting media types
---------------------

Media types describe the general category of a given device. Although
websites are commonly designed with screens in mind, you may want to
create styles that target special devices such as printers or
audio-based screen readers. For example, this CSS targets printers:

[css]

```css
@media print {
  /* … */
}
```

You can also target multiple devices. For instance, this `@media` rule
uses two media queries to target both screen and print devices:

[css]

```css
@media screen, print {
  /* … */
}
```

See [media type](@media.md#media_types) for a list of all media types.
Because they describe devices in only very broad terms, just a few are
available; to target more specific attributes, use *media features*
instead.

Targeting media features
------------------------

Media features describe the specific characteristics of a given [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent),
output device, or environment. For instance, you can apply specific
styles to widescreen monitors, computers that use mice, or to devices
that are being used in low-light conditions. This example applies styles
when the user\'s *primary* input mechanism (such as a mouse) can hover
over elements:

[css]

```css
@media (hover: hover) {
  /* … */
}
```

Many media features are *range features*, which means they can be
prefixed with \"min-\" or \"max-\" to express \"minimum condition\" or
\"maximum condition\" constraints. For example, this CSS will apply
styles only if your browser\'s
[viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport)
width is equal to or narrower than 1250px:

[css]

```css
@media (max-width: 1250px) {
  /* … */
}
```

If you create a media feature query without specifying a value, the
nested styles will be used as long as the feature\'s value is not zero
(or `none`, in [Level 4](https://drafts.csswg.org/mediaqueries-4/)). For
example, this CSS will apply to any device with a color screen:

[css]

```css
@media (color) {
  /* … */
}
```

If a feature doesn\'t apply to the device on which the browser is
running, expressions involving that media feature are always false.

For more [Media feature](@media.md#media_features) examples, please see
the reference page for each specific feature.

Creating complex media queries
------------------------------

Sometimes you may want to create a media query that depends on multiple
conditions. This is where the *logical operators* come in: `not`, `and`,
and `only`. Furthermore, you can combine multiple media queries into a
*comma-separated list*; this allows you to apply the same styles in
different situations.

In the previous example, we\'ve already seen the `and` operator used to
group a media *type* with a media *feature*. The `and` operator can also
combine multiple media features into a single media query. The `not`
operator, meanwhile, negates a media query, basically reversing its
normal meaning. The `only` operator prevents older browsers from
applying the styles.

**Note:** In most cases, the `all` media type is used by default when no
other type is specified. However, if you use the `not` or `only`
operators, you must explicitly specify a media type.

### Combining multiple types or features

The `and` keyword combines a media feature with a media type *or* other
media features. This example combines two media features to restrict
styles to landscape-oriented devices with a width of at least 30 ems:

[css]

```css
@media (min-width: 30em) and (orientation: landscape) {
  /* … */
}
```

To limit the styles to devices with a screen, you can chain the media
features to the `screen` media type:

[css]

```css
@media screen and (min-width: 30em) and (orientation: landscape) {
  /* … */
}
```

### Testing for multiple queries

You can use a comma-separated list to apply styles when the user\'s
device matches any one of various media types, features, or states. For
instance, the following rule will apply its styles if the user\'s device
has either a minimum height of 680px *or* is a screen device in portrait
mode:

[css]

```css
@media (min-height: 680px), screen and (orientation: portrait) {
  /* … */
}
```

Taking the above example, if the user had a printer with a page height
of 800px, the media statement would return true because the first query
would apply. Likewise, if the user were on a smartphone in portrait mode
with a viewport height of 480px, the second query would apply and the
media statement would still return true.

### Inverting a query\'s meaning

The `not` keyword inverts the meaning of an entire media query. It will
only negate the specific media query it is applied to. (Thus, it will
not apply to every media query in a comma-separated list of media
queries.) The `not` keyword can\'t be used to negate an individual
feature query, only an entire media query. The `not` is evaluated last
in the following query:

[css]

```css
@media not all and (monochrome) {
  /* … */
}
```

This means that the above query is evaluated like this:

[css]

```css
@media not (all and (monochrome)) {
  /* … */
}
```

It wouldn\'t be evaluated like this:

[css]

```css
@media (not all) and (monochrome) {
  /* … */
}
```

As another example, the following media query:

[css]

```css
@media not screen and (color), print and (color) {
  /* … */
}
```

This means that the above query is evaluated like this:

[css]

```css
@media (not (screen and (color))), print and (color) {
  /* … */
}
```

### Improving compatibility with older browsers

The `only` keyword prevents older browsers that do not support media
queries with media features from applying the given styles. *It has no
effect on modern browsers.*

[css]

```css
@media only screen and (color) {
  /* … */
}
```

Syntax improvements in Level 4
------------------------------

The Media Queries Level 4 specification includes some syntax
improvements to make media queries using features that have a \"range\"
type, for example width or height, less verbose. Level 4 adds a *range
context* for writing such queries. For example, using the `max-`
functionality for width we might write the following:

**Note:** The Media Queries Level 4 specification has reasonable support
in modern browsers, but some media features are not well supported. See
the [](@media.md#browser_compatibility) for more details.

[css]

```css
@media (max-width: 30em) {
  /* … */
}
```

In Media Queries Level 4 this can be written as:

[css]

```css
@media (width <= 30em) {
  /* … */
}
```

Using `min-` and `max-` we might test for a width between two values
like so:

[css]

```css
@media (min-width: 30em) and (max-width: 50em) {
  /* … */
}
```

This would convert to the Level 4 syntax as:

[css]

```css
@media (30em <= width <= 50em) {
  /* … */
}
```

Media Queries Level 4 also adds ways to combine media queries using full
boolean algebra with **and**, **not**, and **or**.

### Negating a feature with `not`

Using `not()` around a media feature negates that feature in the query.
For example, `not(hover)` would match if the device had no hover
capability:

[css]

```css
@media (not(hover)) {
  /* … */
}
```

### Testing for multiple features with `or`

You can use `or` to test for a match among more than one feature,
resolving to `true` if any of the features are true. For example, the
following query tests for devices that have a monochrome display or
hover capability:

[css]

```css
@media (not (color)) or (hover) {
  /* … */
}
```

See also
--------

- [\@media](@media.md)
- [Container queries](css_container_queries.md)
- [Testing media queries programmatically](testing_media_queries.md)
- [CSS Animations Between Media
    Queries](https://davidwalsh.name/animate-media-queries)
- [Extended Mozilla media
    features](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions#media_features)
- [Extended WebKit media
    features](https://developer.mozilla.org/en-US/docs/Web/CSS/WebKit_Extensions#media_features)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries>
