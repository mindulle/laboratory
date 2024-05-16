\<tbody\>: The Table Body element
=================================

The `<tbody>` [HTML](../index) element encapsulates a set of table rows
([`<tr>`](tr) elements), indicating that they comprise the body of the
table ([`<table>`](table)).

Try it
------

The `<tbody>` element, along with its related [`<thead>`](thead) and
[`<tfoot>`](tfoot) elements, provide useful semantic information that
can be used when rendering for either screen or printer.

  --------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   None.
  Permitted content                             Zero or more [`<tr>`](tr) elements.
  Tag omission                                  A `<tbody>` element\'s start tag can be omitted if the first thing inside the `<tbody>` element is a [`<tr>`](tr) element, and if the element is not immediately preceded by a `<tbody>`, [`<thead>`](thead), or [`<tfoot>`](tfoot) element whose end tag has been omitted. (It can\'t be omitted if the element is empty.) A `<tbody>` element\'s end tag can be omitted if the `<tbody>` element is immediately followed by a `<tbody>` or [`<tfoot>`](tfoot) element, or if there is no more content in the parent element.
  Permitted parents                             Within the required parent [`<table>`](table) element, the `<tbody>` element can be added after a [`<caption>`](caption), [`<colgroup>`](colgroup), and a [`<thead>`](thead) element.
  Implicit ARIA role                            `rowgroup`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLTableSectionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableSectionElement)
  --------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

### Deprecated attributes

