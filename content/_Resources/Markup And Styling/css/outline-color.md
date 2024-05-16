outline-color
=============

The `outline-color` CSS property sets the color of an element\'s
outline.

Try it
------

Syntax
------

[css]

```css
/* <color> values */
outline-color: #f92525;
outline-color: rgb(30, 222, 121);
outline-color: blue;

/* Keyword value */
outline-color: invert;

/* Global values */
outline-color: inherit;
outline-color: initial;
outline-color: revert;
outline-color: revert-layer;
outline-color: unset;
```

The `outline-color` property is specified as any one of the values
listed below.

### Values

[`<color>`](color_value.md)

:   The color of the outline, specified as a `<color>`.

[`invert`](#invert)

:   To ensure the outline is visible, performs a color inversion of the
    background. Note that browsers are not required to support this
    value; if they don\'t, this keyword is considered invalid.

Description
-----------

An outline is a line that is drawn around an element, outside the
[`border`](border.md). Unlike the element\'s border, the outline is drawn
outside the element\'s frame, and may overlap other content. The border,
on the other hand, will actually alter the page\'s layout to ensure that
it fits without overlapping anything else (unless you explicitly set it
to overlap).

It is often more convenient to use the shorthand property
[`outline`](outline.md) when defining the appearance of an outline.

Accessibility concerns
----------------------

Custom [focus styles](:focus) commonly involve making adjustments to the
[`outline`](outline.md) property. If the color of the outline is adjusted,
it is important to ensure that the contrast ratio between it and the
background the outline is placed over is high enough that people
experiencing low vision conditions will be able to perceive it.

Color contrast ratio is determined by comparing the luminosity of the
text and background color values. In order to meet current [Web Content
Accessibility Guidelines
(WCAG)](https://www.w3.org/WAI/standards-guidelines/wcag/), a ratio of
4.5:1 is required for text content and 3:1 for larger text such as
headings. Large text is defined as 18.66px and [bold](_Resources/Markup%20And%20Styling/css/font-weight.md) or
larger, or 24px or larger.

- [WebAIM: Color Contrast
    Checker](https://webaim.org/resources/contrastchecker/)
- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.3 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `invert`, for browsers supporting it, `currentColor` for the other
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   For the keyword `invert`, the computed value is `invert`. For the color value, if the value is translucent, the computed value will be the `rgba()` corresponding one. If it isn\'t, it will be the `rgb()` corresponding one. The `transparent` keyword maps to `rgba(0,0,0,0)`.
  Animation type                     a [color](color_value.md#interpolation)
  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
outline-color = 
  [ <color> | <image-1D> ]  |
  invert                    

<image-1D> = 
  <stripes()>  

<stripes()> = 
  stripes( <color-stripe># )  

<color-stripe> = 
  <color>                            &&
  [ <length-percentage> | <flex> ]?  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Setting a solid blue outline

#### HTML

[html]

```html
<p>My outline is blue, as you can see.</p>
```

#### CSS

[css]

```css
p {
  outline: 2px solid; /* Set the outline width and style */
  outline-color: #0000ff; /* Make the outline blue */
  margin: 5px;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------

  [CSS Basic User Interface Module Level 4\
  [\#
  outline-color]](https://drafts.csswg.org/css-ui/#outline-color)

  -------------------------------------------------------------------------

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

`outline-color`

1

12

1.51--3.6

8

7

1.2

37

18

4

14

1

1.0

`invert`

No

12--79

1--3

8

7--15

No

No

No

No

No

No

No

See also
--------

- [`outline`](outline.md)
- [`outline-color`](outline-color.md)
- [`outline-style`](outline-style.md)
- [`outline-width`](outline-width.md)
- The [`<color>`](color_value.md) data type
- Other color-related properties: [`color`](_Resources/Markup%20And%20Styling/css/color.md),
    [`background-color`](background-color.md),
    [`border-color`](border-color.md),
    [`text-decoration-color`](text-decoration-color.md),
    [`text-emphasis-color`](text-emphasis-color.md),
    [`text-shadow`](text-shadow.md), [`caret-color`](caret-color.md), and
    [`column-rule-color`](column-rule-color.md)
- [](applying_color.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/outline-color>
