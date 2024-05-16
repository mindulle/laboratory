\@container
===========

The `@container` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[at-rule](at-rule.md) is a conditional group rule that applies styles to a
[](css_container_queries.md#naming_containment_contexts). Style
declarations are filtered by a condition and applied to the container if
the condition is true. The condition is evaluated when the container
changes size.

An optional case-sensitive [`container-name`](container-name.md) can be
provided which filters the set of query containers considered to just
those with a matching query container name. Once an eligible query
container has been selected for an element, each container feature in
the `<container-condition>` is evaluated against that query container.

Syntax
------

The `@container` at-rule has the following syntax:

```
@container <container-condition> {
  <stylesheet>
}
```

For example:

[css]

```css
@container (width > 400px) {
  h2 {
    font-size: 1.5em;
  }
}
```

### Values

[`<container-condition>`](#container-condition)

:   A set of features that are evaluated against the query container
    when the size of the container changes. Styles defined in the
    `<stylesheet>` are applied if the condition is true.

[`<stylesheet>`](#stylesheet)

:   A set of CSS declarations.

### Logical keywords in container queries

Logical keywords can be used to define the container condition:

- `and` combines two or more conditions.
- `or` combines two or more conditions.
- `not` negates the condition. Only one \'not\' condition is allowed
    per container query and cannot be used with the `and` or `or`
    keywords.

[css]

```css
@container (width > 400px) and (height > 400px) {
  /* <stylesheet> */
}

@container (width > 400px) or (height > 400px) {
  /* <stylesheet> */
}

@container not (width < 400px) {
  /* <stylesheet> */
}
```

### Named containment contexts

A containment context can be named using the
[`container-name`](container-name.md) property.

[css]

```css
.post {
  container-name: sidebar;
  container-type: inline-size;
}
```

The shorthand syntax for this is to use [`container`](container.md) in the
form `container: <name> / <type>`, for example:

[css]

```css
.post {
  container: sidebar / inline-size;
}
```

In container queries, the [`container-name`](container-name.md) property is
used to filter the set of containers to those with a matching query
container name:

[css]

```css
@container sidebar (width > 400px) {
  /* <stylesheet> */
}
```

Details about usage and naming restrictions are described in the
[`container-name`](container-name.md) page.

### Descriptors

The following descriptors can be used within the container condition:

[`aspect-ratio`](#aspect-ratio)

:   The [`aspect-ratio`](_Resources/Markup%20And%20Styling/css/aspect-ratio.md) of the container calculated as
    the width to the height of the container expressed as a
    [`<ratio>`](ratio.md) value.

[`block-size`](#block-size)

:   The [`block-size`](block-size.md) of the container expressed as a
    [`<length>`](length.md) value.

[`height`](#height)

:   The height of the container expressed as a [`<length>`](length.md)
    value.

[`inline-size`](#inline-size)

:   The [`inline-size`](inline-size.md) of the container expressed as a
    [`<length>`](length.md) value.

[`orientation`](#orientation)

:   The [orientation](orientation.md) of the container, either
    `landscape` or `portrait`.

[`width`](#width)

:   The width of the container expressed as a [`<length>`](length.md)
    value.

Examples
--------

### Setting styles based on a container\'s size

Consider the following example of a card component with a title and some
text:

[html]

```html
<div class="post">
  <div class="card">
    <h2>Card title</h2>
    <p>Card content</p>
  </div>
</div>
```

A container context can be created using the `container-type` property,
in this case using the `inline-size` value on the `.post` class. You can
then use the `@container` at-rule to apply styles to the element with
the `.card` class in a container that\'s narrower than `650px`.

[css]

```css
/* A container context based on inline size */
.post {
  container-type: inline-size;
}

/* Apply styles if the container is narrower than 650px */
@container (width < 650px) {
  .card {
    width: 50%;
    background-color: gray;
    font-size: 1em;
  }
}
```

### Creating named container contexts

Given the following HTML example which is a card component with a title
and some text:

[html]

```html
<div class="post">
  <div class="card">
    <h2>Card title</h2>
    <p>Card content</p>
  </div>
</div>
```

First, create a container context using the `container-type` and
`container-name` properties. The shorthand syntax for this declaration
is described in the [`container`](container.md) page.

[css]

```css
.post {
  container-type: inline-size;
  container-name: summary;
}
```

Next, target that container by adding the name to the container query:

[css]

```css
@container summary (min-width: 400px) {
  .card {
    font-size: 1.5em;
  }
}
```

### Nested container queries

It\'s not possible to target multiple containers in a single container
query. It is possible to nest container queries which has the same
effect.

The following query evaluates to true and applies the declared style if
the container named `summary` is wider than `400px` and has an ancestor
container wider than `800px`:

[css]

```css
@container summary (min-width: 400px) {
  @container (min-width: 800px) {
    /* <stylesheet> */
  }
}
```

### Style container queries

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

Container queries can also evaluate the computed style of the container
element. The following container query checks if the
[`computed_value`](computed_value.md) of the container element\'s
`--accent-color` is `blue`:

[css]

```css
@container style(--accent-color: blue) {
  /* <stylesheet> */
}
```

**Note:** If a custom property has a value of `blue`, the equivalent
hexidecimal code `#0000ff` will not match unless the property has been
defined as a color with [`@property`](@property.md) so the browser can
properly compare computed values.

Specifications
--------------

  ----------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------

  [CSS Containment Module Level 3\
  [\#
  container-rule]](https://drafts.csswg.org/css-contain-3/#container-rule)

  ----------------------------------------------------------------------------------

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

`@container`

105

105

110

No

91

16

105

105

110

72

16

20.0

`style_queries_for_custom_properties`

111

111

No

No

97

No

111

111

No

No

No

22.0

See also
--------

- [Container queries](css_container_queries.md)
- [`container-name`](container-name.md)
- [`container-type`](container-type.md)
- [`contain`](contain.md)
- [`content-visibility`](content-visibility.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@container>