[`align`](#align) [Deprecated]

:   This
    [enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
    attribute specifies how horizontal alignment of each cell content
    will be handled. Possible values are:

    -   `left`, aligning the content to the left of the cell
    -   `center`, centering the content in the cell
    -   `right`, aligning the content to the right of the cell
    -   `justify`, inserting spaces into the textual content so that the
        content is justified in the cell
    -   `char`, aligning the textual content on a special character with
        a minimal offset, defined by the [`char`](#char) and
        [`charoff`](#charoff) attributes.

    If this attribute is not set, the `left` value is assumed.

    As this attribute is deprecated, use the CSS
    [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
    property instead.

     
    **Note:** The equivalent `text-align` property for the
    `align="char"` is not implemented in any browsers yet. See the
    [`text-align`\'s browser compatibility
    section](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align#browser_compatibility)
    for the `<string>` value.

[`bgcolor`](#bgcolor) [Deprecated]

:   The background color of the table. It is a [6-digit hexadecimal RGB
    code](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color),
    prefixed by a \'`#`\'. One of the predefined [color
    keywords](https://developer.mozilla.org/en-US/docs/Web/CSS/named-color)
    can also be used.

    As this attribute is deprecated, use the CSS
    [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color)
    property instead.

[`char`](#char) [Deprecated]

:   This attribute is used to set the character to align the cells in a
    column on. Typical values for this include a period (`.`) when
    attempting to align numbers or monetary values. If [`align`](#align)
    is not set to `char`, this attribute is ignored.

[`charoff`](#charoff) [Deprecated]

:   This attribute is used to indicate the number of characters to
    offset the column data from the alignment characters specified by
    the `char` attribute.

[`valign`](#valign) [Deprecated]

:   This attribute specifies the vertical alignment of the text within
    each row of cells of the table header. Possible values for this
    attribute are:

    -   `baseline`, which will put the text as close to the bottom of
        the cell as it is possible, but align it on the
        [baseline](https://en.wikipedia.org/wiki/Baseline_%28typography%29)
        of the characters instead of the bottom of them. If characters
        are all of the size, this has the same effect as `bottom`.
    -   `bottom`, which will put the text as close to the bottom of the
        cell as it is possible;
    -   `middle`, which will center the text in the cell;
    -   and `top`, which will put the text as close to the top of the
        cell as it is possible.

    As this attribute is deprecated, use the CSS
    [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)
    property instead.

Usage notes
-----------

- If the table includes a [`<thead>`](thead) block (to semantically
    identify a row of column headers), the `<tbody>` block *must* come
    after it.
- If [`<tr>`](tr) elements are specified outside an existing `<tbody>`
    element, as direct children of the [`<table>`](table), these
    elements will be encapsulated by a separate `<tbody>` element
    generated by the browser.
- When printing a document, the `<thead>` and [`<tfoot>`](tfoot)
    elements specify information that may be the same---or at least very
    similar---on every page of a multipage table, while the `<tbody>`
    element\'s contents generally will differ from page to page.
- When a table is presented in a screen context (such as a window)
    which is not large enough to display the entire table, the [user
    agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
    may let the user scroll the contents of the `<thead>`, `<tbody>`,
    `<tfoot>`, and [`<caption>`](caption) blocks separately from one
    another for the same parent table.
- You *may* use more than one `<tbody>` per table as long as they are
    all consecutive. This lets you divide the rows in large tables into
    sections, each of which may be separately formatted if so desired.
    If not marked up to be consecutive elements, browsers will correct
    this author error, ensuring any `<thead>` and `<tfoot>` elements are
    rendered as the first and last elements of the table, respectively.

Examples
--------

Below are some examples showing the use of the `<tbody>` element. For
more examples of this element, see the examples for
[`<table>`](table#examples).

### Basic example

In this relatively simple example, we create a table containing
information about a group of students with a [`<thead>`](thead) and a
[`<tbody>`](tbody), with a number of rows in the body.

#### HTML

The table\'s HTML is shown here. Note that all the body cells including
information about students are contained within a single `<tbody>`
element.

[html]

```html
<table>
  <thead>
    <tr>
      <th>Student ID</th>
      <th>Name</th>
      <th>Major</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>3741255</td>
      <td>Jones, Martha</td>
      <td>Computer Science</td>
    </tr>
    <tr>
      <td>3971244</td>
      <td>Nim, Victor</td>
      <td>Russian Literature</td>
    </tr>
    <tr>
      <td>4100332</td>
      <td>Petrov, Alexandra</td>
      <td>Astrophysics</td>
    </tr>
  </tbody>
</table>
```

#### CSS

The CSS to style our table is shown next.

[css]

```css
table {
  border: 2px solid #555;
  border-collapse: collapse;
  font:
    16px "Lucida Grande",
    "Helvetica",
    "Arial",
    sans-serif;
}

```

First, the table\'s overall style attributes are set, configuring the
thickness, style, and color of the table\'s exterior borders and using
[`border-collapse`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse)
to ensure that the border lines are shared among adjacent cells rather
than each having its own borders with space in between.
[`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) is used
to establish an initial font for the table.

[css]

```css
th,
td {
  border: 1px solid #bbb;
  padding: 2px 8px 0;
  text-align: left;
}

```

Then the style is set for the majority of the cells in the table,
including all data cells but also those styles shared between our
[`<td>`](td) and [`<th>`](th) cells. The cells are given a light gray
outline which is a single pixel thick, padding is adjusted, and all
cells are left-aligned using
[`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)

[css]

```css
thead > tr > th {
  background-color: #cce;
  font-size: 18px;
  border-bottom: 2px solid #999;
}

```

Finally, header cells contained within the [`<thead>`](thead) element
are given additional styling. They use a darker
[`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color),
a larger font size, and a thicker, darker bottom border than the other
cell borders.

#### Result

The resulting table looks like this:

### Multiple bodies

You can create row groupings within a table by using multiple `<tbody>`
elements. Each may potentially have its own header row or rows; however,
*there can be only one [`<thead>`](thead) per table!* Because of that,
you need to use a [`<tr>`](tr) filled with [`<th>`](th) elements to
create headers within each `<tbody>`. Let\'s see how that\'s done.

Let\'s take the previous example, add some more students to the list,
and update the table so that instead of listing each student\'s major on
every row, the students are grouped by major, with heading rows for each
major.

#### Result

First, the resulting table, so you know what we\'re building:

#### HTML

The revised HTML looks like this:

[html]

```html
<table>
  <thead>
    <tr>
      <th>Student ID</th>
      <th>Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th colspan="2">Computer Science</th>
    </tr>
    <tr>
      <td>3741255</td>
      <td>Jones, Martha</td>
    </tr>
    <tr>
      <td>4077830</td>
      <td>Pierce, Benjamin</td>
    </tr>
    <tr>
      <td>5151701</td>
      <td>Kirk, James</td>
    </tr>
  </tbody>
  <tbody>
    <tr>
      <th colspan="2">Russian Literature</th>
    </tr>
    <tr>
      <td>3971244</td>
      <td>Nim, Victor</td>
    </tr>
  </tbody>
  <tbody>
    <tr>
      <th colspan="2">Astrophysics</th>
    </tr>
    <tr>
      <td>4100332</td>
      <td>Petrov, Alexandra</td>
    </tr>
    <tr>
      <td>8892377</td>
      <td>Toyota, Hiroko</td>
    </tr>
  </tbody>
</table>
```

Notice that each major is placed in a separate `<tbody>` block, the
first row of which contains a single [`<th>`](th) element with a
[`colspan`](#colspan) attribute that spans the entire width of the
table. That heading lists the name of the major contained within the
`<tbody>`.

Then each remaining row in each major\'s `<tbody>` consists of two
cells: the first for the student\'s ID and the second for their name.

#### CSS

Most of the CSS is unchanged. We do, however, add a slightly more subtle
style for header cells contained directly within a `<tbody>` (as opposed
to those which reside in a [`<thead>`](thead)). This is used for the
headers indicating each table section\'s corresponding major.

[css]

```css
tbody > tr > th {
  background-color: #dde;
  border-bottom: 1.5px solid #bbb;
  font-weight: normal;
}

```

Specifications
--------------

  ---------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-tbody-element]](https://html.spec.whatwg.org/multipage/tables.html#the-tbody-element)

  ---------------------------------------------------------------------------------------------------

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

`tbody`

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

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

`valign`

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

See also
--------

- CSS properties and
    [pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
    that may be specially useful to style the `<tbody>` element:
  - the
        [`:nth-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child)
        pseudo-class to set the alignment on the cells of the column;
  - the
        [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
        property to align all cells content on the same character, like
        \'.\'.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody>
