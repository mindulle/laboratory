container
=========

The **container** [shorthand](shorthand_properties.md)
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
establishes the element as a query container and specifies the name or
name for the [](css_container_queries.md#naming_containment_contexts) used in a
[container query](css_container_queries.md).

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`container-name`](container-name.md)
- [`container-type`](container-type.md)

Syntax
------

[css]

```css
/* <container-name> */
container: my-layout;

/* <container-name> / <container-type> */
container: my-layout / size;

/* Global Values */
container: inherit;
container: initial;
container: revert;
container: revert-layer;
container: unset;
```

### Values

[`<container-name>`](#container-name)

:   A case-sensitive name for the containment context. More details on
    the syntax are covered in the [`container-name`](container-name.md)
    property page.

[`<container-type>`](#container-type)

:   The type of containment context. More details on the syntax are
    covered in the [`container-type`](container-type.md) property page.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](container-name.md): |
|                                   |     `none`                        |
|                                   | -   [](container-type.md): |
|                                   |     `normal`                      |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements                      |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| Percentages                       | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](container-name.md): |
|                                   |     no                            |
|                                   | -   [](container-type.md): |
|                                   |     no                            |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](container-name.md): |
|                                   |     `none` or an ordered list of  |
|                                   |     identifiers                   |
|                                   | -   [](container-type.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](container-name.md): |
|                                   |     Not animatable                |
|                                   | -   [](container-type.md): |
|                                   |     a                             |
|                                   |     [](color_value.md#interpolation) |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
container = 
  <'container-name'> [ / <'container-type'> ]?  
```

Examples
--------

### Establishing inline size containment

Given the following HTML example which is a card component with an
image, a title, and some text:

[html]

```html
<div class="post">
  <div class="card">
    <h2>Card title</h2>
    <p>Card content</p>
  </div>
</div>
```

The explicit way to create a container context is to declare a
`container-type` with an optional `container-name`:

[css]

```css
.post {
  container-type: inline-size;
  container-name: sidebar;
}
```

The `container` shorthand is intended to make this simpler to define in
a single declaration:

[css]

```css
.post {
  container: sidebar / inline-size;
}
```

You can then target that container by name using the
[`@container`](@container.md) at-rule:

[css]

```css
@container sidebar (min-width: 400px) {
  /* <stylesheet> */
}
```

Specifications
--------------

  --------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------

  [CSS Containment Module Level 3\
  [\#
  container-shorthand]](https://drafts.csswg.org/css-contain-3/#container-shorthand)

  --------------------------------------------------------------------------------------------

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

`container`

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
- CSS [`contain`](contain.md) property
- CSS [`container-type`](container-type.md) property
- CSS [`container-name`](container-name.md) property
- CSS [`content-visibility`](content-visibility.md) property

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/container>
