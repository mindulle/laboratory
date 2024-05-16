container-type
==============

The **container-type**
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is used
to define the [](css_container_queries.md#naming_containment_contexts) used in
a [container query](css_container_queries.md).

Syntax
------

[css]

```css
/* Keyword values */
container-type: normal;
container-type: size;
container-type: inline-size;

/* Global Values */
container-type: inherit;
container-type: initial;
container-type: revert;
container-type: revert-layer;
container-type: unset;
```

### Values

[`size`](#size)

:   Establishes a query container for container size queries on both the
    inline and block axis in both the [](basic_concepts_of_logical_properties_and_values.md#block_and_inline_dimensions)
    dimensions. Applies layout containment, style containment, and size
    containment to the container.

[`inline-size`](#inline-size)

:   Establishes a query container for dimensional queries on the [](basic_concepts_of_logical_properties_and_values.md#block_and_inline_dimensions)
    of the container. Applies layout, style, and inline-size containment
    to the element.

[`normal`](#normal)

:   The element is not a query container for any container size queries,
    but remains a query container for container style queries.

**Note:** to understand what happens when you apply layout, style, and
size containment to a box, see the [`contain`](contain.md) property.

Formal definition
-----------------

  ---------------------------------- --------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     a [color](color_value.md#interpolation)
  ---------------------------------- --------------------------------------

Formal syntax
-------------

```
container-type = 
  normal       |
  size         |
  inline-size  
```

Examples
--------

### Establishing inline size containment

Given the following HTML example which is a card component with an
image, a title, and some text:

[html]

```html
<div class="container">
  <div class="card">
    <img src="image.png" alt="Cat with two different color eyes" />
    <h2>Card title</h2>
    <p>Card content</p>
  </div>
</div>
```

To create a container context, add the `container-type` property to an
element. The following uses the `inline-size` value to create a
containment context for the [](basic_concepts_of_logical_properties_and_values.md#block_and_inline_dimensions)
of the container:

[css]

```css
.container {
  container-type: inline-size;
}
```

Writing a container query via the [`@container`](@container.md) at-rule
will apply styles to the elements of the container when it is wider than
400px:

[css]

```css
@container (min-width: 400px) {
  .card {
    display: grid;
    grid-template-columns: 2fr 1fr;
  }
}
```

Specifications
--------------

  ----------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------

  [CSS Containment Module Level 3\
  [\#
  container-type]](https://drafts.csswg.org/css-contain-3/#container-type)

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

`container-type`

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

See also
--------

- [CSS container queries](css_container_queries.md)
- [`@container`](@container.md) at-rule
- CSS [`container`](container.md) shorthand property
- CSS [`container-name`](container-name.md) property
- CSS [`content-visibility`](content-visibility.md) property

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/container-type>
