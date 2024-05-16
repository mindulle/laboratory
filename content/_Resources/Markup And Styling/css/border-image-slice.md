border-image-slice
==================

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `border-image-slice`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property divides
the image specified by [`border-image-source`](border-image-source.md) into
regions. These regions form the components of an element\'s [](border-image.md).

Try it
------

The slicing process creates nine regions in total: four corners, four
edges, and a middle region. Four slice lines, set a given distance from
their respective sides, control the size of the regions.

[![The nine regions defined by the border-image or border-image-slice
properties](data:image/png;base64,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)](border-image-slice/border-image-slice.png)

The above diagram illustrates the location of each region.

- Zones 1-4 are corner regions. Each one is used a single time to form
    the corners of the final border image.
- Zones 5-8 are edge regions. These are [](border-image-repeat.md) in the final border image
    to match the dimensions of the element.
- Zone 9 is the middle region. It is discarded by default, but is used
    like a background image if the keyword `fill` is set.

The [`border-image-repeat`](border-image-repeat.md),
[`border-image-width`](border-image-width.md), and
[`border-image-outset`](border-image-outset.md) properties determine how
these regions are used to form the final border image.

Syntax
------

[css]

```css
/* All sides */
border-image-slice: 30%;

/* top and bottom | left and right */
border-image-slice: 10% 30%;

/* top | left and right | bottom */
border-image-slice: 30 30% 45;

/* top | right | bottom | left */
border-image-slice: 7 12 14 5;

/* Using the `fill` keyword */
border-image-slice: 10% fill;
border-image-slice: fill 10%;

/* Global values */
border-image-slice: inherit;
border-image-slice: initial;
border-image-slice: revert;
border-image-slice: revert-layer;
border-image-slice: unset;
```

The `border-image-slice` property may be specified using one to four
`<number-percentage>` values to represent the position of each image
slice. Negative values are invalid; values greater than their
corresponding dimension are clamped to `100%`.

- When **one** position is specified, it creates all four slices at
    the same distance from their respective sides.
- When **two** positions are specified, the first value creates slices
    measured from the **top and bottom**, the second creates slices
    measured from the **left and right**.
- When **three** positions are specified, the first value creates a
    slice measured from the **top**, the second creates slices measured
    from the **left and right**, the third creates a slice measured from
    the **bottom**.
- When **four** positions are specified, they create slices measured
    from the **top**, **right**, **bottom**, and **left** in that order
    (clockwise).

The optional `fill` value, if used, can be placed anywhere in the
declaration.

### Values

[`<number>`](number.md)

:   Represents an edge offset in *pixels* for raster images and
    *coordinates* for vector images. For vector images, the number is
    relative to the element\'s size, not the size of the source image,
    so percentages are generally preferable in these cases.

[`<percentage>`](percentage.md)

:   Represents an edge offset as a percentage of the source image\'s
    size: the width of the image for horizontal offsets, the height for
    vertical offsets.

