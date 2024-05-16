flex-flow
=========

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `flex-flow` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[shorthand property](shorthand_properties.md) specifies the direction of a
flex container, as well as its wrapping behavior.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`flex-direction`](flex-direction.md)
- [`flex-wrap`](flex-wrap.md)

Syntax
------

[css]

```css
/* flex-flow: <'flex-direction'> */
flex-flow: row;
flex-flow: row-reverse;
flex-flow: column;
flex-flow: column-reverse;

/* flex-flow: <'flex-wrap'> */
flex-flow: nowrap;
flex-flow: wrap;
flex-flow: wrap-reverse;

/* flex-flow: <'flex-direction'> and <'flex-wrap'> */
flex-flow: row nowrap;
flex-flow: column wrap;
flex-flow: column-reverse wrap-reverse;

/* Global values */
flex-flow: inherit;
flex-flow: initial;
flex-flow: revert;
flex-flow: revert-layer;
flex-flow: unset;
```

### Values

See [`flex-direction`](flex-direction.md) and [`flex-wrap`](flex-wrap.md) for
details on the values.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](flex-direction.md): |
|                                   |     `row`                         |
|                                   | -   [`flex-wrap`](flex-wrap.md):     |
|                                   |     `nowrap`                      |
+-----------------------------------+-----------------------------------+
| Applies to                        | flex containers                   |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](flex-direction.md): |
|                                   |     as specified                  |
|                                   | -   [`flex-wrap`](flex-wrap.md): as  |
|                                   |     specified                     |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](flex-direction.md): |
|                                   |     discrete                      |
|                                   | -   [`flex-wrap`](flex-wrap.md):     |
|                                   |     discrete                      |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
flex-flow = 
  <'flex-direction'>  ||
  <'flex-wrap'>       
```

Examples
--------

### Setting column-reverse and wrap

[css]

```css
element {
  /* Main-axis is the block direction with reversed main-start and main-end. Flex items are laid out in multiple lines */
  flex-flow: column-reverse wrap;
}
```

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [CSS Flexible Box Layout Module Level 1\
  [\#
  flex-flow-property]](https://drafts.csswg.org/css-flexbox/#flex-flow-property)

  ----------------------------------------------------------------------------------------

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

`flex-flow`

2921

12

4928

11

1512.1

97

≤374.4

2925

4928

1412.1

97

2.01.5

See also
--------

- CSS Flexbox Guide: *[](basic_concepts_of_flexbox.md)*
- CSS Flexbox Guide: *[](ordering_flex_items.md)*

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/flex-flow>
