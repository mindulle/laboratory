color
=====

The `color` CSS property sets the foreground [color value](color_value.md)
of an element\'s text and [text decorations](text-decoration.md), and sets
the [`currentcolor`](color_value.md#currentcolor_keyword) value.
`currentcolor` may be used as an indirect value on *other* properties
and is the default for other color properties, such as
[`border-color`](border-color.md).

Try it
------

For an overview of using color in HTML, see [](applying_color.md).

Syntax
------

[css]

```css
/* Keyword values */
color: currentcolor;

/* <named-color> values */
color: red;
color: orange;
color: tan;
color: rebeccapurple;

/* <hex-color> values */
color: #090;
color: #009900;
color: #090a;
color: #009900aa;

/* <rgb()> values */
color: rgb(34, 12, 64, 0.6);
color: rgba(34, 12, 64, 0.6);
color: rgb(34 12 64 / 0.6);
color: rgba(34 12 64 / 0.3);
color: rgb(34 12 64 / 60%);
color: rgba(34.6 12 64 / 30%);

/* <hsl()> values */
color: hsl(30, 100%, 50%, 0.6);
color: hsla(30, 100%, 50%, 0.6);
color: hsl(30 100% 50% / 0.6);
color: hsla(30 100% 50% / 0.6);
color: hsl(30 100% 50% / 60%);
color: hsla(30.2 100% 50% / 60%);

/* <hwb()> values */
color: hwb(90 10% 10%);
color: hwb(90 10% 10% / 0.5);
color: hwb(90deg 10% 10%);
color: hwb(1.5708rad 60% 0%);
color: hwb(0.25turn 0% 40% / 50%);

/* Global values */
color: inherit;
color: initial;
color: revert;
color: revert-layer;
color: unset;
```

The `color` property is specified as a single [`<color>`](color_value.md)
value.

Note that the value must be a uniform [`color`](_Resources/Markup%20And%20Styling/css/color.md). It can\'t be a
[`<gradient>`](gradient.md), which is actually a type of
[`<image>`](_Resources/Markup%20And%20Styling/css/image.md).

### Values

[`<color>`](color_value.md)

:   Sets the color of the textual and decorative parts of the element.

[`currentcolor`](color_value.md#currentcolor_keyword)

:   Sets the color to the element\'s `color` property value. However, if
    set as the value of `color`, `currentcolor` is treated as `inherit`.

Accessibility concerns
----------------------

It is important to ensure that the contrast ratio between the color of
the text and the background the text is placed over is high enough that
people experiencing low vision conditions will be able to read the
content of the page.

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

  ---------------------------------- ------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `canvastext`
  Applies to                         all elements and text. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   computed color
  Animation type                     by computed value type
  ---------------------------------- ------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
color = 
  <color>  
```

Examples
--------

### Making text red

The following are all ways to make a paragraph\'s text red:

[css]

```css
p {
  color: red;
}
p {
  color: #f00;
}
p {
  color: #ff0000;
}
p {
  color: rgb(255, 0, 0);
}
p {
  color: rgb(100%, 0%, 0%);
}
p {
  color: hsl(0, 100%, 50%);
}

/* 50% translucent */
p {
  color: #ff000080;
}
p {
  color: rgba(255, 0, 0, 0.5);
}
p {
  color: hsla(0, 100%, 50%, 0.5);
}
```

Specifications
--------------

  --------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------

  [CSS Color Module Level 4\
  [\#
  the-color-property]](https://drafts.csswg.org/css-color/#the-color-property)

  --------------------------------------------------------------------------------------

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

`color`

1

12

1

3

3.5

1

4.4

18

4

10.1

1

1.0

See also
--------

- The [`<color>`](color_value.md) data type
- Other color-related properties:
    [`background-color`](background-color.md),
    [`border-color`](border-color.md), [`outline-color`](outline-color.md),
    [`text-decoration-color`](text-decoration-color.md),
    [`text-emphasis-color`](text-emphasis-color.md),
    [`text-shadow`](text-shadow.md), [`caret-color`](caret-color.md),
    [`column-rule-color`](column-rule-color.md), and
    [`print-color-adjust`](print-color-adjust.md)
- [](applying_color.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/color>
