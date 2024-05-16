background
==========

The `background` [shorthand](shorthand_properties.md)
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
all background style properties at once, such as color, image, origin
and size, or repeat method. Component properties not set in the
`background` shorthand property value declaration are set to their
default values.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`background-attachment`](background-attachment.md)
- [`background-clip`](background-clip.md)
- [`background-color`](background-color.md)
- [`background-image`](background-image.md)
- [`background-origin`](background-origin.md)
- [`background-position`](background-position.md)
- [`background-repeat`](background-repeat.md)
- [`background-size`](background-size.md)

Syntax
------

[css]

```css
/* Using a <background-color> */
background: green;

/* Using a <bg-image> and <repeat-style> */
background: url("test.jpg") repeat-y;

/* Using a <box> and <background-color> */
background: border-box red;

/* A single image, centered and scaled */
background: no-repeat center/80% url("../img/image.png");

/* Global values */
background: inherit;
background: initial;
background: revert;
background: revert-layer;
background: unset;
```

The `background` property is specified as one or more background layers,
separated by commas.

The syntax of each layer is as follows:

- Each layer may include zero or one occurrences of any of the
    following values:
  - `<attachment>`
  - `<bg-image>`
  - `<position>`
  - `<bg-size>`
  - `<repeat-style>`
- The `<bg-size>` value may only be included immediately after
    `<position>`, separated with the \'/\' character, like this:
    \"`center/80%`\".
- The `<box>` value may be included zero, one, or two times. If
    included once, it sets both [`background-origin`](background-origin.md)
    and [`background-clip`](background-clip.md). If it is included twice,
    the first occurrence sets [`background-origin`](background-origin.md),
    and the second sets [`background-clip`](background-clip.md).
- The `<background-color>` value may only be included in the last
    layer specified.

### Values

