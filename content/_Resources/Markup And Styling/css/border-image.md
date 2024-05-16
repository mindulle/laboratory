border-image
============

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `border-image`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property draws
an image around a given element. It replaces the element\'s regular
[border](border.md).

Try it
------

**Note:** You should specify a separate [`border-style`](border-style.md)
in case the border image fails to load. Although the specification
doesn\'t strictly require it, some browsers don\'t render the border
image if [`border-style`](border-style.md) is `none` or
[`border-width`](border-width.md) is `0`.

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`border-image-outset`](border-image-outset.md)
- [`border-image-repeat`](border-image-repeat.md)
- [`border-image-slice`](border-image-slice.md)
- [`border-image-source`](border-image-source.md)
- [`border-image-width`](border-image-width.md)

Syntax
------

[css]

```css
/* source | slice */
border-image: linear-gradient(red, blue) 27;

/* source | slice | repeat */
border-image: url("/images/border.png") 27 space;

/* source | slice | width */
border-image: linear-gradient(red, blue) 27 / 35px;

/* source | slice | width | outset | repeat */
border-image: url("/images/border.png") 27 23 / 50px 30px / 1rem round space;

/* Global values */
border-image: inherit;
border-image: initial;
border-image: revert;
border-image: revert-layer;
border-image: unset;
```

The `border-image` property may be specified with anywhere from one to
five of the values listed below.

**Note:** If the [computed value](computed_value.md) of
[`border-image-source`](border-image-source.md) is `none`, or if the image
cannot be displayed, the [`border-style`](border-style.md) will be
displayed instead.

### Values

