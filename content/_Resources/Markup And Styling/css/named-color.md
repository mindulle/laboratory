\<named-color\>
===============

The `<named-color>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](css_types.md) is the name of a color, such as `red`, `blue`, `black`,
or `lightseagreen`. Syntactically, a `<named-color>` is an
[`<ident>`](ident.md).

A `<named-color>` value can be used anywhere a [`<color>`](color_value.md)
can be used.

Syntax
------

[css]

```css
color: red;
color: orange;
color: tan;
color: rebeccapurple;
color: transparent;
```

### Value

Named colors consists of standard colors, the
[`transparent`](#transparent) and
[`currentcolor`](color_value.md#currentcolor_keyword) keywords.

#### Standard colors

Basic colors have standard, easy-to-remember names:

  Keyword     RGB hex value   Sample
  ----------- --------------- --------
  `black`     `#000000`
  `silver`    `#c0c0c0`
  `gray`      `#808080`
  `white`     `#ffffff`
  `maroon`    `#800000`
  `red`       `#ff0000`
  `purple`    `#800080`
  `fuchsia`   `#ff00ff`
  `green`     `#008000`
  `lime`      `#00ff00`
  `olive`     `#808000`
  `yellow`    `#ffff00`
  `navy`      `#000080`
  `blue`      `#0000ff`
  `teal`      `#008080`
  `aqua`      `#00ffff`

