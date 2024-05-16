text-shadow
===========

The `text-shadow` CSS property adds shadows to text. It accepts a
comma-separated list of shadows to be applied to the text and any of its
[`decorations`](text-decoration.md). Each shadow is described by some
combination of X and Y offsets from the element, blur radius, and color.

Try it
------

Syntax
------

[css]

```css
/* offset-x | offset-y | blur-radius | color */
text-shadow: 1px 1px 2px black;

/* color | offset-x | offset-y | blur-radius */
text-shadow: #fc0 1px 0 10px;

/* offset-x | offset-y | color */
text-shadow: 5px 5px #558abb;

/* color | offset-x | offset-y */
text-shadow: white 2px 5px;

/* offset-x | offset-y
/* Use defaults for color and blur-radius */
text-shadow: 5px 10px;

/* Global values */
text-shadow: inherit;
text-shadow: initial;
text-shadow: revert;
text-shadow: revert-layer;
text-shadow: unset;
```

This property is specified as a comma-separated list of shadows.

Each shadow is specified as two or three `<length>` values, followed
optionally by a `<color>` value. The first two `<length>` values are the
`<offset-x>` and `<offset-y>` values. The third, optional, `<length>`
value is the `<blur-radius>`. The `<color>` value is the shadow\'s
color.

When more than one shadow is given, shadows are applied front-to-back,
with the first-specified shadow on top.

This property applies to both [`::first-line`](::first-line) and
[`::first-letter`](::first-letter) [pseudo-elements](pseudo-elements.md).

### Values

[`<color>`](color_value.md)

:   Optional. The color of the shadow. It can be specified either before
    or after the offset values. If unspecified, the color\'s value is
    left up to the user agent, so when consistency across browsers is
    desired you should define it explicitly.

[`<offset-x> <offset-y>`](#offset-x_offset-y)

:   Required. These [`<length>`](length.md) values specify the shadow\'s
    distance from the text. `<offset-x>` specifies the horizontal
    distance; a negative value places the shadow to the left of the
    text. `<offset-y>` specifies the vertical distance; a negative value
    places the shadow above the text. If both values are `0`, the shadow
    is placed directly behind the text, although it may be partly
    visible due to the effect of `<blur-radius>`.

[`<blur-radius>`](#blur-radius)

:   Optional. This is a [`<length>`](length.md) value. The higher the
    value, the bigger the blur; the shadow becomes wider and lighter. If
    not specified, it defaults to `0`.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   a color plus three absolute lengths
  Animation type                     a [shadow list](box-shadow.md#interpolation)
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
text-shadow = 
  none                            |
  [ <color>? && <length> ]#  
```

Examples
--------

### Simple shadow

[css]

```css
.red-text-shadow {
  text-shadow: red 0 -2px;
}
```

[html]

```html
<p class="red-text-shadow">
  Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium
  doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore.
</p>
```

### Multiple shadows

[css]

```css
.white-text-with-blue-shadow {
  text-shadow:
    1px 1px 2px black,
    0 0 1em blue,
    0 0 0.2em blue;
  color: white;
  font:
    1.5em Georgia,
    serif;
}
```

[html]

```html
<p class="white-text-with-blue-shadow">
  Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium
  doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore.
</p>
```

Specifications
--------------

  -----------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------

  [CSS Text Decoration Module Level 3\
  [\#
  text-shadow-property]](https://drafts.csswg.org/css-text-decor/#text-shadow-property)

  -----------------------------------------------------------------------------------------------

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

`text-shadow`

2

12

3.5\[\"Firefox versions before 57 have a bug whereby
[`transition`](https://developer.mozilla.org/docs/Web/CSS/transition)s
will not work when transitioning from a `text-shadow` with a color
specified to a `text-shadow` without a color specified ([bug
726550](https://bugzil.la/726550)).\", \"From Firefox 4, the blur radius
is capped at 300 for performance reasons.\", \"Firefox theoretically
supports infinite text-shadows (don\'t try it).\", \"If the `<color>`
value is unspecified, then Firefox uses the value of the element\'s
[`color`](https://developer.mozilla.org/docs/Web/CSS/color)
property.\"\]

10

9.5\[\"Opera supports a maximum of 6-9 text-shadows for performance
reasons. The blur radius is limited to 100px.\", \"Opera 9.5 to 10.1
adheres to the old, reverse painting order (in CSS2, the first specified
shadow is on the bottom).\"\]

1.1\[\"In Safari, any shadows that do not explicitly specify a color are
transparent.\", \"Safari 1.1 to 3.2 only supports one text-shadow
(displays the first shadow of a comma-separated list and ignores the
rest). Safari 4.0 (WebKit 528) and later support multiple
text-shadows.\"\]

37

18

4\[\"Firefox versions before 57 have a bug whereby
[`transition`](https://developer.mozilla.org/docs/Web/CSS/transition)s
will not work when transitioning from a `text-shadow` with a color
specified to a `text-shadow` without a color specified ([bug
726550](https://bugzil.la/726550)).\", \"From Firefox 4, the blur radius
is capped at 300 for performance reasons.\", \"Firefox theoretically
supports infinite text-shadows (don\'t try it).\", \"If the `<color>`
value is unspecified, then Firefox uses the value of the element\'s
[`color`](https://developer.mozilla.org/docs/Web/CSS/color)
property.\"\]

14

1\[\"In Safari, any shadows that do not explicitly specify a color are
transparent.\", \"Safari iOS 1 and 2 only support one text-shadow
(displays the first shadow of a comma-separated list and ignores the
rest). Safari iOS 3 (WebKit 528) and later support multiple
text-shadows.\"\]

1.0

See also
--------

- The [`<color>`](color_value.md) data type (for specifying the shadow
    color)
- [`box-shadow`](box-shadow.md)
- [`drop-shadow()`](drop-shadow.md)
- [](applying_color.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow>
