forced-color-adjust
===================

The `forced-color-adjust` CSS property allows authors to opt certain
elements out of forced colors mode. This then restores the control of
those values to CSS.

Syntax
------

[css]

```css
forced-color-adjust: auto;
forced-color-adjust: none;

/* Global values */
forced-color-adjust: inherit;
forced-color-adjust: initial;
forced-color-adjust: revert;
forced-color-adjust: revert-layer;
forced-color-adjust: unset;
```

The `forced-color-adjust` property\'s value must be one of the following
keywords.

### Values

[`auto`](#auto)

:   The element\'s colors are adjusted by the [user
    agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
    in forced colors mode. This is the default.

[`none`](#none)

:   The element\'s colors are not automatically adjusted by the [user
    agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
    in forced colors mode.

Usage notes
-----------

This property should only be used to makes changes that will support a
user\'s color and contrast requirements. For example, if you become
aware that the color optimizations made by the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
result in a poor experience when in a high contrast or dark mode. Using
this property would enable tweaking of the result in that mode to
provide a better experience. **It should not be used to prevent user
choices being respected**.

Formal definition
-----------------

  ---------------------------------- -----------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements and text
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- -----------------------

Formal syntax
-------------

```
forced-color-adjust = 
  auto                   |
  none                   |
  preserve-parent-color  
```

Examples
--------

### Preserving colors

In the example below the first box will use the color scheme that the
user has set. For example in Windows High Contrast mode black scheme it
will have a black background and white text. The second box will
preserve the site colors set on the `.box` class.

By using the [`forced-colors`](forced-colors.md) media feature you
could add any other optimizations for forced color mode alongside the
`forced-color-adjust` property.

#### CSS

[css]

```css
.box {
  border: 5px solid grey;
  background-color: #ccc;
  width: 300px;
  margin: 20px;
  padding: 10px;
}

@media (forced-colors: active) {
  .forced {
    forced-color-adjust: none;
  }
}
```

#### HTML

[html]

```html
<div class="box">
  <p>This is a box which should use your color preferences.</p>
</div>

<div class="box forced">
  <p>This is a box which should stay the colors set by the site.</p>
</div>
```

#### Result

The following screenshot shows the image above in Windows High Contrast
Mode:

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [CSS Color Adjustment Module Level 1\
  [\#
  forced-color-adjust-prop]](https://drafts.csswg.org/css-color-adjust/#forced-color-adjust-prop)

  ---------------------------------------------------------------------------------------------------------

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

`forced-color-adjust`

89

7912

113

10

75

No

89

89

113

63

No

15.0

See also
--------

- [](applying_color.md)
- [Styling for Windows high contrast with standards for forced
    colors.](https://blogs.windows.com/msedgedev/2020/09/17/styling-for-windows-high-contrast-with-new-standards-for-forced-colors/)
- [`print-color-adjust`](print-color-adjust.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/forced-color-adjust>
