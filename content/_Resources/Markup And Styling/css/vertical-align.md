vertical-align
==============

The `vertical-align`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
vertical alignment of an inline, inline-block or table-cell box.

Try it
------

The vertical-align property can be used in two contexts:

- To vertically align an inline-level element\'s box inside its
    containing line box. For example, it could be used to [vertically
    position an image in a line of
    text](#vertical_alignment_in_a_line_box).
- To vertically align [the content of a cell in a
    table](#vertical_alignment_in_a_table_cell).

Note that `vertical-align` only applies to inline, inline-block and
table-cell elements: you can\'t use it to vertically align [block-level
elements](https://developer.mozilla.org/en-US/docs/Glossary/Block-level_content).

Syntax
------

[css]

```css
/* Keyword values */
vertical-align: baseline;
vertical-align: sub;
vertical-align: super;
vertical-align: text-top;
vertical-align: text-bottom;
vertical-align: middle;
vertical-align: top;
vertical-align: bottom;

/* <length> values */
vertical-align: 10em;
vertical-align: 4px;

/* <percentage> values */
vertical-align: 20%;

/* Global values */
vertical-align: inherit;
vertical-align: initial;
vertical-align: revert;
vertical-align: revert-layer;
vertical-align: unset;
```

The `vertical-align` property is specified as one of the values listed
below.

### Values for inline elements

#### Parent-relative values

These values vertically align the element relative to its parent
element:

[`baseline`](#baseline)

:   Aligns the baseline of the element with the baseline of its parent.
    The baseline of some [replaced elements](replaced_element.md), like
    [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea),
    is not specified by the HTML specification, meaning that their
    behavior with this keyword may vary between browsers.

[`sub`](#sub)

:   Aligns the baseline of the element with the subscript-baseline of
    its parent.

[`super`](#super)

:   Aligns the baseline of the element with the superscript-baseline of
    its parent.

[`text-top`](#text-top)

:   Aligns the top of the element with the top of the parent element\'s
    font.

[`text-bottom`](#text-bottom)

:   Aligns the bottom of the element with the bottom of the parent
    element\'s font.

[`middle`](#middle)

:   Aligns the middle of the element with the baseline plus half the
    x-height of the parent.

[`<length>`](length.md)

:   Aligns the baseline of the element to the given length above the
    baseline of its parent. A negative value is allowed.

[`<percentage>`](percentage.md)

:   Aligns the baseline of the element to the given percentage above the
    baseline of its parent, with the value being a percentage of the
    [`line-height`](line-height.md) property. A negative value is allowed.

#### Line-relative values

The following values vertically align the element relative to the entire
line:

[`top`](#top)

:   Aligns the top of the element and its descendants with the top of
    the entire line.

[`bottom`](#bottom)

:   Aligns the bottom of the element and its descendants with the bottom
    of the entire line.

For elements that do not have a baseline, the bottom margin edge is used
instead.

### Values for table cells

[`baseline`](#baseline_2) (and `sub`, `super`, `text-top`, `text-bottom`, `<length>`, and `<percentage>`)

:   Aligns the baseline of the cell with the baseline of all other cells
    in the row that are baseline-aligned.

[`top`](#top_2)

:   Aligns the top padding edge of the cell with the top of the row.

[`middle`](#middle_2)

:   Centers the padding box of the cell within the row.

[`bottom`](#bottom_2)

:   Aligns the bottom padding edge of the cell with the bottom of the
    row.

Negative values are allowed.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `baseline`
  Applies to                         inline-level and table-cell elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           no
  Percentages                        refer to the [`line-height`](line-height.md) of the element itself
  [Computed value](computed_value.md)   for percentage and length values, the absolute length, otherwise the keyword as specified
  Animation type                     a [length](length.md#interpolation)
  ---------------------------------- ---------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
vertical-align = 
  [ first | last ]        ||
  <'alignment-baseline'>  ||
  <'baseline-shift'>      
```

Examples
--------

### Basic example

#### HTML

[html]

```html
<div>
  An <img src="frame_image.svg" alt="link" width="32" height="32" /> image with
  a default alignment.
</div>
<div>
  An
  <img class="top" src="frame_image.svg" alt="link" width="32" height="32" />
  image with a text-top alignment.
</div>
<div>
  An
  <img class="bottom" src="frame_image.svg" alt="link" width="32" height="32" />
  image with a text-bottom alignment.
</div>
<div>
  An
  <img class="middle" src="frame_image.svg" alt="link" width="32" height="32" />
  image with a middle alignment.
</div>
```

#### CSS

[css]

```css
img.top {
  vertical-align: text-top;
}
img.bottom {
  vertical-align: text-bottom;
}
img.middle {
  vertical-align: middle;
}
```

#### Result

### Vertical alignment in a line box

#### HTML

[html]

```html
<p>
top:         <img style="vertical-align: top" src="star.png" alt="star"/>
middle:      <img style="vertical-align: middle" src="star.png" alt="star"/>
bottom:      <img style="vertical-align: bottom" src="star.png" alt="star"/>
super:       <img style="vertical-align: super" src="star.png" alt="star"/>
sub:         <img style="vertical-align: sub" src="star.png" alt="star"/>
</p>

<p>
text-top:    <img style="vertical-align: text-top" src="star.png" alt="star"/>
text-bottom: <img style="vertical-align: text-bottom" src="star.png" alt="star"/>
0.2em:       <img style="vertical-align: 0.2em" src="star.png" alt="star"/>
-1em:        <img style="vertical-align: -1em" src="star.png" alt="star"/>
20%:         <img style="vertical-align: 20%" src="star.png" alt="star"/>
-100%:       <img style="vertical-align: -100%" src="star.png" alt="star"/>
</p>
```

#### Result

### Vertical alignment in a table cell

#### HTML

[html]

```html
<table>
  <tr>
    <td style="vertical-align: baseline">baseline</td>
    <td style="vertical-align: top">top</td>
    <td style="vertical-align: middle">middle</td>
    <td style="vertical-align: bottom">bottom</td>
    <td>
      <p>
        There is a theory which states that if ever anyone discovers exactly
        what the Universe is for and why it is here, it will instantly disappear
        and be replaced by something even more bizarre and inexplicable.
      </p>
      <p>
        There is another theory which states that this has already happened.
      </p>
    </td>
  </tr>
</table>
```

#### CSS

[css]

```css
table {
  margin-left: auto;
  margin-right: auto;
  width: 80%;
}

table,
th,
td {
  border: 1px solid black;
}

td {
  padding: 0.5em;
  font-family: monospace;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------

  [Cascading Style Sheets Level 2 Revision 2 (CSS 2.2) Specification\
  [\#
  propdef-vertical-align]](https://drafts.csswg.org/css2/#propdef-vertical-align)

  -----------------------------------------------------------------------------------------

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

`vertical-align`

1

12

1

4

4

1

4.4

18

4

14

1

1.0

See also
--------

- [](typical_use_cases_of_flexbox.md#center_item)
- [`line-height`](line-height.md), [`text-align`](text-align.md),
    [`margin`](margin.md)
- [Understanding `vertical-align`, or \"How (Not) To Vertically Center
    Content\"](http://phrogz.net/css/vertical-align/index.html)
- [Vertical-Align: All You Need To
    Know](https://christopheraue.net/design/vertical-align)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align>
