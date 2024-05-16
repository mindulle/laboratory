writing-mode
============

The `writing-mode`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
whether lines of text are laid out horizontally or vertically, as well
as the direction in which blocks progress. When set for an entire
document, it should be set on the root element (`html` element for HTML
documents).

Try it
------

This property specifies the *block flow direction*, which is the
direction in which block-level containers are stacked, and the direction
in which inline-level content flows within a block container. Thus, it
also determines the ordering of block-level content.

Syntax
------

[css]

```css
/* Keyword values */
writing-mode: horizontal-tb;
writing-mode: vertical-rl;
writing-mode: vertical-lr;

/* Global values */
writing-mode: inherit;
writing-mode: initial;
writing-mode: revert;
writing-mode: revert-layer;
writing-mode: unset;
```

The `writing-mode` property is specified as one of the values listed
below. The flow direction in horizontal scripts is also affected by the
[directionality of that
script](https://www.w3.org/International/questions/qa-scripts.en),
either left-to-right (`ltr`, like English and most other languages) or
right-to-left (`rtl`, like Hebrew or Arabic).

### Values

[`horizontal-tb`](#horizontal-tb)

:   For `ltr` scripts, content flows horizontally from left to right.
    For `rtl` scripts, content flows horizontally from right to left.
    The next horizontal line is positioned below the previous line.

[`vertical-rl`](#vertical-rl)

:   For `ltr` scripts, content flows vertically from top to bottom, and
    the next vertical line is positioned to the left of the previous
    line. For `rtl` scripts, content flows vertically from bottom to
    top, and the next vertical line is positioned to the right of the
    previous line.

[`vertical-lr`](#vertical-lr)

:   For `ltr` scripts, content flows vertically from top to bottom, and
    the next vertical line is positioned to the right of the previous
    line. For `rtl` scripts, content flows vertically from bottom to
    top, and the next vertical line is positioned to the left of the
    previous line.

[`sideways-rl`](#sideways-rl) [Experimental]

:   For `ltr` scripts, content flows vertically from top to bottom. For
    `rtl` scripts, content flows vertically from bottom to top. All the
    glyphs, even those in vertical scripts, are set sideways toward the
    right.

[`sideways-lr`](#sideways-lr) [Experimental]

:   For `ltr` scripts, content flows vertically from bottom to top. For
    `rtl` scripts, content flows vertically from top to bottom. All the
    glyphs, even those in vertical scripts, are set sideways toward the
    left.

[`lr`](#lr) [Deprecated]

:   Deprecated except for SVG1 documents. For CSS, use `horizontal-tb`
    instead.

[`lr-tb`](#lr-tb) [Deprecated]

:   Deprecated except for SVG1 documents. For CSS, use `horizontal-tb`
    instead.

[`rl`](#rl) [Deprecated]

:   Deprecated except for SVG1 documents. For CSS, use `horizontal-tb`
    instead.

[`tb`](#tb) [Deprecated]

:   Deprecated except for SVG1 documents. For CSS, use `vertical-lr`
    instead.

[`tb-lr`](#tb-lr) [Deprecated]

:   Deprecated except for SVG1 documents. For CSS, use `vertical-lr`
    instead.

[`tb-rl`](#tb-rl) [Deprecated]

:   Deprecated except for SVG1 documents. For CSS, use `vertical-rl`
    instead.

Formal definition
-----------------

  ---------------------------------- ------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `horizontal-tb`
  Applies to                         all elements except table row groups, table column groups, table rows, and table columns
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- ------------------------------------------------------------------------------------------

Formal syntax
-------------

```
writing-mode = 
  horizontal-tb  |
  vertical-rl    |
  vertical-lr    |
  sideways-rl    |
  sideways-lr    
```

Examples
--------

### Using multiple writing modes

This example demonstrates all of the writing modes, showing each with
text in various languages.

#### HTML

The HTML is a
[`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
with each writing mode in a row with a column showing text in various
scripts using that writing mode.

[html]

```html
<table>
  <caption>
    Using multiple writing modes
  </caption>
  <tr>
    <th>Value</th>
    <th>Vertical script</th>
    <th>Horizontal (LTR) script</th>
    <th>Horizontal (RTL) script</th>
    <th>Mixed script</th>
  </tr>
  <tr class="text1">
    <th>horizontal-tb</th>
    <td>我家没有电脑。</td>
    <td>Example text</td>
    <td>מלל ארוך לדוגמא</td>
    <td>1994年に至っては</td>
  </tr>
  <tr class="text2">
    <th>vertical-lr</th>
    <td>我家没有电脑。</td>
    <td>Example text</td>
    <td>מלל ארוך לדוגמא</td>
    <td>1994年に至っては</td>
  </tr>
  <tr class="text3">
    <th>vertical-rl</th>
    <td>我家没有电脑。</td>
    <td>Example text</td>
    <td>מלל ארוך לדוגמא</td>
    <td>1994年に至っては</td>
  </tr>
  <tr class="experimental text4">
    <th>sideways-lr</th>
    <td>我家没有电脑。</td>
    <td>Example text</td>
    <td>מלל ארוך לדוגמא</td>
    <td>1994年に至っては</td>
  </tr>
  <tr class="experimental text5">
    <th>sideways-rl</th>
    <td>我家没有电脑。</td>
    <td>Example text</td>
    <td>מלל ארוך לדוגמא</td>
    <td>1994年に至っては</td>
  </tr>
</table>
<p class="notice">
  Your browser does not support the <code>sideways-lr</code> or
  <code>sideways-rl</code> values.
</p>
```

#### CSS

The CSS that adjusts the directionality of the content looks like this:

[css]

```css
.text1 td {
  writing-mode: horizontal-tb;
}

.text2 td {
  writing-mode: vertical-lr;
}

.text3 td {
  writing-mode: vertical-rl;
}

.text4 td {
  writing-mode: sideways-lr;
}

.text5 td {
  writing-mode: sideways-rl;
}
```

#### Result

### Using writing-mode with transforms

If your browser doesn\'t support `sideways-lr`, a workaround is to use
[`transform`](transform.md) to achieve a similar effect depending on the
script direction. The effect of `vertical-rl` is the same as with
`sideways-lr`, so no transformation is required for left-to-right
scripts. In some cases, rotating the text 180 degrees is sufficient to
achieve the effect of `sideways-lr`, but font glyphs may not be designed
to be rotated, so this may produce unexpected positioning or rendering.

#### HTML

[html]

```html
<table>
  <caption>
    Using writing-mode with transforms
  </caption>
  <thead>
    <tr>
      <th>Vertical LR</th>
      <th>Vertical LR with transform</th>
      <th>Sideways LR</th>
      <th>Only rotate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <span class="vertical-lr">我家没有电脑。</span>
        <span class="vertical-lr">Example text</span>
      </td>
      <td>
        <span class="vertical-lr rotated">我家没有电脑。</span>
        <span class="vertical-lr rotated">Example text</span>
      </td>
      <td>
        <span class="sideways-lr">我家没有电脑。</span>
        <span class="sideways-lr">Example text</span>
      </td>
      <td>
        <span class="only-rotate">我家没有电脑。</span>
        <span class="only-rotate">Example text</span>
      </td>
    </tr>
  </tbody>
</table>
```

#### CSS

[css]

```css
.vertical-lr {
  writing-mode: vertical-lr;
}

.rotated {
  transform: rotate(180deg);
}

.sideways-lr {
  writing-mode: sideways-lr;
}

.only-rotate {
  inline-size: fit-content;
  transform: rotate(-90deg);
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Writing Modes Level 4\
  [\#
  block-flow]](https://drafts.csswg.org/css-writing-modes/#block-flow)

  ------------------------------------------------------------------------------

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

`writing-mode`

488

1212

41Firefox 42 added support for bidirectional and RTL scripts in vertical
modes.

9Internet Explorer\'s implementation differs from the specification.

9Internet Explorer\'s implementation differs from the specification.

3515

10.15.1

483

4818

41Firefox 42 added support for bidirectional and RTL scripts in vertical
modes.

3514

10.35

5.01.0

`horizontal_vertical_values`

48

79

43

No

35

9

48

48

43

35

9

5.0

`sideways_values`

No

No

43

No

No

No

No

No

43

No

No

No

`svg_values`

48

12

43

9

35

10.1

48

48

43

35

10.3

5.0

See also
--------

- SVG
    [`writing-mode`](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/writing-mode)
    attribute
- [`direction`](direction.md)
- [`unicode-bidi`](unicode-bidi.md)
- [`text-orientation`](text-orientation.md)
- [`text-combine-upright`](text-combine-upright.md)
- [CSS logical properties](css_logical_properties_and_values.md)
- [Styling vertical text (Chinese, Japanese, Korean and
    Mongolian)](https://www.w3.org/International/articles/vertical-text/)
    on W3.org (2022)
- [CSS writing modes](css_writing_modes.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode>
