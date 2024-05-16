flex-wrap
=========

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `flex-wrap` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets whether flex items are forced onto one line or can wrap
onto multiple lines. If wrapping is allowed, it sets the direction that
lines are stacked.

Try it
------

See [](basic_concepts_of_flexbox.md) for more
properties and information.

Syntax
------

[css]

```css
flex-wrap: nowrap; /* Default value */
flex-wrap: wrap;
flex-wrap: wrap-reverse;

/* Global values */
flex-wrap: inherit;
flex-wrap: initial;
flex-wrap: revert;
flex-wrap: revert-layer;
flex-wrap: unset;
```

The `flex-wrap` property is specified as a single keyword chosen from
the list of values below.

### Values

The following values are accepted:

[`nowrap`](#nowrap)

:   The flex items are laid out in a single line which may cause the
    flex container to overflow. The **cross-start** is either equivalent
    to **start** or **before** depending on the
    [`flex-direction`](flex-direction.md) value. This is the default value.

[`wrap`](#wrap)

:   The flex items break into multiple lines. The **cross-start** is
    either equivalent to **start** or **before** depending
    `flex-direction` value and the **cross-end** is the opposite of the
    specified **cross-start**.

[`wrap-reverse`](#wrap-reverse)

:   Behaves the same as `wrap` but **cross-start** and **cross-end** are
    permuted.

Formal definition
-----------------

  ---------------------------------- -----------------
  [Initial value](initial_value.md)     `nowrap`
  Applies to                         flex containers
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -----------------

Formal syntax
-------------

```
flex-wrap = 
  nowrap        |
  wrap          |
  wrap-reverse  
```

Examples
--------

### Setting flex container wrap values

#### HTML

[html]

```html
<h4>This is an example for flex-wrap:wrap</h4>
<div class="content">
  <div class="red">1</div>
  <div class="green">2</div>
  <div class="blue">3</div>
</div>
<h4>This is an example for flex-wrap:nowrap</h4>
<div class="content1">
  <div class="red">1</div>
  <div class="green">2</div>
  <div class="blue">3</div>
</div>
<h4>This is an example for flex-wrap:wrap-reverse</h4>
<div class="content2">
  <div class="red">1</div>
  <div class="green">2</div>
  <div class="blue">3</div>
</div>
```

#### CSS

[css]

```css
/* Common Styles */
.content,
.content1,
.content2 {
  color: #fff;
  font: 100 24px/100px sans-serif;
  height: 150px;
  width: 897px;
  text-align: center;
}

.content div,
.content1 div,
.content2 div {
  height: 50%;
  width: 300px;
}
.red {
  background: orangered;
}
.green {
  background: yellowgreen;
}
.blue {
  background: steelblue;
}

/* Flexbox Styles */
.content {
  display: flex;
  flex-wrap: wrap;
}
.content1 {
  display: flex;
  flex-wrap: nowrap;
}
.content2 {
  display: flex;
  flex-wrap: wrap-reverse;
}
```

#### Results

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [CSS Flexible Box Layout Module Level 1\
  [\#
  flex-wrap-property]](https://drafts.csswg.org/css-flexbox/#flex-wrap-property)

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

`flex-wrap`

2921

12

28

11Partial support due to large number of bugs present. See
[Flexbugs](https://github.com/philipwalton/flexbugs).

17

97

≤374.4

2925

52

18

97

2.01.5

See also
--------

- CSS [`flex-flow`](flex-flow.md) shorthand property for the CSS
    `flex-wrap` and [`flex-direction`](flex-direction.md) properties.
- Flexbox Guide: *[](basic_concepts_of_flexbox.md)*
- CSS Flexbox Guide: *[](mastering_wrapping_of_flex_items.md)*

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/flex-wrap>