[`<'border-image-source'>`](#border-image-source)

:   The source image. See [`border-image-source`](border-image-source.md).

[`<'border-image-slice'>`](#border-image-slice)

:   The dimensions for slicing the source image into regions. Up to four
    values may be specified. See
    [`border-image-slice`](border-image-slice.md).

[`<'border-image-width'>`](#border-image-width)

:   The width of the border image. Up to four values may be specified.
    See [`border-image-width`](border-image-width.md).

[`<'border-image-outset'>`](#border-image-outset)

:   The distance of the border image from the element\'s outside edge.
    Up to four values may be specified. See
    [`border-image-outset`](border-image-outset.md).

[`<'border-image-repeat'>`](#border-image-repeat)

:   Defines how the edge regions of the source image are adjusted to fit
    the dimensions of the border image. Up to two values may be
    specified. See [`border-image-repeat`](border-image-repeat.md).

Accessibility concerns
----------------------

Assistive technology cannot parse border images. If the image contains
information critical to understanding the page\'s overall purpose, it is
better to describe it semantically in the document.

- [MDN Understanding WCAG, Guideline 1.1
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.1_%E2%80%94_providing_text_alternatives_for_non-text_content)
- [Understanding Success Criterion 1.1.1 \| Understanding WCAG
    2.0](https://www.w3.org/TR/2016/NOTE-UNDERSTANDING-WCAG20-20161007/text-equiv-all.html)

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-image-source.md): |
|                                   |     `none`                        |
|                                   | -   [](border-image-slice.md): |
|                                   |     `100%`                        |
|                                   | -   [](border-image-width.md): |
|                                   |     `1`                           |
|                                   | -   [](border-image-outset.md): |
|                                   |     `0`                           |
|                                   | -   [](border-image-repeat.md): |
|                                   |     `stretch`                     |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements, except internal     |
|                                   | table elements when               |
|                                   | [](border-collapse.md) |
|                                   | is `collapse`. It also applies to |
|                                   | [`|
|                                   | ::first-letter`](::first-letter). |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| Percentages                       | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-image-slice.md): |
|                                   |     refer to the size of the      |
|                                   |     border image                  |
|                                   | -   [](border-image-width.md): |
|                                   |     refer to the width or height  |
|                                   |     of the border image area      |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-image-outset.md): |
|                                   |     as specified, but with        |
|                                   |     relative lengths converted    |
|                                   |     into absolute lengths         |
|                                   | -   [](border-image-repeat.md): |
|                                   |     as specified                  |
|                                   | -   [](border-image-slice.md): |
|                                   |     one to four percentage(s) (as |
|                                   |     specified) or absolute        |
|                                   |     length(s), plus the keyword   |
|                                   |     `fill` if specified           |
|                                   | -   [](border-image-source.md): |
|                                   |     `none` or the image with its  |
|                                   |     URI made absolute             |
|                                   | -   [](border-image-width.md): |
|                                   |     as specified, but with        |
|                                   |     relative lengths converted    |
|                                   |     into absolute lengths         |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-image-outset.md): |
|                                   |     by computed value type        |
|                                   | -   [](border-image-repeat.md): |
|                                   |     discrete                      |
|                                   | -   [](border-image-slice.md): |
|                                   |     by computed value type        |
|                                   | -   [](border-image-source.md): |
|                                   |     discrete                      |
|                                   | -   [](border-image-width.md): |
|                                   |     by computed value type        |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
border-image = 
  <'border-image-source'>                             ||
  <'border-image-slice'> [ / <'border-image-width'> | / <'border-image-width'>? / <'border-image-outset'> ]?  ||
  <'border-image-repeat'>                             
```

Examples
--------

### Bitmap

In this example, we will apply a diamond pattern to an element\'s
borders. The source for the border image is a \".png\" file of 81 by 81
pixels, with three diamonds going vertically and horizontally:

#### HTML

[html]

```html
<div id="bitmap">
  This element is surrounded by a bitmap-based border image!
</div>
```

#### CSS

To match the size of a single diamond, we will use a value of 81 divided
by 3, or `27`, for slicing the image into corner and edge regions. To
center the border image on the edge of the element\'s background, we
will make the outset values equal to half of the width values. Finally,
a repeat value of `round` will make the border slices fit evenly, i.e.,
without clipping or gaps.

[css]

```css
#bitmap {
  width: 200px;
  background-color: #ffa;
  border: 36px solid orange;
  margin: 30px;
  padding: 10px;

  border-image: url("border.png") 27 / 36px 28px 18px 8px / 18px 14px 9px 4px
    round;
}
```

#### Result

### Gradient

#### HTML

[html]

```html
<div id="gradient">
  This element is surrounded by a gradient-based border image!
</div>
```

#### CSS

[css]

```css
#gradient {
  width: 200px;
  border: 30px solid;
  border-image: repeating-linear-gradient(45deg, #f33, #3bf, #f33 30px) 60;
  padding: 20px;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  the-border-image]](https://drafts.csswg.org/css-backgrounds/#the-border-image)

  ----------------------------------------------------------------------------------------

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

`border-image`

16Before Chrome 112, a border image\'s absolute or percentage length
width may not take precedence over a narrower `border-width` ([bug
767352](https://crbug.com/767352)).

7

12Before Edge 112, a border image\'s absolute or percentage length width
may not take precedence over a narrower `border-width` ([bug
767352](https://crbug.com/767352)).

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

3.5Before Firefox 15, an earlier version of the specification was
implemented, prefixed.

11

11Before Opera 98, a border image\'s absolute or percentage length width
may not take precedence over a narrower `border-width` ([bug
767352](https://crbug.com/767352)).

10.5--15

63

4.4Before WebView 112, a border image\'s absolute or percentage length
width may not take precedence over a narrower `border-width` ([bug
767352](https://crbug.com/767352)).

2

18Before Chrome 112, a border image\'s absolute or percentage length
width may not take precedence over a narrower `border-width` ([bug
767352](https://crbug.com/767352)).

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

4Before Firefox 15, an earlier version of the specification was
implemented, prefixed.

11A border image\'s absolute or percentage length width may not take
precedence over a narrower `border-width` ([bug
767352](https://crbug.com/767352)).

11--14

63.2

1.0Before Samsung Internet false, a border image\'s absolute or
percentage length width may not take precedence over a narrower
`border-width` ([bug 767352](https://crbug.com/767352)).

1.0

`fill`

16

12

15

11

15

6

≤37

18

15

14

6

1.0

`gradient`

7

12

29

11

15

4

≤37

18

29

14

3.2

1.0

`optional_border_image_slice`

16

12

15

11

15

6

≤37

18

15

14

6

1.0

See also
--------

- [`border`](border.md)
- [`outline`](outline.md)
- [`box-shadow`](box-shadow.md)
- [`background-image`](background-image.md)
- [`url()`](url.md) function
- Gradient functions: [`conic-gradient()`](conic-gradient.md),
    [`repeating-conic-gradient()`](repeating-conic-gradient.md),
    [`linear-gradient()`](linear-gradient.md),
    [`repeating-linear-gradient()`](repeating-linear-gradient.md),
    [`radial-gradient()`](radial-gradient.md),
    [`repeating-radial-gradient()`](repeating-radial-gradient.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-image>
