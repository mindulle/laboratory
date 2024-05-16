text-emphasis-color
===================

The `text-emphasis-color`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the color of emphasis marks. This value can also be set using the
[`text-emphasis`](text-emphasis.md) shorthand.

Try it
------

Syntax
------

[css]

```css
/* Initial value */
text-emphasis-color: currentcolor;

/* <color> */
text-emphasis-color: #555;
text-emphasis-color: blue;
text-emphasis-color: rgba(90, 200, 160, 0.8);
text-emphasis-color: transparent;

/* Global values */
text-emphasis-color: inherit;
text-emphasis-color: initial;
text-emphasis-color: revert;
text-emphasis-color: revert-layer;
text-emphasis-color: unset;
```

### Values

[`<color>`](#color)

:   Defines the color of the emphasis marks. If no color is present, it
    defaults to `currentcolor`.

Formal definition
-----------------

  ---------------------------------- --------------------------------------
  [Initial value](initial_value.md)     `currentcolor`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   computed color
  Animation type                     a [color](color_value.md#interpolation)
  ---------------------------------- --------------------------------------

Formal syntax
-------------

```
text-emphasis-color = 
  <color>  
```

Examples
--------

### Emphasis with a color and custom character

#### CSS

[css]

```css
em {
  text-emphasis-color: green;
  text-emphasis-style: "*";
}
```

#### HTML

[html]

```html
<p>Here's an example:</p>

<em>This has emphasis marks!</em>
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------

  [CSS Text Decoration Module Level 3\
  [\#
  text-emphasis-color-property]](https://drafts.csswg.org/css-text-decor/#text-emphasis-color-property)

  ---------------------------------------------------------------------------------------------------------------

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

`text-emphasis-color`

9925

9979

46

No

8515

77

994.4

9925

46

6814

77

18.01.5

See also
--------

- The [`<color>`](color_value.md) data type
- The other emphasis mark related properties:
    [`text-emphasis-style`](text-emphasis-style.md),
    [`text-emphasis`](text-emphasis.md), and
    [`text-emphasis-position`](text-emphasis-position.md).
- Other color-related properties: [`color`](_Resources/Markup%20And%20Styling/css/color.md),
    [`background-color`](background-color.md),
    [`border-color`](border-color.md), [`outline-color`](outline-color.md),
    [`text-emphasis-color`](text-emphasis-color.md),
    [`text-shadow`](text-shadow.md), [`caret-color`](caret-color.md), and
    [`column-rule-color`](column-rule-color.md)
- [](applying_color.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-color>