In addition to these 16 colors, about 150 other colors have a keyword
associated to them:

  -------------------------------------------------------------------------------
  Keyword                  RGB hex value                  Sample
  ------------------------ ------------------------------ -----------------------
  `aliceblue`              `#f0f8ff`

  `antiquewhite`           `#faebd7`

  `aqua`                   `#00ffff`

  `aquamarine`             `#7fffd4`

  `azure`                  `#f0ffff`

  `beige`                  `#f5f5dc`

  `bisque`                 `#ffe4c4`

  `black`                  `#000000`

  `blanchedalmond`         `#ffebcd`

  `blue`                   `#0000ff`

  `blueviolet`             `#8a2be2`

  `brown`                  `#a52a2a`

  `burlywood`              `#deb887`

  `cadetblue`              `#5f9ea0`

  `chartreuse`             `#7fff00`

  `chocolate`              `#d2691e`

  `coral`                  `#ff7f50`

  `cornflowerblue`         `#6495ed`

  `cornsilk`               `#fff8dc`

  `crimson`                `#dc143c`

  `cyan`\                  `#00ffff` (synonym of `aqua`)  

  `darkblue`               `#00008b`

  `darkcyan`               `#008b8b`

  `darkgoldenrod`          `#b8860b`

  `darkgray`               `#a9a9a9`

  `darkgreen`              `#006400`

  `darkgrey`               `#a9a9a9`

  `darkkhaki`              `#bdb76b`

  `darkmagenta`            `#8b008b`

  `darkolivegreen`         `#556b2f`

  `darkorange`             `#ff8c00`

  `darkorchid`             `#9932cc`

  `darkred`                `#8b0000`

  `darksalmon`             `#e9967a`

  `darkseagreen`           `#8fbc8f`

  `darkslateblue`          `#483d8b`

  `darkslategray`          `#2f4f4f`

  `darkslategrey`          `#2f4f4f`

  `darkturquoise`          `#00ced1`

  `darkviolet`             `#9400d3`

  `deeppink`               `#ff1493`

  `deepskyblue`            `#00bfff`

  `dimgray`                `#696969`

  `dimgrey`                `#696969`

  `dodgerblue`             `#1e90ff`

  `firebrick`              `#b22222`

  `floralwhite`            `#fffaf0`

  `forestgreen`            `#228b22`

  `fuchsia`                `#ff00ff`

  `gainsboro`              `#dcdcdc`

  `ghostwhite`             `#f8f8ff`

  `gold`                   `#ffd700`

  `goldenrod`              `#daa520`

  `gray`                   `#808080`

  `green`                  `#008000`

  `greenyellow`            `#adff2f`

  `grey`                   `#808080` (synonym of `gray`)  

  `honeydew`               `#f0fff0`

  `hotpink`                `#ff69b4`

  `indianred`              `#cd5c5c`

  `indigo`                 `#4b0082`

  `ivory`                  `#fffff0`

  `khaki`                  `#f0e68c`

  `lavender`               `#e6e6fa`

  `lavenderblush`          `#fff0f5`

  `lawngreen`              `#7cfc00`

  `lemonchiffon`           `#fffacd`

  `lightblue`              `#add8e6`

  `lightcoral`             `#f08080`

  `lightcyan`              `#e0ffff`

  `lightgoldenrodyellow`   `#fafad2`

  `lightgray`              `#d3d3d3`

  `lightgreen`             `#90ee90`

  `lightgrey`              `#d3d3d3`

  `lightpink`              `#ffb6c1`

  `lightsalmon`            `#ffa07a`

  `lightseagreen`          `#20b2aa`

  `lightskyblue`           `#87cefa`

  `lightslategray`         `#778899`

  `lightslategrey`         `#778899`

  `lightsteelblue`         `#b0c4de`

  `lightyellow`            `#ffffe0`

  `lime`                   `#00ff00`

  `limegreen`              `#32cd32`

  `linen`                  `#faf0e6`

  `magenta`\               `#ff00ff` (synonym of
                           `fuchsia`)

  `maroon`                 `#800000`

  `mediumaquamarine`       `#66cdaa`

  `mediumblue`             `#0000cd`

  `mediumorchid`           `#ba55d3`

  `mediumpurple`           `#9370db`

  `mediumseagreen`         `#3cb371`

  `mediumslateblue`        `#7b68ee`

  `mediumspringgreen`      `#00fa9a`

  `mediumturquoise`        `#48d1cc`

  `mediumvioletred`        `#c71585`

  `midnightblue`           `#191970`

  `mintcream`              `#f5fffa`

  `mistyrose`              `#ffe4e1`

  `moccasin`               `#ffe4b5`

  `navajowhite`            `#ffdead`

  `navy`                   `#000080`

  `oldlace`                `#fdf5e6`

  `olive`                  `#808000`

  `olivedrab`              `#6b8e23`

  `orange`                 `#ffa500`

  `orangered`              `#ff4500`

  `orchid`                 `#da70d6`

  `palegoldenrod`          `#eee8aa`

  `palegreen`              `#98fb98`

  `paleturquoise`          `#afeeee`

  `palevioletred`          `#db7093`

  `papayawhip`             `#ffefd5`

  `peachpuff`              `#ffdab9`

  `peru`                   `#cd853f`

  `pink`                   `#ffc0cb`

  `plum`                   `#dda0dd`

  `powderblue`             `#b0e0e6`

  `purple`                 `#800080`

  `rebeccapurple`          `#663399`

  `red`                    `#ff0000`

  `rosybrown`              `#bc8f8f`

  `royalblue`              `#4169e1`

  `saddlebrown`            `#8b4513`

  `salmon`                 `#fa8072`

  `sandybrown`             `#f4a460`

  `seagreen`               `#2e8b57`

  `seashell`               `#fff5ee`

  `sienna`                 `#a0522d`

  `silver`                 `#c0c0c0`

  `skyblue`                `#87ceeb`

  `slateblue`              `#6a5acd`

  `slategray`              `#708090`

  `slategrey`              `#708090`

  `snow`                   `#fffafa`

  `springgreen`            `#00ff7f`

  `steelblue`              `#4682b4`

  `tan`                    `#d2b48c`

  `teal`                   `#008080`

  `thistle`                `#d8bfd8`

  `tomato`                 `#ff6347`

  `transparent`            See
                           [transparent](#transparent).

  `turquoise`              `#40e0d0`

  `violet`                 `#ee82ee`

  `wheat`                  `#f5deb3`

  `white`                  `#ffffff`

  `whitesmoke`             `#f5f5f5`

  `yellow`                 `#ffff00`

`yellowgreen`            `#9acd32`
  -------------------------------------------------------------------------------

Initially, in [CSS Level
1](https://www.w3.org/TR/REC-CSS1/#color-units), only 16 basic colors
were defined, with `orange` added in [CSS Level
2](https://www.w3.org/TR/CSS2/syndata.html#value-def-color). Web
designers found this list too short, and browser vendors added numerous
names for colors based on the X11 color names. In [SVG
1.0](https://www.w3.org/TR/2001/REC-SVG-20010904/), then in [CSS Colors
Level 3](https://www.w3.org/TR/css-color-3/#svg-color), these names got
standardized, formally defined, and made uniform (some had different
spellings that are now aliases). They are called *extended color
keywords*, *X11 colors*, or *SVG colors*.

In [CSS Colors Level
4](https://www.w3.org/TR/css-color-4/#named-colors), an additional
color, `rebeccapurple` was added to honor [web pioneer Eric
Meyer](https://meyerweb.com/eric/thoughts/2014/06/19/rebeccapurple/).

### transparent

The `transparent` keyword represents a fully transparent color. This
makes the background behind the colored item completely visible.
Technically, `transparent` is a shortcut for `rgba(0,0,0,0)`.

To prevent unexpected behavior, such as in a [`<gradient>`](gradient.md),
the current CSS spec states that `transparent` should be calculated in
the [alpha-premultiplied color
space](https://www.w3.org/TR/css-color-4/#interpolation-alpha). However,
be aware that older browsers may treat it as black with an alpha value
of `0`.

The `transparent` keyword wasn\'t a true color in CSS Level 2 (Revision
1). It was a special keyword that could be used instead of a regular
`<color>` value on two CSS properties: [`background`](background.md) and
[`border`](border.md). It was essentially added to allow developers to
override an inherited solid color. With the advent of alpha channels in
CSS Colors Level 3, `transparent` was redefined as a true color. It can
now be used wherever a `<color>` value can be used.

Description
-----------

All names specify a color in the [sRGB color
space](https://en.wikipedia.org/wiki/SRGB). Although the names more or
less describe their respective colors, they are essentially artificial,
without a strict rationale behind the terms used.

The color keywords all represent plain, solid colors without
transparency.

Several keywords are aliases for each other:

- `aqua` / `cyan`
- `fuchsia` / `magenta`
- `darkgray` / `darkgrey`
- `darkslategray` / `darkslategrey`
- `dimgray` / `dimgrey`
- `lightgray` / `lightgrey`
- `lightslategray` / `lightslategrey`
- `gray` / `grey`
- `slategray` / `slategrey`

Though many keywords have been adapted from
[X11](https://en.wikipedia.org/wiki/X_Window_System), their RGB values
may differ from the corresponding color on X11 systems since
manufacturers sometimes tailor X11 colors to their specific hardware.

Examples
--------

### Using named colors

#### HTML

[html]

```html
<div id="container">
  <div id="one"></div>
  <div id="two"></div>
  <div id="three"></div>
</div>
```

#### CSS

[css]

```css
#container {
  display: flex;
  justify-content: space-around;
  background-color: darkslateblue;
  padding: 20px;
}

#container > div {
  height: 100px;
  width: 100px;
  margin: 3px;
  border: 2px solid black;
}

#one {
  background-color: red;
}

#two {
  background-color: lavender;
}

#three {
  background-color: transparent;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------

  [CSS Color Module Level 4\
  [\#
  named-colors]](https://drafts.csswg.org/css-color/#named-colors)

  --------------------------------------------------------------------------

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

`named-color`

1

12

1

3Internet Explorer 8 and later support gray color keywords spelled with
an *e* (`grey`, `darkgrey`, `darkslategrey`, `dimgrey`, `lightgrey`, and
`lightslategrey`). Internet Explorer 3 to Internet Explorer 7 only
support the keywords spelled with *a* (`gray`, `darkgray`,
`darkslategray`, `dimgray`, `lightgray`, and `lightslategray`).

3.5

1

≤37

18

4

10.1

1

1.0

`rebeccapurple`

38

12

33

11

25

9

38

38

33

25

8

3.0

See also
--------

- [`<color>`](color_value.md): the data type of whose definition
    `<named-color>` is a constituent part.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/named-color>
