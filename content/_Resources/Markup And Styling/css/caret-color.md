caret-color
===========

The `caret-color` CSS property sets the color of the **insertion
caret**, the visible marker where the next character typed will be
inserted. This is sometimes referred to as the **text input cursor**.
The caret appears in elements such as
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
or those with the
[`contenteditable`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#contenteditable)
attribute. The caret is typically a thin vertical line that flashes to
help make it more noticeable. By default, it is black, but its color can
be altered with this property.

Try it
------

Note that the insertion caret is only one type of caret. For example,
many browsers have a \"navigation caret,\" which acts similarly to an
insertion caret but can be moved around in non-editable text. On the
other hand, the mouse cursor image shown when hovering over text where
the [`cursor`](cursor.md) property is `auto`, or when hovering over an
element where the `cursor` property is `text` or `vertical-text`, though
it sometimes looks like a caret, is not a caret (it\'s a cursor).

Syntax
------

[css]

```css
/* Keyword values */
caret-color: auto;
caret-color: transparent;
caret-color: currentcolor;

/* <color> values */
caret-color: red;
caret-color: #5729e9;
caret-color: rgb(0 200 0);
caret-color: hsl(228deg 4% 24% / 0.8);

/* Global values */
caret-color: inherit;
caret-color: initial;
caret-color: revert;
caret-color: revert-layer;
caret-color: unset;
```

### Values

[`auto`](#auto)

:   The user agent selects an appropriate color for the caret. This is
    generally [`currentcolor`](color_value.md#currentcolor_keyword), but
    the user agent may choose a different color to ensure good
    visibility and contrast with the surrounding content, taking into
    account the value of `currentcolor`, the background, shadows, and
    other factors.

    **Note:** While user agents may use `currentcolor` (which is usually
    animatable) for the `auto` value, `auto` is not interpolated in
    transitions and animations.

[`<color>`](color_value.md)

:   The color of the caret.

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   `auto` is computed as specified and `<color>` values are computed as defined for the [`color`](_Resources/Markup%20And%20Styling/css/color.md) property.
  Animation type                     a [color](color_value.md#interpolation)
  ---------------------------------- -----------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
caret-color = 
  auto     |
  <color>  
```

Examples
--------

### Setting a custom caret color

#### HTML

[html]

```html
<input value="This field uses a default caret." size="64" />
<input class="custom" value="I have a custom caret color!" size="64" />
<p contenteditable class="custom">
  This paragraph can be edited, and its caret has a custom color as well!
</p>
```

#### CSS

[css]

```css
input {
  caret-color: auto;
  display: block;
  margin-bottom: 0.5em;
}

input.custom {
  caret-color: red;
}

p.custom {
  caret-color: green;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Basic User Interface Module Level 4\
  [\# caret-color]](https://drafts.csswg.org/css-ui/#caret-color)

  -----------------------------------------------------------------------

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

`caret-color`

57

79

53

No

44

11.1

57

57

53

43

11.3While the property is recognized, implementation is incomplete. The
color of the caret does not always match the color set for the element
in focus. See [bug 177489](https://webkit.org/b/177489).

7.0

See also
--------

- The
    [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
    element
- The HTML
    [`contenteditable`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#contenteditable)
    attribute, which can be used to make any element\'s text editable
- [](applying_color.md)
- The [`<color>`](color_value.md) data type
- Other color-related properties: [`color`](_Resources/Markup%20And%20Styling/css/color.md),
    [`background-color`](background-color.md),
    [`border-color`](border-color.md), [`outline-color`](outline-color.md),
    [`text-decoration-color`](text-decoration-color.md),
    [`text-emphasis-color`](text-emphasis-color.md),
    [`text-shadow`](text-shadow.md), [`caret-color`](caret-color.md), and
    [`column-rule-color`](column-rule-color.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color>
