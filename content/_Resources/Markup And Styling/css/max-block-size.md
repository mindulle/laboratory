max-block-size
==============

The `max-block-size`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies the maximum size of an element in the direction opposite that
of the writing direction as specified by [`writing-mode`](writing-mode.md).
That is, if the writing direction is horizontal, then `max-block-size`
is equivalent to [`max-height`](max-height.md); if the writing direction is
vertical, `max-block-size` is the same as [`max-width`](max-width.md).

The other dimension\'s maximum length is specified using the
[`max-inline-size`](max-inline-size.md) property.

This is useful because the `max-width` is always used for horizontal
sizes and `max-height` is always used for vertical sizes, and if you
need to set lengths based on the size of your text content, you need to
be able to do so with the writing direction in mind.

Any time you would normally use `max-height` or `max-width`, you should
instead use `max-block-size` to set the maximum \"height\" of the
content (even though this may not be a vertical value) and
`max-inline-size` to set the maximum \"width\" of the content (although
this may instead be vertical rather than horizontal). See
[`writing-mode` examples](writing-mode.md#examples), which show the
different writing modes in action.

Try it
------

Syntax
------

[css]

```css
/* <length> values */
max-block-size: 300px;
max-block-size: 25em;

/* <percentage> values */
max-block-size: 75%;

/* Keyword values */
max-block-size: none;
max-block-size: max-content;
max-block-size: min-content;
max-block-size: fit-content(20em);

/* Global values */
max-block-size: inherit;
max-block-size: initial;
max-block-size: revert;
max-block-size: revert-layer;
max-block-size: unset;
```

### Values

The `max-block-size` property\'s value can be any value that\'s legal
for the [`max-width`](max-width.md) and [`max-height`](max-height.md)
properties:

[`<length>`](length.md)

:   Defines the `max-block-size` as an absolute value.

[`<percentage>`](percentage.md)

:   Defines the `max-block-size` as a percentage of the containing
    block\'s size in block axis.

[`none`](#none)

:   No limit on the size of the box.

[`max-content`](#max-content)

:   The intrinsic preferred `max-block-size`.

[`min-content`](#min-content)

:   The intrinsic minimum `max-block-size`.

[`fit-content(`](#fit-content)`<length-percentage>`)

:   Uses the `fit-content` formula with the available space replaced by
    the specified argument, i.e.
    `min(max-content, max(min-content, argument))`.

### How writing-mode affects directionality

The values of `writing-mode` affect the mapping of `max-block-size` to
`max-width` or `max-height` as follows:

  Values of `writing-mode`                                                                                                                                                                                             `max-block-size` is equivalent to
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- -----------------------------------
  `horizontal-tb`, `lr` [Deprecated]   [`max-height`](max-height.md)
  `vertical-rl`, `vertical-lr`, `sideways-rl` [Experimental]         [`max-width`](max-width.md)

**Note:** The `writing-mode` values `sideways-lr` and `sideways-rl` were
removed from the CSS Writing Modes Level 3 specification late in its
design process. They may be restored in Level 4.

**Note:** The writing modes `lr`, `lr-tb`, `rl`, `rb`, and `rb-tl` are
no longer allowed in
[HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML) contexts;
they may only be used in
[SVG](https://developer.mozilla.org/en-US/docs/Glossary/SVG) 1.x
contexts.

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         same as [`width`](_Resources/Markup%20And%20Styling/css/width.md) and [`height`](_Resources/Markup%20And%20Styling/css/height.md)
  [Inherited](inheritance.md)           no
  Percentages                        block-size of containing block
  [Computed value](computed_value.md)   same as [`max-width`](max-width.md) and [`max-height`](max-height.md)
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- -------------------------------------------------------------------------------------

Formal syntax
-------------

```
max-block-size = 
  <'max-width'>  
```

Examples
--------

### Setting max-block-size with horizontal and vertical text

In this example, the same text (the opening sentences from [Herman
Melville\'s](https://en.wikipedia.org/wiki/Herman_Melville) novel
*[Moby-Dick](https://en.wikipedia.org/wiki/Moby-Dick)*) is presented in
both the `horizontal-tb` and `vertical-rl` writing modes.

Everything else about the two boxes is identical, including the values
used for [`max-block-size`](max-block-size.md).

#### HTML

The HTML establishes the two
[`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
blocks that will be presented with their [`writing-mode`](writing-mode.md)
set using the classes `horizontal` or `vertical`. Both boxes share the
`standard-box` class, which establishes coloring, padding, and their
respective values of `max-block-size`.

[html]

```html
<p>Writing mode <code>horizontal-tb</code> (the default):</p>
<div class="standard-box horizontal">
  Call me Ishmael. Some years ago—never mind how long precisely—having little or
  no money in my purse, and nothing particular to interest me on shore, I
  thought I would sail about a little and see the watery part of the world. It
  is a way I have of driving off the spleen and regulating the circulation.
</div>

<p>Writing mode <code>vertical-rl</code>:</p>
<div class="standard-box vertical">
  Call me Ishmael. Some years ago—never mind how long precisely—having little or
  no money in my purse, and nothing particular to interest me on shore, I
  thought I would sail about a little and see the watery part of the world. It
  is a way I have of driving off the spleen and regulating the circulation.
</div>
```

#### CSS

The CSS defines three classes. The first, `standard-box`, is applied to
both boxes, as seen above. It provides standard styling including the
minimum and maximum block sizes, font size, and so forth.

After that come the classes `horizontal` and `vertical`, which add the
[`writing-mode`](writing-mode.md) property to the box, with the value set
to `horizontal-tb` or `vertical-rl` depending on which class is used.

[css]

```css
.standard-box {
  padding: 4px;
  background-color: #abcdef;
  color: #000;
  font:
    16px "Open Sans",
    "Helvetica",
    "Arial",
    sans-serif;
  max-block-size: 160px;
  min-block-size: 100px;
}

.horizontal {
  writing-mode: horizontal-tb;
}

.vertical {
  writing-mode: vertical-rl;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  propdef-max-block-size]](https://drafts.csswg.org/css-logical/#propdef-max-block-size)

  ------------------------------------------------------------------------------------------------

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

`max-block-size`

57

79

41

No

44

12.1

57

57

41

43

12.2

5.0

`fit-content`

57

79

94

No

44

12.1

57

57

94

43

12.2

5.0

`fit-content_function`

No

No

91

No

No

No

No

No

No

No

No

No

`max-content`

57

79

6641

No

44

12.1

57

57

6641

43

12.2

5.0

`min-content`

57

79

6641

No

44

12.1

57

57

6641

43

12.2

5.0

See also
--------

- The mapped physical properties: [`max-width`](max-width.md) and
    [`max-height`](max-height.md)
- Setting the other direction\'s maximum size:
    [`max-inline-size`](max-inline-size.md)
- [`writing-mode`](writing-mode.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/max-block-size>