[`fill`](#fill)

:   Preserves the middle image region and displays it like a background
    image, but stacked above the actual [`background`](background.md). Its
    width and height are sized to match the top and left image regions,
    respectively.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `100%`
  Applies to                         all elements, except internal table elements when [`border-collapse`](border-collapse.md) is `collapse`. It also applies to [`::first-letter`](::first-letter).
  [Inherited](inheritance.md)           no
  Percentages                        refer to the size of the border image
  [Computed value](computed_value.md)   one to four percentage(s) (as specified) or absolute length(s), plus the keyword `fill` if specified
  Animation type                     by computed value type
  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
border-image-slice = 
  [ <number [0,∞]> | <percentage [0,∞]> ]  &&
  fill?                                         
```

Examples
--------

### Adjustable border width and slice

The following example shows a simple `<div>` with a border image set on
it. The source image for the borders is as follows:

![nice multi-colored
diamonds](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAABaBAMAAADKhlwxAAAAFVBMVEX////2nTzmZGXu7u72nTzmZGXu7u5STD5TAAAABHRSTlMAoKCgEjok+wAAAT5JREFUeF7tlkGqwjAURaNuwA8uQIQ/FwTnQlcgZAVC9r8EIVx66q0U7sBZOj29p03y3iNFz6V8PH+FZ0339byku+m4Qct/fS7xaXp8oYSr4lJPyKGEq+JST8ihhBWf1cihhHscNXIoYcVRI4cS7nHUyKGEFZcauVOFFZdacqcKE5dacqMKE5dacqMKE+9q5EYVnuNdjdxo9nb2J9Eqsx2MTic7+aiqsoqNuiHrtKiLswmRT598suVT0/Fti/qnD+3qdGNZ9/ZaU98y1A051I4DdUMO9aNGjRzqZYQaOdRLFDVyqJU/asmNWmtJjdyota3UyI3aSJBacqc2bqRGbtRGWVcjN1psTHY1cqPZ29mfRKvMdjA6nezko6rKKjbqhqzToi7OJkQ0fdLJlk/N391jxz123GPHPXbcY8c99g1A7me1IHQX+QAAAABJRU5ErkJggg==)

The diamonds are 30px across, therefore setting 30 pixels as the value
for both [`border-width`](border-width.md) and `border-image-slice` will
get you complete and fairly crisp diamonds in your border:

[css]

```css
border-width: 30px;
border-image-slice: 30;
```

These are the default values we have used in this example. However, we
have also provided two sliders to allow you to dynamically change the
values of the above two properties, allowing you to appreciate the
effect they have:

`border-image-slice` Changes the size of the image slice sampled for use
in each border and border corner (and the content area, if the `fill`
keyword is used) --- varying this away from 30 causes the border to look
somewhat irregular, but can have some interesting effects.

`border-width`: Changes the width of the border. The sampled image size
is scaled to fit inside the border, which means that if the width is
bigger than the slice, the image can start to look somewhat pixelated
(unless of course you use an SVG image).

#### HTML

[html]

```html
<div class="wrapper">
  <div></div>
</div>

<ul>
  <li>
    <label for="width">slide to adjust <code>border-width</code></label>
    <input type="range" min="10" max="45" id="width" />
    <output id="width-output">30px</output>
  </li>
  <li>
    <label for="slice">slide to adjust <code>border-image-slice</code></label>
    <input type="range" min="10" max="45" id="slice" />
    <output id="slice-output">30</output>
  </li>
</ul>
```

#### CSS

[css]

```css
.wrapper {
  width: 400px;
  height: 300px;
}

div > div {
  width: 300px;
  height: 200px;
  border-width: 30px;
  border-style: solid;
  border-image: url(https://interactive-examples.mdn.mozilla.net/media/examples/border-diamonds.png);
  border-image-slice: 30;
  border-image-repeat: round;
}

li {
  display: flex;
  place-content: center;
}
```

#### JavaScript

[js]

```js
const widthSlider = document.getElementById("width");
const sliceSlider = document.getElementById("slice");
const widthOutput = document.getElementById("width-output");
const sliceOutput = document.getElementById("slice-output");
const divElem = document.querySelector("div > div");

widthSlider.addEventListener("input", () => {
  const newValue = `$px`;
  divElem.style.borderWidth = newValue;
  widthOutput.textContent = newValue;
});

sliceSlider.addEventListener("input", () => {
  const newValue = sliceSlider.value;
  divElem.style.borderImageSlice = newValue;
  sliceOutput.textContent = newValue;
});
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  the-border-image-slice]](https://drafts.csswg.org/css-backgrounds/#the-border-image-slice)

  ----------------------------------------------------------------------------------------------------

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

`border-image-slice`

15

12

15\[\"Small SVGs are incorrectly stretched, because percentages in
[`border-image-slice`](https://developer.mozilla.org/docs/Web/CSS/border-image-slice)
are computed to integers instead of floats ([bug
1284797](https://bugzil.la/1284797)).\", \"Until Firefox 47, SVGs
without viewport were not sliced correctly ([bug
619500](https://bugzil.la/619500)).\", \"From Firefox 48 until Firefox
49, SVGs without viewport are displayed the same as SVGs with viewport,
but if the slices are not exactly 50%, they are incorrectly stretched
([bug 1264809](https://bugzil.la/1264809)).\", \"Until Firefox 57, an
issue persisted for SVGs without viewport when
[e10s](https://wiki.mozilla.org/Electrolysis) was disabled ([bug
1290782](https://bugzil.la/1290782)).\"\]

11

15

6

4.44

18

15\[\"Small SVGs are incorrectly stretched, because percentages in
[`border-image-slice`](https://developer.mozilla.org/docs/Web/CSS/border-image-slice)
are computed to integers instead of floats ([bug
1284797](https://bugzil.la/1284797)).\", \"Until Firefox 47, SVGs
without viewport were not sliced correctly ([bug
619500](https://bugzil.la/619500)).\", \"From Firefox 48 until Firefox
49, SVGs without viewport are displayed the same as SVGs with viewport,
but if the slices are not exactly 50%, they are incorrectly stretched
([bug 1264809](https://bugzil.la/1264809)).\", \"Until Firefox 57, an
issue persisted for SVGs without viewport when
[e10s](https://wiki.mozilla.org/Electrolysis) was disabled ([bug
1290782](https://bugzil.la/1290782)).\"\]

14

6

1.0

See also
--------

- [](shorthand_properties.md#tricky_edge_cases)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-slice>
