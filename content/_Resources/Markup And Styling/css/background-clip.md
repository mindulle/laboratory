background-clip
===============

The `background-clip`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
whether an element\'s background extends underneath its border box,
padding box, or content box.

Try it
------

If the element has no [`background-image`](background-image.md) or
[`background-color`](background-color.md), this property will only have a
visual effect when the border has transparent regions or partially
opaque regions (due to [`border-style`](border-style.md) or
[`border-image`](border-image.md)); otherwise, the border masks the
difference.

**Note:** Because the [root
element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)
has a different background painting area, the `background-clip` property
has no effect when specified on it. See \"[The backgrounds of special
elements.](https://drafts.csswg.org/css-backgrounds-3/#special-backgrounds)\"

**Note:** For documents whose [root
element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)
is an HTML element: if the computed value of
[`background-image`](background-image.md) on the root element is `none` and
its [`background-color`](background-color.md) is `transparent`, user agents
must instead propagate the computed values of the `background`
properties from that element\'s first HTML
[`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body)
child element. The used values of that `<body>` element\'s `background`
properties are their initial values, and the propagated values are
treated as if they were specified on the root element. It is recommended
that authors of HTML documents specify the canvas background for the
`<body>` element rather than the HTML element.

Syntax
------

[css]

```css
/* Keyword values */
background-clip: border-box;
background-clip: padding-box;
background-clip: content-box;
background-clip: text;

/* Global values */
background-clip: inherit;
background-clip: initial;
background-clip: revert;
background-clip: revert-layer;
background-clip: unset;
```

### Values

[`border-box`](#border-box)

:   The background extends to the outside edge of the border (but
    underneath the border in z-ordering).

[`padding-box`](#padding-box)

:   The background extends to the outside edge of the padding. No
    background is drawn beneath the border.

[`content-box`](#content-box)

:   The background is painted within (clipped to) the content box.

[`text`](#text)

:   The background is painted within (clipped to) the foreground text.

Accessibility concerns
----------------------

When using `background-clip: text` check that the contrast ratio between
the background color and the color of the text placed over it is high
enough that people experiencing low vision conditions will be able to
read the content of the page.

If the background image does not load, this could also lead to the text
becoming unreadable. Add a fallback
[`background-color`](background-color.md) to prevent this from happening,
and test without the image.

Consider using feature queries with [`@supports`](@supports.md) to test for
support of `background-clip: text` and provide an accessible alternative
where it is not supported.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `border-box`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     a repeatable list
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
background-clip = 
  <box>#  

<box> = 
  border-box   |
  padding-box  |
  content-box  
```

Examples
--------

### HTML

[html]

```html
<p class="border-box">The background extends behind the border.</p>
<p class="padding-box">
  The background extends to the inside edge of the border.
</p>
<p class="content-box">
  The background extends only to the edge of the content box.
</p>
<p class="text">The background is clipped to the foreground text.</p>
```

### CSS

[css]

```css
p {
  border: 0.8em darkviolet;
  border-style: dotted double;
  margin: 1em 0;
  padding: 1.4em;
  background: linear-gradient(60deg, red, yellow, red, yellow, red);
  font: 900 1.2em sans-serif;
  text-decoration: underline;
}

.border-box {
  background-clip: border-box;
}
.padding-box {
  background-clip: padding-box;
}
.content-box {
  background-clip: content-box;
}

.text {
  background-clip: text;
  -webkit-background-clip: text;
  color: rgba(0, 0, 0, 0.2);
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  background-clip]](https://drafts.csswg.org/css-backgrounds/#background-clip)

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

`background-clip`

1

1Chrome accepts alternate synonyms to its values: `padding`, `border`,
and `content`.

12

12Since Edge 79, accepts alternate synonyms to its values: `padding`,
`border`, and `content`.

494

1--4Used the `-moz-background-clip: padding | border` syntax.

9In IE 7 and IE 8 of Internet Explorer, this property always behaved
like `background-clip: padding` when `overflow` was `hidden`, `auto`, or
`scroll`.

15Opera accepts alternate synonyms to its values: `padding`, `border`,
and `content`.

10.5

5

3Safari accepts alternate synonyms to its values: `padding`, `border`,
and `content`.

≤37WebView accepts alternate synonyms to its values: `padding`,
`border`, and `content`.

4

18

18Chrome accepts alternate synonyms to its values: `padding`, `border`,
and `content`.

4914

14Opera accepts alternate synonyms to its values: `padding`, `border`,
and `content`.

11

5

1Safari accepts alternate synonyms to its values: `padding`, `border`,
and `content`.

1.0

1.0Samsung Internet accepts alternate synonyms to its values: `padding`,
`border`, and `content`.

`content-box`

1

12

4

9In IE 7 and IE 9 of Internet Explorer, it always behaved like
`background-clip: padding` if `overflow: hidden | auto | scroll`

10.5

3

4

18

14

11

1

1.0

`text`

3The `text` value is only supported by `-webkit-background-clip` (and
not by `background-clip`).

15

12Before Edge 15, this value was supported with the prefixed version of
the property only.

49

No

15The `text` value is only supported by `-webkit-background-clip` (and
not by `background-clip`).

14

4The `text` value is only supported by `-webkit-background-clip` (and
not by `background-clip`).

4.4The `text` value is only supported by `-webkit-background-clip` (and
not by `background-clip`).

18The `text` value is only supported by `-webkit-background-clip` (and
not by `background-clip`).

49

14The `text` value is only supported by `-webkit-background-clip` (and
not by `background-clip`).

14

3.2The `text` value is only supported by `-webkit-background-clip` (and
not by `background-clip`).

1.0The `text` value is only supported by `-webkit-background-clip` (and
not by `background-clip`).

See also
--------

- The [`clip-path`](clip-path.md) property creates a clipping region that
    defines what part of an *entire element* should be displayed.
- Background properties: [`background`](background.md),
    [`background-color`](background-color.md),
    [`background-image`](background-image.md),
    [`background-origin`](background-origin.md)
- [](introduction_to_the_css_box_model.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/background-clip>
