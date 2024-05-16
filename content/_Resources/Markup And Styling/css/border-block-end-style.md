border-block-end-style
======================

The `border-block-end-style`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the style of the logical block-end border of an element, which maps to a
physical border style depending on the element\'s writing mode,
directionality, and text orientation. It corresponds to the
[`border-top-style`](border-top-style.md),
[`border-right-style`](border-right-style.md),
[`border-bottom-style`](border-bottom-style.md), or
[`border-left-style`](border-left-style.md) property depending on the
values defined for [`writing-mode`](writing-mode.md),
[`direction`](direction.md), and [`text-orientation`](text-orientation.md).

Try it
------

Syntax
------

[css]

```css
/* <'border-style'> values */
border-block-end-style: dashed;
border-block-end-style: dotted;
border-block-end-style: groove;

/* Global values */
border-block-end-style: inherit;
border-block-end-style: initial;
border-block-end-style: revert;
border-block-end-style: revert-layer;
border-block-end-style: unset;
```

Related properties are
[`border-block-start-style`](border-block-start-style.md),
[`border-inline-start-style`](border-inline-start-style.md), and
[`border-inline-end-style`](border-inline-end-style.md), which define the
other border styles of the element.

### Values

[`<'border-style'>`](#border-style)

:   The line style of the border. See [`border-style`](border-style.md).

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
border-block-end-style = 
  <'border-top-style'>  
```

Examples
--------

### Dashed border with vertical text

#### HTML

[html]

```html
<div>
  <p class="exampleText">Example text</p>
</div>
```

#### CSS

[css]

```css
div {
  background-color: yellow;
  width: 120px;
  height: 120px;
}

.exampleText {
  writing-mode: vertical-lr;
  border: 5px solid blue;
  border-block-end-style: dashed;
}
```

#### Results

Specifications
--------------

  ----------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  border-style]](https://drafts.csswg.org/css-logical/#border-style)

  ----------------------------------------------------------------------------

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

`border-block-end-style`

69

79

41

No

56

12.1

69

69

41

48

12.2

10.0

See also
--------

- [](css_logical_properties_and_values.md)
- This property maps to one of the physical border properties:
    [`border-top-style`](border-top-style.md),
    [`border-right-style`](border-right-style.md),
    [`border-bottom-style`](border-bottom-style.md), and
    [`border-left-style`](border-left-style.md).
- [`writing-mode`](writing-mode.md), [`direction`](direction.md),
    [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-end-style>
