print-color-adjust
==================

The `print-color-adjust` CSS property sets what, if anything, the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) may
do to optimize the appearance of the element on the output device. By
default, the browser is allowed to make any adjustments to the
element\'s appearance it determines to be necessary and prudent given
the type and capabilities of the output device.

Syntax
------

[css]

```css
print-color-adjust: economy;
print-color-adjust: exact;

/* Global values */
print-color-adjust: inherit;
print-color-adjust: initial;
print-color-adjust: revert;
print-color-adjust: revert-layer;
print-color-adjust: unset;
```

The `print-color-adjust` property\'s value must be one of the following
keywords.

### Values

[`economy`](#economy)

:   The user agent is allowed to make adjustments to the element as it
    deems appropriate and prudent in order to optimize the output for
    the device it\'s being rendered for. For example, when printing, a
    browser might opt to leave out all background images and to adjust
    text colors to be sure the contrast is optimized for reading on
    white paper. This is the default.

[`exact`](#exact)

:   The element\'s content has been specifically and carefully crafted
    to use colors, images, and styles in a thoughtful and/or important
    way, such that being altered by the browser might actually make
    things worse rather than better. The appearance of the content
    should not be changed except by the user\'s request. For example, a
    page might include a list of information with rows whose background
    colors alternate between white and a light grey. Removing the
    background color would decrease the legibility of the content.

Usage notes
-----------

There are a number of reasons a browser might wish to deviate from the
specified appearance, such as:

- The content uses text and background colors that will be too similar
    on the output device for legibility purposes.
- If the output device is a printer, and to save ink, dark or
    extremely dense background images might be removed.
- When printing a page, the browser might want to replace
    light-colored text on a dark background with dark text on a white
    background.

Any options the user agent offers the user to allow them to control the
use of color and images will take priority over the value of
`print-color-adjust`. In other words, there isn\'t any guarantee that
`print-color-adjust` will do anything. Not only can the user override
the behavior, but each user agent is allowed to decide for itself how to
handle `print-color-adjust` in any given situation.

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `economy`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
print-color-adjust = 
  economy  |
  exact    
```

Examples
--------

### Preserving low contrast

In this example, a box is shown which uses a
[`background-image`](background-image.md) and a translucent
[`linear-gradient()`](linear-gradient.md) function atop a black
background color to have a dark blue gradient behind medium red text.
For whatever reason, this is the desired appearance in any rendering
environment, including on paper, so we also use
`print-color-adjust: exact` to tell the browser not to make color or
style adjustments to the box when rendering it.

#### CSS

[css]

```css
.my-box {
  background-color: black;
  background-image: linear-gradient(
    rgba(0, 0, 180, 0.5),
    rgba(70, 140, 220, 0.5)
  );
  color: #900;
  width: 15rem;
  height: 6rem;
  text-align: center;
  font:
    24px "Helvetica",
    sans-serif;
  display: flex;
  align-items: center;
  justify-content: center;
  print-color-adjust: exact;
}
```

#### HTML

[html]

```html
<div class="my-box">
  <p>Need more contrast!</p>
</div>
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------

  [CSS Color Adjustment Module Level 1\
  [\#
  propdef-print-color-adjust]](https://drafts.csswg.org/css-color-adjust/#propdef-print-color-adjust)

  -------------------------------------------------------------------------------------------------------------

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

`print-color-adjust`

17\[\"Chrome does not print backgrounds of the
[`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body)
element. If this property is set to `exact` for the `<body>` element, it
will apply only to its descendants.\", \"Before version 26, if
background images are clipped (for example, when using
`background-image` sprites) and `-webkit-print-color-adjust` is set to
`exact`, then backgrounds will appear distorted when printed. Solid
backgrounds and background images that are not clipped (i.e.,
backgrounds that have narrower and shorter than the element to which
they are applied) are printed correctly. See [Chromium bug
131054](https://crbug.com/131054).\"\]

79Edge does not print backgrounds of the
[`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body)
element. If this property is set to `exact` for the `<body>` element, it
will apply only to its descendants.

9748

No

15Opera does not print backgrounds of the
[`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body)
element. If this property is set to `exact` for the `<body>` element, it
will apply only to its descendants.

15.4

6Safari does not print backgrounds of the
[`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body)
element. If this property is set to `exact` for the `<body>` element, it
will apply only to its descendants.

4.4WebView does not print backgrounds of the
[`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body)
element. If this property is set to `exact` for the `<body>` element, it
will apply only to its descendants.

18\[\"Chrome does not print backgrounds of the
[`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body)
element. If this property is set to `exact` for the `<body>` element, it
will apply only to its descendants.\", \"Before version 26, if
background images are clipped (for example, when using
`background-image` sprites) and `-webkit-print-color-adjust` is set to
`exact`, then backgrounds will appear distorted when printed. Solid
backgrounds and background images that are not clipped (i.e.,
backgrounds that have narrower and shorter than the element to which
they are applied) are printed correctly. See [Chromium bug
131054](https://crbug.com/131054).\"\]

9748

15Opera does not print backgrounds of the
[`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body)
element. If this property is set to `exact` for the `<body>` element, it
will apply only to its descendants.

15.4

6Safari does not print backgrounds of the
[`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body)
element. If this property is set to `exact` for the `<body>` element, it
will apply only to its descendants.

1.0\[\"Samsung Internet does not print backgrounds of the
[`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body)
element. If this property is set to `exact` for the `<body>` element, it
will apply only to its descendants.\", \"In version 1, if background
images are clipped (for example, when using `background-image` sprites)
and `-webkit-print-color-adjust` is set to `exact`, then backgrounds
will appear distorted when printed. Solid backgrounds and background
images that are not clipped (i.e., backgrounds that have narrower and
shorter than the element to which they are applied) are printed
correctly. See [Chromium bug 131054](https://crbug.com/131054).\"\]

See also
--------

- [](applying_color.md)
- Other color-related properties: [`color`](_Resources/Markup%20And%20Styling/css/color.md),
    [`background-color`](background-color.md),
    [`border-color`](border-color.md), [`outline-color`](outline-color.md),
    [`text-decoration-color`](text-decoration-color.md),
    [`text-emphasis-color`](text-emphasis-color.md),
    [`text-shadow`](text-shadow.md), [`caret-color`](caret-color.md), and
    [`column-rule-color`](column-rule-color.md)
- [`background-image`](background-image.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/print-color-adjust>
