border-block-style
==================

The `border-block-style`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the style of the logical block borders of an element, which maps to a
physical border style depending on the element\'s writing mode,
directionality, and text orientation. It corresponds to the
[`border-top-style`](border-top-style.md) and
[`border-bottom-style`](border-bottom-style.md), or
[`border-left-style`](border-left-style.md) and
[`border-right-style`](border-right-style.md) properties depending on the
values defined for [`writing-mode`](writing-mode.md),
[`direction`](direction.md), and [`text-orientation`](text-orientation.md).

Try it
------

The border style in the other dimension can be set with
[`border-inline-style`](border-inline-style.md), which sets
[`border-inline-start-style`](border-inline-start-style.md), and
[`border-inline-end-style`](border-inline-end-style.md).

Syntax
------

[css]

```css
/* <'border-style'> values */
border-block-style: dashed;
border-block-style: dotted;
border-block-style: groove;

/* Global values */
border-block-style: inherit;
border-block-style: initial;
border-block-style: revert;
border-block-style: revert-layer;
border-block-style: unset;
```

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
border-block-style = 
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
  border-block-style: dashed;
}
```

#### Results

Specifications
--------------

  --------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  propdef-border-block-style]](https://drafts.csswg.org/css-logical/#propdef-border-block-style)

  --------------------------------------------------------------------------------------------------------

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

`border-block-style`

87

87

66

No

73

14.1

87

87

66

62

14.5

14.0

See also
--------

- [](css_logical_properties_and_values.md)
- This property maps to one of the physical border properties:
    [`border-top-style`](border-top-style.md),
    [`border-right-style`](border-right-style.md),
    [`border-bottom-style`](border-bottom-style.md), or
    [`border-left-style`](border-left-style.md).
- [`writing-mode`](writing-mode.md), [`direction`](direction.md),
    [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-style>
