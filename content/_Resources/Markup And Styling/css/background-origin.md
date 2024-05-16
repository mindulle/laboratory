background-origin
=================

The `background-origin`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the background\'s origin: from the border start, inside the border, or
inside the padding.

Try it
------

Note that `background-origin` is ignored when
[`background-attachment`](background-attachment.md) is `fixed`.

Syntax
------

[css]

```css
/* Keyword values */
background-origin: border-box;
background-origin: padding-box;
background-origin: content-box;

/* Global values */
background-origin: inherit;
background-origin: initial;
background-origin: revert;
background-origin: revert-layer;
background-origin: unset;
```

The `background-origin` property is specified as one of the keyword
values listed below.

### Values

[`border-box`](#border-box)

:   The background is positioned relative to the border box.

[`padding-box`](#padding-box)

:   The background is positioned relative to the padding box.

[`content-box`](#content-box)

:   The background is positioned relative to the content box.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `padding-box`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     a repeatable list
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
background-origin = 
  <box>#  

<box> = 
  border-box   |
  padding-box  |
  content-box  
```

Examples
--------

### Setting background origins

[css]

```css
.example {
  border: 10px double;
  padding: 10px;
  background: url("image.jpg");
  background-position: center left;
  background-origin: content-box;
}
```

[css]

```css
#example2 {
  border: 4px solid black;
  padding: 10px;
  background: url("image.gif");
  background-repeat: no-repeat;
  background-origin: border-box;
}
```

[css]

```css
div {
  background-image: url("logo.jpg"), url("mainback.png"); /* Applies two images to the background */
  background-position:
    top right,
    0px 0px;
  background-origin: content-box, padding-box;
}
```

### Using two gradients

In this example the box has a thick dotted border. The first gradient
uses the `padding-box` as the `background-origin` and therefore the
background sits inside the border. The second uses the `content-box` and
so only displays behind the content.

[css]

```css
.box {
  margin: 10px 0;
  color: #fff;
  background: linear-gradient(
      90deg,
      rgba(131, 58, 180, 1) 0%,
      rgba(253, 29, 29, 0.6) 60%,
      rgba(252, 176, 69, 1) 100%
    ), radial-gradient(circle, rgba(255, 255, 255, 1) 0%, rgba(0, 0, 0, 1) 28%);
  border: 20px dashed black;
  padding: 20px;
  width: 400px;
  background-origin: padding-box, content-box;
  background-repeat: no-repeat;
}
```

[html]

```html
<div class="box">Hello!</div>
```

Specifications
--------------

  --------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  the-background-origin]](https://drafts.csswg.org/css-backgrounds/#the-background-origin)

  --------------------------------------------------------------------------------------------------

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

`background-origin`

1

1Chrome accepts alternate synonyms to its values: `padding`, `border`,
and `content`.

12

12Since Edge 79, accepts alternate synonyms to its values: `padding`,
`border`, and `content`.

494

1--4Used the `-moz-background-clip: padding | border` syntax.

9In IE 7 and before, Internet explorer was behaving as if
`background-origin: border-box` was set. In Internet Explorer 8, as if
`background-origin: padding-box`, the regular default value, was set.

15Opera accepts alternate synonyms to its values: `padding`, `border`,
and `content`.

10.5

3

3Webkit accepts alternate synonyms to its values: `padding`, `border`,
and `content`.

4

4WebView accepts alternate synonyms to its values: `padding`, `border`,
and `content`.

18

18Chrome accepts alternate synonyms to its values: `padding`, `border`,
and `content`.

4914

14Opera accepts alternate synonyms to its values: `padding`, `border`,
and `content`.

11

1

1Webkit accepts alternate synonyms to its values: `padding`, `border`,
and `content`.

1.0

1.0Samsung Internet accepts alternate synonyms to its values: `padding`,
`border`, and `content`.

`content-box`

1

12

4

9In IE 7 and IE 9 of Internet Explorer, it always behaved like
`background-clip: padding` if `overflow: hidden | auto | scroll`.

10.5

3

4

18

14

11

1

1.0

See also
--------

- [`background-clip`](background-clip.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/background-origin>
