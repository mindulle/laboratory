line-height-step
================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `line-height-step` CSS property sets the step unit for line box
heights. When the property is set, line box heights are rounded up to
the closest multiple of the unit.

Syntax
------

[css]

```css
/* Point values */
line-height-step: 18pt;

/* Global values */
line-height-step: inherit;
line-height-step: initial;
line-height-step: revert;
line-height-step: revert-layer;
line-height-step: unset;
```

The `line-height-step` property is specified as any one of the
following:

- a `<length>`.

### Values

[`<length>`](#length)

:   The specified [`<length>`](length.md) is used in the calculation of the
    line box height step.

Formal definition
-----------------

  ---------------------------------- -------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         block containers
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   absolute [`<length>`](length.md)
  Animation type                     by computed value type
  ---------------------------------- -------------------------------

Formal syntax
-------------

```
line-height-step = 
  <length [0,∞]>  
```

Examples
--------

### Setting step unit for line box height

In the following example, the height of line box in each paragraph is
rounded up to the step unit. The line box in `<h1>` does not fit into
one step unit and thus occupies two, but it is still centered within the
two step unit.

[css]

```css
:root {
  font-size: 12pt;
  --my-grid: 18pt;
  line-height-step: var(--my-grid);
}
h1 {
  font-size: 20pt;
  margin-top: calc(2 * var(--my-grid));
}
```

The result of these rules is shown below in the following screenshot:

Specifications
--------------

  -----------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------

  [CSS Rhythmic Sizing\
  [\#
  line-height-step]](https://drafts.csswg.org/css-rhythm/#line-height-step)

  -----------------------------------------------------------------------------------

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

`line-height-step`

60

79

No

No

47

No

No

60

No

No

No

No

See also
--------

- [`font`](font.md)
- [`font-size`](font-size.md)
- [`line-height`](line-height.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/line-height-step>
