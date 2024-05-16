text-decoration-color
=====================

The `text-decoration-color`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the color of decorations added to text by
[`text-decoration-line`](text-decoration-line.md).

The color applies to decorations, such as underlines, overlines,
strikethroughs, and wavy lines like those used to mark misspellings, in
the scope of the property\'s value.

Try it
------

CSS does not provide a direct mechanism for specifying a unique color
for each line type. This effect can nevertheless be achieved by nesting
elements, applying a different line type to each element (with the
[`text-decoration-line`](text-decoration-line.md) property), and specifying
the line color (with `text-decoration-color`) on a per-element basis.

Syntax
------

[css]

```css
/* <color> values */
text-decoration-color: currentcolor;
text-decoration-color: red;
text-decoration-color: #00ff00;
text-decoration-color: rgba(255, 128, 128, 0.5);
text-decoration-color: transparent;

/* Global values */
text-decoration-color: inherit;
text-decoration-color: initial;
text-decoration-color: revert;
text-decoration-color: revert-layer;
text-decoration-color: unset;
```

### Values

[`<color>`](color_value.md)

:   The color of the line decoration.

Accessibility concerns
----------------------

It is important to ensure that the contrast ratio between the color of
the text, the background the text is placed over, and the text
decoration line is high enough that people experiencing low vision
conditions will be able to read the content of the page. Color contrast
ratio is determined by comparing the luminosity of the text and
background color values.

Color alone should not be used to convey meaning. For example, change of
text and text-decoration-color alone is not enough to indicate a link
has focus.

- [WebAIM: Color Contrast
    Checker](https://webaim.org/resources/contrastchecker/)
- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.3 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `currentcolor`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   computed color
  Animation type                     a [color](color_value.md#interpolation)
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
text-decoration-color = 
  <color>  
```

Examples
--------

### Basic example

[html]

```html
<p>
  This paragraph has <s>some erroneous text</s> inside it that I want to call
  attention to.
</p>
```

[css]

```css
p {
  text-decoration-line: underline;
  text-decoration-color: cyan;
}

s {
  text-decoration-line: line-through;
  text-decoration-color: red;
  text-decoration-style: wavy;
}
```

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------------

  [CSS Text Decoration Module Level 3\
  [\#
  text-decoration-color-property]](https://drafts.csswg.org/css-text-decor/#text-decoration-color-property)

  -------------------------------------------------------------------------------------------------------------------

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

`text-decoration-color`

57

79

366--39

No

44

12.18

57

57

366--39

43

12.28

7.0

See also
--------

- When setting multiple line-decoration properties at once, it may be
    more convenient to use the [`text-decoration`](text-decoration.md)
    shorthand property instead.
- The [`<color>`](color_value.md) data type
- Other color-related properties:
    [`background-color`](background-color.md),
    [`border-color`](border-color.md), [`outline-color`](outline-color.md),
    [`text-decoration-color`](text-decoration-color.md),
    [`text-emphasis-color`](text-emphasis-color.md),
    [`text-shadow`](text-shadow.md), [`caret-color`](caret-color.md), and
    [`column-rule-color`](column-rule-color.md)
- [](applying_color.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-color>
