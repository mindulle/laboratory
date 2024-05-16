\<tr\>: The Table Row element
=============================

The `<tr>` [HTML](../index) element defines a row of cells in a table.
The row\'s cells can then be established using a mix of [`<td>`](td)
(data cell) and [`<th>`](th) (header cell) elements.

Try it
------

To provide additional control over how cells fit into (or span across)
columns, both `<th>` and `<td>` support the [`colspan`](td#colspan)
attribute, which lets you specify how many columns wide the cell should
be, with the default being 1. Similarly, you can use the
[`rowspan`](td#rowspan) attribute on cells to indicate they should span
more than one table row.

This can take a little practice to get right when building your tables.
We have some [examples](#examples) below, but for more examples and an
in-depth tutorial, see the [HTML
tables](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables)
series in our [Learn web
development](https://developer.mozilla.org/en-US/docs/Learn) area, where
you\'ll learn how to use the table elements and their attributes to get
just the right layout and formatting for your tabular data.

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).
There are also several [deprecated attributes](#deprecated_attributes),
which you should avoid but may need to know when reading older code.

### Deprecated attributes

The following attributes may still be implemented in browsers but are no
longer part of the HTML specification and may be missing or may not work
as expected. They should be avoided.

[`align`](#align) [Deprecated]

:   A string which specifies how the cell\'s context should be aligned
    horizontally within the cells in the row; this is shorthand for
    using `align` on every cell in the row individually. Possible values
    are:

    [`left`](#left)

    :   Align the content of each cell at its left edge.

    [`center`](#center)

    :   Center the contents of each cell between their left and right
        edges.

    [`right`](#right)

    :   Align the content of each cell at its right edge.

    [`justify`](#justify)

    :   Widen whitespaces within the text of each cell so that the text
        fills the full width of each cell (full justification).

    [`char`](#char)

    :   Align each cell in the row on a specific character (such that
        each row in the column that is configured this way will
        horizontally align its cells on that character). This uses the
        [`char`](#char) and [`charoff`](#charoff) to establish the
        alignment character (typically \".\" or \",\" when aligning
        numerical data) and the number of characters that should follow
        the alignment character. This alignment type was never widely
        supported.

    If no value is expressly set for `align`, the parent node\'s value
    is inherited.

     
    **Note:** Instead of using the obsolete `align` attribute, you
    should instead use the CSS
    [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
    property to establish `left`, `center`, `right`, or `justify`
    alignment for the row\'s cells. To apply character-based alignment,
    set the CSS
    [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
    property to the alignment character (such as `"."` or `","`).

[`bgcolor`](#bgcolor) [Deprecated]

:   A string specifying a color to apply to the backgrounds of each of
    the row\'s cells. This can be either a [hexadecimal `#RRGGBB` or
    `#RGB`
    value](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/rgb)
    or a [color
    keyword](https://developer.mozilla.org/en-US/docs/Web/CSS/named-color).
    Omitting the attribute or setting it to `null` in JavaScript causes
    the row\'s cells to inherit the row\'s parent element\'s background
    color.

    **Note:** The [`<tr>`](tr) element should be styled using
    [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS). To give a
    similar effect as the `bgcolor` attribute, use the CSS property
    [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color).

[`char`](#char_2) [Deprecated]

:   A string that sets the character to align the cells in each row\'s
    columns (each row\'s centering that uses the same character gets
    aligned with others using the same character. Typical values for
    this include a period (`"."`) or comma (`","`) when attempting to
    align numbers or monetary values. If [`align`](#align) is not set to
    `char`, this attribute is ignored.

    **Note:** This attribute is obsolete and rarely implemented anyway.
    To achieve the same effect as the [`char`](#char) attribute, set the
    CSS
    [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
    property to the same string you would specify for the `char`
    property, such as `text-align: "."`.

[`charoff`](#charoff) [Deprecated]

:   A string indicating the number of characters on the tail end of the
    column\'s data should be displayed after the alignment character
    specified by the `char` attribute. For example, when displaying
    money values for currencies that use hundredths of a unit (such as
    the dollar, which is divided into 100 cents), you would typically
    specify a value of 2, so that in tandem with `char` being set to
    `"."`, the values in a column would be cleanly aligned on the
    decimal points, with the number of cents properly displayed to the
    right of the decimal point.

    **Note:** This attribute is obsolete, and was never widely supported
    anyway.

[`valign`](#valign) [Deprecated]

:   A string specifying the vertical alignment of the text within each
    cell in the row. Possible values for this attribute are:

    [`baseline`](#baseline)

    :   Aligns each cell\'s content text as closely as possible to the
        bottom of the cell, handling alignment of different fonts and
        font sizes by aligning the characters along the
        [baseline](https://en.wikipedia.org/wiki/Baseline) of the
        font(s) used in the row. If all the characters in the row are
        the same size, the effect is the same as `bottom`.

    [`bottom`](#bottom),

    :   Draws the text in each of the row\'s cells as closely as
        possible to the bottom edge of those cells.

    [`middle`](#middle)

    :   Each cell\'s text is vertically centered.

    [`top`](#top)

    :   Each cell\'s text is drawn as closely as possible to the top
        edge of the containing cell.

     
    **Note:** Don\'t use the obsolete `valign` attribute. Instead, add
    the CSS
    [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)
    property to the row.

Examples
--------

See [`<table>`](table) for examples on `<tr>`.

### Basic example

This simple example shows a table listing people\'s names along with
various information about membership in a club or service.

#### HTML

This HTML demonstrates the most basic structure of a table. There are no
groups, no cells that span multiple rows or columns, no captions, and
only the most basic styling to create lines around the components of the
table for something resembling clarity.

There are just four rows (including one header row), each with four
columns (including one header column). Not even the table section
elements are used; instead, the browser is allowed to determine this
automatically. We\'ll add [`<thead>`](thead), [`<tbody>`](tbody), and
[`<tfoot>`](tfoot) in the next example.

[html]

```html
<table>
  <tr>
    <th>Name</th>
    <th>ID</th>
    <th>Member Since</th>
    <th>Balance</th>
  </tr>
  <tr>
    <td>Margaret Nguyen</td>
    <td>427311</td>
    <td><time datetime="2010-06-03">June 3, 2010</time></td>
    <td>0.00</td>
  </tr>
  <tr>
    <td>Edvard Galinski</td>
    <td>533175</td>
    <td><time datetime="2011-01-13">January 13, 2011</time></td>
    <td>37.00</td>
  </tr>
  <tr>
    <td>Hoshi Nakamura</td>
    <td>601942</td>
    <td><time datetime="2012-07-23">July 23, 2012</time></td>
    <td>15.00</td>
  </tr>
</table>
```

#### CSS

This simple CSS just adds a solid black border around the table and
around each of its cells, including those specified using both
[`<th>`](th) and [`<td>`](td). That way, both header and data cells are
easily demarcated.

[css]

```css
table {
  border: 1px solid black;
}

th,
td {
  border: 1px solid black;
}

```

#### Result

### Row and column spanning

Now, let\'s introduce another column that shows the date the user\'s
membership ended, along with a super-heading above the \"joined\" and
\"canceled\" dates called \"Membership Dates\". This involves adding
both row and column spans to the table, so that the heading cells can
wind up in the right places.

#### Result

Let\'s actually look at the output first this time:

Notice how the heading area here is actually two rows, one with
\"Name\", \"ID\", \"Membership Dates\", and \"Balance\" headings, and
the other with \"Joined\" and \"Canceled\", which are subheadings below
\"Membership Dates\". This is accomplished by:

- Having the first row\'s \"Name\", \"ID\", and \"Balance\" heading
    cells span two rows using the [`rowspan`](#rowspan) attribute,
    making them each two rows tall.
- Having the first row\'s \"Membership Dates\" heading cell span two
    columns using the [`colspan`](#colspan) attribute, which causes this
    heading actually to be two columns wide.
- Having a second row of [`<th>`](th) elements that contains only the
    \"Joined\" and \"Canceled\" headings. Because the other columns are
    already occupied by first-row cells that span into the second row,
    these wind up correctly positioned under the \"Membership Dates\"
    heading.

#### HTML

The HTML is similar to the previous example\'s, except for the addition
of the new column in each data row, and the changes to the header. Those
changes make the HTML look like this:

[html]

```html
<table>
  <tr>
    <th rowspan="2">Name</th>
    <th rowspan="2">ID</th>
    <th colspan="2">Membership Dates</th>
    <th rowspan="2">Balance</th>
  </tr>
  <tr>
    <th>Joined</th>
    <th>Canceled</th>
  </tr>
  <tr>
    <th>Margaret Nguyen</th>
    <td>427311</td>
    <td><time datetime="2010-06-03">June 3, 2010</time></td>
    <td>n/a</td>
    <td>0.00</td>
  </tr>
  <tr>
    <th>Edvard Galinski</th>
    <td>533175</td>
    <td><time datetime="2011-01-13">January 13, 2011</time></td>
    <td><time datetime="2017-04-08">April 8, 2017</time></td>
    <td>37.00</td>
  </tr>
  <tr>
    <th>Hoshi Nakamura</th>
    <td>601942</td>
    <td><time datetime="2012-07-23">July 23, 2012</time></td>
    <td>n/a</td>
    <td>15.00</td>
  </tr>
</table>
```

The differences that matter here---for the purposes of discussing row
and column spans---are in the first few lines of the code above. Note
the use of `rowspan` on to make the \"Name\", \"ID\", and \"Balance\"
headers occupy two rows instead of just one, and the use of `colspan` to
make the \"Membership Dates\" header cell span across two columns.

The CSS is unchanged from before.

### Explicitly specifying table content groups

Before really getting into styling this table, let\'s take a moment to
add row and column groups to help make our CSS easier.

#### HTML

The HTML is where the action is here, and the action is pretty simple.

[html]

```html
<table>
  <thead>
    <tr>
      <th rowspan="2">Name</th>
      <th rowspan="2">ID</th>
      <th colspan="2">Membership Dates</th>
      <th rowspan="2">Balance</th>
    </tr>
    <tr>
      <th>Joined</th>
      <th>Canceled</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Margaret Nguyen</th>
      <td>427311</td>
      <td><time datetime="2010-06-03">June 3, 2010</time></td>
      <td>n/a</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th scope="row">Edvard Galinski</th>
      <td>533175</td>
      <td><time datetime="2011-01-13">January 13, 2011</time></td>
      <td><time datetime="2017-04-08">April 8, 2017</time></td>
      <td>37.00</td>
    </tr>
    <tr>
      <th scope="row">Hoshi Nakamura</th>
      <td>601942</td>
      <td><time datetime="2012-07-23">July 23, 2012</time></td>
      <td>n/a</td>
      <td>15.00</td>
    </tr>
  </tbody>
</table>
```

The differences that matter here---for the purposes of discussing row
and column spans---are in the first few lines of the code above. Note
the use of `rowspan` on to make the \"Name\", \"ID\", and \"Balance\"
headers occupy two rows instead of just one, and the use of `colspan` to
make the \"Membership Dates\" header cell span across two columns.

Once again, we haven\'t touched the CSS.

#### Result

The output is entirely unchanged, despite the addition of useful
contextual information under the hood:

### Basic styling

As is the case with all parts of a table, you can change the appearance
of a table row and its contents using CSS. Any styles applied to the
`<tr>` element will affect the cells within the row unless overridden by
styles applied to those cells.

Let\'s apply a basic style to the table to adjust the typeface being
used, and add a background color to the header row.

#### Result

Again, let\'s take a look at the result first.

#### CSS

This time, the HTML is unchanged, so let\'s dive right into the CSS.

[css]

```css
table {
  border: 1px solid black;
  font:
    16px "Open Sans",
    Helvetica,
    Arial,
    sans-serif;
}

thead > tr {
  background-color: rgb(228, 240, 245);
}

th,
td {
  border: 1px solid black;
  padding: 4px 6px;
}

```

While we add a
[`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) property
to the [`<table>`](table) element here to set a more visually-appealing
typeface (or an abominable sans-serif typeface, depending on your
personal opinion), the interesting part is the second style here, where
we style `<tr>` elements located within the [`<thead>`](thead) so they
have a light blue background color. This is a way to quickly apply a
background color to all the cells in the heading area at once.

This does *not* affect the style of the [`<th>`](th) elements in the
first column, though, where we treat the member names as a row heading.

### Advanced styling

Now we\'ll go all-out, with styles on rows in the header and body areas
both, including alternating row colors, cells with different colors
depending on position within a row, and so forth.

#### Result

Here\'s what the final table will look like:

There is no change to the HTML again. See what proper preparation of
your HTML can do for you?

#### CSS

The CSS is much more involved this time. It\'s not complicated, but
there\'s a lot going on. Let\'s break it down.

##### The table and base styles

[css]

```css
table {
  border: 1px solid black;
  font:
    16px "Open Sans",
    Helvetica,
    Arial,
    sans-serif;
  border-spacing: 0;
  border-collapse: collapse;
}

```

Here we\'ve added the
[`border-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-spacing)
and
[`border-collapse`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse)
properties to eliminate spacing between cells and collapse borders that
touch one another to be a single border instead of winding up with
double borders.

[css]

```css
th,
td {
  border: 1px solid black;
  padding: 4px 6px;
}

th {
  vertical-align: bottom;
}

```

And here are the default styles for all table cells. Now let\'s
customize!

##### The top header: overall

We\'re going to look at the top header in two pieces. First, the overall
styling of the header:

[css]

```css
thead > tr {
  background-color: rgb(228, 240, 245);
}

thead > tr:nth-of-type(2) {
  border-bottom: 2px solid black;
}

```

This sets the background color of all `<tr>` elements in the table\'s
heading (as specified using [`<thead>`](thead)). Then we set the bottom
border of the top header to be a two-pixel wide line. Notice, however,
that we\'re using the
[`:nth-of-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-of-type)
selector to apply
[`border-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom)
to the *second* row in the heading. Why? Because the heading is made of
two rows that are spanned by some of the cells. That means there are
actually two rows there; applying the style to the first row would not
give us the expected result.

##### The \"Joined\" and \"Canceled\" headers

Let\'s style these two header cells with green and red hues to represent
the \"good\" of a new member and the \"bummer\" of a canceled
membership.

[css]

```css
thead > tr:last-of-type > th:nth-of-type(1) {
  background-color: rgb(225, 255, 225);
}

thead > tr:last-of-type > th:nth-of-type(2) {
  background-color: rgb(255, 225, 225);
}

```

Here we dig into the last row of the table\'s header block and give the
first header cell in it (the \"Joined\" header) a greenish color, and
the second header cell in it (the \"Canceled\" header) a reddish hue.

##### Color every body other row differently

It\'s common to help improve readability of table data by alternating
row colors. Let\'s add a bit of color to every even row:

[css]

```css
tbody > tr:nth-of-type(even) {
  background-color: rgb(237, 238, 242);
}

```

##### Give the left-side header some style

Since we want the first column to stand out as well, we\'ll add some
custom styling here, too.

[css]

```css
tbody > tr > th:first-of-type {
  text-align: left;
  background-color: rgb(225, 229, 244);
}

```

This styles the first header cell in each row of the table\'s body with
[`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
to left-justify the member names, and with a somewhat different
background color.

##### Justify the balances

Finally, since it\'s standard practice to right-justify currency values
in tables, let\'s do that here.

[css]

```css
tbody > tr > td:last-of-type {
  text-align: right;
}

```

This just sets the CSS
[`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
property for the last [`<td>`](td) in each body row to `"right"`.

Technical summary
-----------------

  --------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   None
  Permitted content                             Zero or more [`<td>`](td) and/or [`<th>`](th) elements; [script-supporting elements](https://developer.mozilla.org/en-US/docs/Glossary/Script-supporting_element) ([`<script>`](script) and [`<template>`](template)) are also allowed
  Tag omission                                  Start tag is mandatory. End tag may be omitted if the [`<tr>`](tr) element is immediately followed by a [`<tr>`](tr) element, or if the row is the last element in its parent table group ([`<thead>`](thead), [`<tbody>`](tbody) or [`<tfoot>`](tfoot)) element
  Permitted parents                             [`<table>`](table) (only if the table has no child [`<tbody>`](tbody) element, and even then only after any [`<caption>`](caption), [`<colgroup>`](colgroup), and [`<thead>`](thead) elements); otherwise, the parent must be [`<thead>`](thead), [`<tbody>`](tbody) or [`<tfoot>`](tfoot)
  Implicit ARIA role                            `row`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLTableRowElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableRowElement)
  --------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-tr-element]](https://html.spec.whatwg.org/multipage/tables.html#the-tr-element)

  ---------------------------------------------------------------------------------------------

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

`tr`

1

12

1

Yes

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`align`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`bgcolor`

1

12

1

Yes

≤15

1

4.4

18

4

≤14

1

1.0

`char`

1

12

No

Yes

15

≤4

4.4

18

No

14

≤3.2

1.0

`charoff`

1

12

No

Yes

15

≤4

4.4

18

No

14

≤3.2

1.0

`valign`

1

12

No

Yes

15

3

4.4

18

No

14

2

1.0

See also
--------

- [Learning area: HTML
    tables](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables):
    An introduction to using tables, including `<tr>`.
- [`HTMLTableRowElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableRowElement):
    the interface on which `<tr>` is based.
- Other table-related elements:
  - [`<table>`](table), [`<thead>`](thead), [`<tbody>`](tbody),
        [`<tfoot>`](tfoot), [`<td>`](td), [`<th>`](th),
        [`<caption>`](caption), [`<col>`](col), and
        [`<colgroup>`](colgroup)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr>>