[`<attachment>`](#attachment)

:   See [`background-attachment`](background-attachment.md). Default:
    `scroll`.

[`<box>`](#box)

:   See [`background-clip`](background-clip.md) and
    [`background-origin`](background-origin.md). Default: `border-box` and
    `padding-box` respectively.

[`<background-color>`](#background-color)

:   See [`background-color`](background-color.md). Default: `transparent`.

[`<bg-image>`](#bg-image)

:   See [`background-image`](background-image.md). Default: `none`.

[`<position>`](#position)

:   See [`background-position`](background-position.md). Default: 0% 0%.

[`<repeat-style>`](#repeat-style)

:   See [`background-repeat`](background-repeat.md). Default: `repeat`.

[`<bg-size>`](#bg-size)

:   See [`background-size`](background-size.md). Default: `auto`.

The following three lines of CSS are equivalent:

[css]

```css
background: none;
background: transparent;
background: repeat scroll 0% 0% / auto padding-box border-box none transparent;
```

Accessibility concerns
----------------------

Browsers do not provide any special information on background images to
assistive technology. This is important primarily for screen readers, as
a screen reader will not announce its presence and therefore convey
nothing to its users. If the image contains information critical to
understanding the page\'s overall purpose, it is better to describe it
semantically in the document.

- [MDN Understanding WCAG, Guideline 1.1
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.1_%E2%80%94_providing_text_alternatives_for_non-text_content)
- [Understanding Success Criterion 1.1.1 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/2016/NOTE-UNDERSTANDING-WCAG20-20161007/text-equiv-all.html)

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](background-image.md): |
|                                   |     `none`                        |
|                                   | -   [](background-position.md): |
|                                   |     `0% 0%`                       |
|                                   | -   [](background-size.md): |
|                                   |     `auto auto`                   |
|                                   | -   [](background-repeat.md): |
|                                   |     `repeat`                      |
|                                   | -   [](background-origin.md): |
|                                   |     `padding-box`                 |
|                                   | -   [](background-clip.md): |
|                                   |     `border-box`                  |
|                                   | -   [](background-attachment.md): |
|                                   |     `scroll`                      |
|                                   | -   [](background-color.md): |
|                                   |     `transparent`                 |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements. It also applies to  |
|                                   | [                                 |
|                                   | `::first-letter`](::first-letter) |
|                                   | and                               |
|                                   | [`::first-line`](::first-line).   |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| Percentages                       | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](background-position.md): |
|                                   |     refer to the size of the      |
|                                   |     background positioning area   |
|                                   |     minus size of background      |
|                                   |     image; size refers to the     |
|                                   |     width for horizontal offsets  |
|                                   |     and to the height for         |
|                                   |     vertical offsets              |
|                                   | -   [](background-size.md): |
|                                   |     relative to the background    |
|                                   |     positioning area              |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](background-image.md): |
|                                   |     as specified, but with        |
|                                   |     [`url()`](url.md) values made    |
|                                   |     absolute                      |
|                                   | -   [](background-position.md): |
|                                   |     as each of the properties of  |
|                                   |     the shorthand:\               |
|                                   |     -   [](background-position-x.md): |
|                                   |         A list, each item         |
|                                   |         consisting of: an offset  |
|                                   |         given as a combination of |
|                                   |         an absolute length and a  |
|                                   |         percentage, plus an       |
|                                   |         origin keyword            |
|                                   |     -   [](background-position-y.md): |
|                                   |         A list, each item         |
|                                   |         consisting of: an offset  |
|                                   |         given as a combination of |
|                                   |         an absolute length and a  |
|                                   |         percentage, plus an       |
|                                   |         origin keyword            |
|                                   | -   [](background-size.md): |
|                                   |     as specified, but with        |
|                                   |     relative lengths converted    |
|                                   |     into absolute lengths         |
|                                   | -   [](background-repeat.md): |
|                                   |     a list, each item consisting  |
|                                   |     of two keywords, one per      |
|                                   |     dimension                     |
|                                   | -   [](background-origin.md): |
|                                   |     as specified                  |
|                                   | -   [](background-clip.md): |
|                                   |     as specified                  |
|                                   | -   [](background-attachment.md): |
|                                   |     as specified                  |
|                                   | -   [](background-color.md): |
|                                   |     computed color                |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](background-color.md): |
|                                   |     a                             |
|                                   |     [](color_value.md#interpolation) |
|                                   | -   [](background-image.md): |
|                                   |     discrete                      |
|                                   | -   [](background-clip.md): |
|                                   |     a repeatable list             |
|                                   | -   [](background-position.md): |
|                                   |     a repeatable list             |
|                                   | -   [](background-size.md): |
|                                   |     a repeatable list             |
|                                   | -   [](background-repeat.md): |
|                                   |     discrete                      |
|                                   | -   [](background-attachment.md): |
|                                   |     discrete                      |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
background = 
  [ <bg-layer># , ]? <final-bg-layer>  

<bg-layer> = 
  <bg-image>                      ||
  <bg-position> [ / <bg-size> ]?  ||
  <repeat-style>                  ||
  <attachment>                    ||
  <box>                           ||
  <box>                           

<final-bg-layer> = 
  <'background-color'>            ||
  <bg-image>                      ||
  <bg-position> [ / <bg-size> ]?  ||
  <repeat-style>                  ||
  <attachment>                    ||
  <box>                           ||
  <box>                           

<bg-image> = 
  <image>  |
  none     

<bg-position> = 
  [ left | center | right | top | bottom | <length-percentage> ]  |
  [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]  |
  [ center | [ left | right ] <length-percentage>? ] && [ center | [ top | bottom ] <length-percentage>? ]  

<bg-size> = 
  [ <length-percentage [0,∞]> | auto ]  |
  cover                                      |
  contain                                    

<repeat-style> = 
  repeat-x                                     |
  repeat-y                                     |
  [ repeat | space | round | no-repeat ]  

<attachment> = 
  scroll  |
  fixed   |
  local   

<box> = 
  border-box   |
  padding-box  |
  content-box  

<image> = 
  <url>       |
  <gradient>  

<length-percentage> = 
  <length>      |
  <percentage>  

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  
```

Examples
--------

### Setting backgrounds with color keywords and images

#### HTML

[html]

```html
<p class="topbanner">
  Starry sky<br />
  Twinkle twinkle<br />
  Starry sky
</p>
<p class="warning">Here is a paragraph</p>
<p></p>
```

#### CSS

[css]

```css
.warning {
  background: pink;
}

.topbanner {
  background: url("starsolid.gif") #99f repeat-y fixed;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  the-background]](https://drafts.csswg.org/css-backgrounds/#the-background)

  ------------------------------------------------------------------------------------

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

`SVG_image_as_background`

1

12

4

9

9.5

3.1

≤37

18

4

10.1

1

1.0

`background`

1

12

1

4

3.5

1

2

18

4

10.1

1

1.0

`background-clip`

21

12

22

9

15

5.1

3

25

22

14

4

1.5

`background-origin`

21

12

22

9

15

5.1

3

25

22

14

4

1.5

`background-size`

21

12

9

9

21

5.1

3

25

18

14

4

1.5

`multiple_backgrounds`

1

12

3.6

9

10.5

1.3

2

18

4

14

1

1.0

See also
--------

- [`box-decoration-break`](box-decoration-break.md)
- [Using gradients](using_css_gradients.md)
- [](using_multiple_backgrounds.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/background>
