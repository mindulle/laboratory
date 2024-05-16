rgb()
=====

The `rgb()` functional notation expresses a color according to its red,
green, and blue components. An optional alpha component represents the
color\'s transparency.

**Note:** The legacy `rgba()` syntax is an alias for `rgb()`, accepting
the same parameters and behaving in the same way.

Try it
------

Syntax
------

[css]

```css
rgb(255 255 255)
rgb(255 255 255 / .5)
```

The function also accepts a legacy syntax in which all values are
separated with commas.

### Values

Functional notation: `rgb(R G B[ / A])`

[`R`](#r), `G`, `B`

:   Each as a [`<number>`](number.md) between `0` and `255`, a
    [`<percentage>`](percentage.md) between `0%` and `100%`, or the
    keyword `none`, which represent the red, green, and blue channels,
    respectively.

[`A`](#a) [Optional]

:   An [`<alpha-value>`](alpha-value.md) or the keyword `none`, where
    the number `1` corresponds to `100%` (full opacity).

**Note:** This functional notation serializes to sRGB values, and the
values of the red, green, blue components may be rounded in
serialization.

**Note:** See [](color_value.md#missing_color_components) for the effect of
`none`.

### Formal syntax

```
<rgb()> = 
  rgb( [ <percentage> | none ] [ / [ <alpha-value> | none ] ]? )  |
  rgb( [ <number> | none ] [ / [ <alpha-value> | none ] ]? )  |
  rgb( <percentage># , <alpha-value>? )            |
  rgb( <number># , <alpha-value>? )                |
  rgb( [ <percentage> | none ] [ / [ <alpha-value> | none ] ]? )  |
  rgb( [ <number> | none ] [ / [ <alpha-value> | none ] ]? )  

<alpha-value> = 
  <number>      |
  <percentage>  
```

Examples
--------

### Legacy syntax: comma-separated values

For legacy reasons, the `rgb()` function accepts a form in which all
values are separated using commas.

#### HTML

[html]

```html
<div class="space-separated"></div>
<div class="comma-separated"></div>
```

#### CSS

[css]

```css
div {
  width: 100px;
  height: 50px;
  margin: 1rem;
}

div.space-separated {
  background-color: rgb(255 0 0 / 0.5);
}

div.comma-separated {
  background-color: rgb(255, 0, 0, 0.5);
}
```

#### Result

### Legacy syntax: rgba()

The legacy `rgba()` syntax is an alias for `rgb()`.

#### HTML

[html]

```html
<div class="rgb"></div>
<div class="rgba"></div>
```

#### CSS

[css]

```css
div {
  width: 100px;
  height: 50px;
  margin: 1rem;
}

div.rgb {
  background-color: rgb(255 0 0 / 0.5);
}

div.rgba {
  background-color: rgba(255 0 0 / 0.5);
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------

  [CSS Color Module Level 4\
  [\#
  rgb-functions]](https://drafts.csswg.org/css-color/#rgb-functions)

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

`rgb`

1

12

1

4

3.5

1

≤37

18

4

10.1

1

1.0

`alpha_parameter`

65

79

52

No

52

12.1

65

65

52

47

12.2

9.0

`float_values`

66

79

52

No

53

12.1

66

66

52

47

12.2

9.0

`space_separated_parameters`

65

79

52

No

52

12.1

65

65

52

47

12.2

9.0

See also
--------

- The [`<color>`](color_value.md) data type for a list of all color
    notations

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/rgb>
