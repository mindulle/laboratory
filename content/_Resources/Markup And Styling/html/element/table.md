\<table\>: The Table element
============================

The `<table>` [HTML](../index) element represents tabular data --- that
is, information presented in a two-dimensional table comprised of rows
and columns of cells containing data.

Try it
------

+-----------------------------------+-----------------------------------+
| [Content                          | [Flow                             |
| c                                 | content](..                       |
| ategories](../content_categories) | /content_categories#flow_content) |
+-----------------------------------+-----------------------------------+
| Permitted content                 | In this order:                    |
|                                   |                                   |
|                                   | 1.  an optional                   |
|                                   |     [`<caption>`](caption)        |
|                                   |     element,                      |
|                                   | 2.  zero or more                  |
|                                   |     [`<colgroup>`](colgroup)      |
|                                   |     elements,                     |
|                                   | 3.  an optional                   |
|                                   |     [`<thead>`](thead) element,   |
|                                   | 4.  either one of the following:  |
|                                   |     -   zero or more              |
|                                   |         [`<tbody>`](tbody)        |
|                                   |         elements                  |
|                                   |     -   one or more [`<tr>`](tr)  |
|                                   |         elements                  |
|                                   | 5.  an optional                   |
|                                   |     [`<tfoot>`](tfoot) element    |
+-----------------------------------+-----------------------------------+
| Tag omission                      | None, both the starting and       |
|                                   | ending tag are mandatory.         |
+-----------------------------------+-----------------------------------+
| Permitted parents                 | Any element that accepts flow     |
|                                   | content                           |
+-----------------------------------+-----------------------------------+
| Implicit ARIA role                | `table`                           |
+-----------------------------------+-----------------------------------+
| Permitted ARIA roles              | Any                               |
+-----------------------------------+-----------------------------------+
| DOM interface                     | [`HTMLTableElement`](             |
|                                   | https://developer.mozilla.org/en->> |
|                                   | US/docs/Web/API/HTMLTableElement) |
+-----------------------------------+-----------------------------------+

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

### Deprecated attributes

[`align`](#align) [Deprecated]

:   This
    [enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
    attribute indicates how the table must be aligned inside the
    containing document. It may have the following values:

    -   `left`: the table is displayed on the left side of the document;
    -   `center`: the table is displayed in the center of the document;
    -   `right`: the table is displayed on the right side of the
        document.

    Set
    [`margin-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left)
    and
    [`margin-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-right)
    to achieve an effect that is similar to the align attribute:

    -   `left`: `margin-right: auto; margin-left: 0;`
    -   `center`: `margin-right: auto; margin-left: auto;`
    -   `right`: `margin-right: 0; margin-left: auto;`

[`bgcolor`](#bgcolor) [Deprecated]

:   The background color of the table. It is a [6-digit hexadecimal RGB
    code](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color),
    prefixed by a \'`#`\'. One of the predefined [color
    keywords](https://developer.mozilla.org/en-US/docs/Web/CSS/named-color)
    can also be used.

    To achieve a similar effect, use the CSS
    [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color)
    property.

[`border`](#border) [Deprecated]

:   This integer attribute defines, in pixels, the size of the frame
    surrounding the table. If set to 0, the [`frame`](#frame) attribute
    is set to void.

    To achieve a similar effect, use the CSS
    [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border)
    shorthand property.

[`cellpadding`](#cellpadding) [Deprecated]

:   This attribute defines the space between the content of a cell and
    its border, displayed or not. If the cellpadding\'s length is
    defined in pixels, this pixel-sized space will be applied to all
    four sides of the cell\'s content. If the length is defined using a
    percentage value, the content will be centered and the total
    vertical space (top and bottom) will represent this value. The same
    is true for the total horizontal space (left and right).

    To achieve a similar effect, apply the
    [`border-collapse`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse)
    property to the `<table>` element, with its value set to collapse,
    and the
    [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding)
    property to the [`<td>`](td) elements.

[`cellspacing`](#cellspacing) [Deprecated]

:   This attribute defines the size of the space between two cells in a
    percentage value or pixels. The attribute is applied both
    horizontally and vertically, to the space between the top of the
    table and the cells of the first row, the left of the table and the
    first column, the right of the table and the last column and the
    bottom of the table and the last row.

    To achieve a similar effect, apply the
    [`border-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-spacing)
    property to the `<table>` element. `border-spacing` does not have
    any effect if
    [`border-collapse`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse)
    is set to collapse.

[`frame`](#frame) [Deprecated]

:   This enumerated attribute defines which side of the frame
    surrounding the table must be displayed.

    To achieve a similar effect, use the
    [`border-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-style)
    and
    [`border-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-width)
    properties.

[`rules`](#rules) [Deprecated]

:   This enumerated attribute defines where rules, i.e. lines, should
    appear in a table. It can have the following values:

    -   `none`, which indicates that no rules will be displayed; it is
        the default value;
    -   `groups`, which will cause the rules to be displayed between row
        groups (defined by the [`<thead>`](thead), [`<tbody>`](tbody)
        and [`<tfoot>`](tfoot) elements) and between column groups
        (defined by the [`<col>`](col) and [`<colgroup>`](colgroup)
        elements) only;
    -   `rows`, which will cause the rules to be displayed between rows;
    -   `cols`, which will cause the rules to be displayed between
        columns;
    -   `all`, which will cause the rules to be displayed between rows
        and columns.

    To achieve a similar effect, apply the
    [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border)
    property to the appropriate [`<thead>`](thead), [`<tbody>`](tbody),
    [`<tfoot>`](tfoot), [`<col>`](col), or [`<colgroup>`](colgroup)
    elements.

[`summary`](#summary) [Deprecated]

:   This attribute defines an alternative text that summarizes the
    content of the table. Use the [`<caption>`](caption) element
    instead.

[`width`](#width) [Deprecated]

:   This attribute defines the width of the table. Use the CSS
    [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width)
    property instead.

**Note:** While no HTML specification includes `height` as a `<table>`
attribute, some browsers support a non-standard interpretation of
`height`. The unitless value sets a minimum absolute height in pixels.
If set as a percent value, the minimum table height will be relative to
the height of the parent container.

Examples
--------

### Simple table

[html]

```html
<table>
  <tr>
    <td>John</td>
    <td>Doe</td>
  </tr>
  <tr>
    <td>Jane</td>
    <td>Doe</td>
  </tr>
</table>
```

#### Result

### Further simple examples

[html]

```html
<p>Simple table with header</p>
<table>
  <tr>
    <th>First name</th>
    <th>Last name</th>
  </tr>
  <tr>
    <td>John</td>
    <td>Doe</td>
  </tr>
  <tr>
    <td>Jane</td>
    <td>Doe</td>
  </tr>
</table>

<p>Table with thead, tfoot, and tbody</p>
<table>
  <thead>
    <tr>
      <th>Header content 1</th>
      <th>Header content 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Body content 1</td>
      <td>Body content 2</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Footer content 1</td>
      <td>Footer content 2</td>
    </tr>
  </tfoot>
</table>

<p>Table with colgroup</p>
<table>
  <colgroup span="4"></colgroup>
  <tr>
    <th>Countries</th>
    <th>Capitals</th>
    <th>Population</th>
    <th>Language</th>
  </tr>
  <tr>
    <td>USA</td>
    <td>Washington, D.C.</td>
    <td>309 million</td>
    <td>English</td>
  </tr>
  <tr>
    <td>Sweden</td>
    <td>Stockholm</td>
    <td>9 million</td>
    <td>Swedish</td>
  </tr>
</table>

<p>Table with colgroup and col</p>
<table>
  <colgroup>
    <col style="background-color: #0f0" />
    <col span="2" />
  </colgroup>
  <tr>
    <th>Lime</th>
    <th>Lemon</th>
    <th>Orange</th>
  </tr>
  <tr>
    <td>Green</td>
    <td>Yellow</td>
    <td>Orange</td>
  </tr>
</table>

<p>Simple table with caption</p>
<table>
  <caption>
    Awesome caption
  </caption>
  <tr>
    <td>Awesome data</td>
  </tr>
</table>
```

#### Result

### Table sorting

#### Sorting table rows

There are no native methods for sorting the rows ([`<tr>`](tr) elements)
of an HTML table. But using
[`Array.prototype.slice()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice),
[`Array.prototype.sort()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort),
[`Node.removeChild()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/removeChild),
and
[`Node.appendChild()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild),
you can implement your own `sort()` function to sort an
[`HTMLCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection)
of `<tr>` elements.

In the below example, you can see such an example. We are attaching it
to the \<tbody\> element so that it sorts the table cells in order of
increasing value, and updates the display to suit.

##### HTML

[html]

```html
<table>
  <tbody>
    <tr>
      <td>3</td>
    </tr>
    <tr>
      <td>2</td>
    </tr>
    <tr>
      <td>1</td>
    </tr>
  </tbody>
</table>
```

##### JavaScript

[js]

```js
HTMLTableSectionElement.prototype.sort = function (cb) {
  Array.from(this.rows)
    .sort(cb)
    .forEach((e) => this.appendChild(this.removeChild(e)));
};

document
  .querySelector("table")
  .tBodies[0].sort((a, b) => a.textContent.localeCompare(b.textContent));
```

##### Result

#### Sorting rows with a click on the th element

The following example adds an event handler to every `<th>` element of
every `<table>` in the `document`; it sorts all the `<tbody>`\'s rows,
basing the sorting on the `td` cells contained in the rows.

**Note:** This solution assumes that the `<td>` elements are populated
by raw text with no descendant elements.

##### HTML

[html]

```html
<table>
  <thead>
    <tr>
      <th>Numbers</th>
      <th>Letters</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>3</td>
      <td>A</td>
    </tr>
    <tr>
      <td>2</td>
      <td>B</td>
    </tr>
    <tr>
      <td>1</td>
      <td>C</td>
    </tr>
  </tbody>
</table>
```

##### JavaScript

[js]

```js
const allTables = document.querySelectorAll("table");

for (const table of allTables) {
  const tBody = table.tBodies[0];
  const rows = Array.from(tBody.rows);
  const headerCells = table.tHead.rows[0].cells;

  for (const th of headerCells) {
    const cellIndex = th.cellIndex;

    th.addEventListener("click", () => {
      rows.sort((tr1, tr2) => {
        const tr1Text = tr1.cells[cellIndex].textContent;
        const tr2Text = tr2.cells[cellIndex].textContent;
        return tr1Text.localeCompare(tr2Text);
      });

      tBody.append(...rows);
    });
  }
}
```

##### Result

### Displaying large tables in small spaces

A common issue with tables on the web is that they don\'t natively work
very well on small screens when the amount of content is large, and the
way to make them scrollable isn\'t obvious, especially when the markup
may come from a CMS and cannot be modified to have a wrapper.

This example provides one way to display tables in small spaces. We\'ve
hidden the HTML content as it is very large, and there is nothing
remarkable about it. The CSS is more useful to inspect in this example.

When looking at these styles you\'ll notice that table\'s
[`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
property has been set to `block`. While this allows scrolling, the table
loses some of its integrity, and table cells try to become as small as
possible. To mitigate this issue we\'ve set
[`white-space`](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space)
to `nowrap` on the `<tbody>`. However, we don\'t do this for the
`<thead>` to avoid long titles forcing columns to be wider than they
need to be to display the data.

To keep the table headers on the page while scrolling down we\'ve set
[`position`](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
to sticky on the `<th>` elements. Note that we have **not** set
[`border-collapse`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse)
to `collapse`, as if we do the header cannot be separated correctly from
the rest of the table.

[css]

```css
table,
th,
td {
  border: 1px solid;
}

table {
  width: 100%;
  max-width: 400px;
  height: 240px;
  margin: 0 auto;
  display: block;
  overflow-x: auto;
  border-spacing: 0;
}

tbody {
  white-space: nowrap;
}

th,
td {
  padding: 5px 10px;
  border-top-width: 0;
  border-left-width: 0;
}

th {
  position: sticky;
  top: 0;
  background: #fff;
  vertical-align: bottom;
}

th:last-child,
td:last-child {
  border-right-width: 0;
}

tr:last-child td {
  border-bottom-width: 0;
}

```

#### Result

Accessibility concerns
----------------------

### Captions

By supplying a [`<caption>`](caption) element whose value clearly and
concisely describes the table\'s purpose, it helps the people decide if
they need to read the rest of the table content or skip over it.

This helps people navigating with the aid of assistive technology such
as a screen reader, people experiencing low vision conditions, and
people with cognitive concerns.

- [MDN Adding a caption to your table with
    \<caption\>](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Advanced#adding_a_caption_to_your_table_with_caption)
- [Caption & Summary • Tables • W3C WAI Web Accessibility
    Tutorials](https://www.w3.org/WAI/tutorials/tables/caption-summary/)

### Scoping rows and columns

The [`scope`](th#scope) attribute on header elements is redundant in
simple contexts, because scope is inferred. However, some assistive
technologies may fail to draw correct inferences, so specifying header
scope may improve user experiences. In complex tables, scope can be
specified to provide necessary information about the cells related to a
header.

#### Examples

[html]

```html
<table>
  <caption>
    Color names and values
  </caption>
  <tbody>
    <tr>
      <th scope="col">Name</th>
      <th scope="col">HEX</th>
      <th scope="col">HSLa</th>
      <th scope="col">RGBa</th>
    </tr>
    <tr>
      <th scope="row">Teal</th>
      <td><code>#51F6F6</code></td>
      <td><code>hsl(180 90% 64% / 1)</code></td>
      <td><code>rgb(81 246 246 / 1)</code></td>
    </tr>
    <tr>
      <th scope="row">Goldenrod</th>
      <td><code>#F6BC57</code></td>
      <td><code>hsl(38 90% 65% / 1)</code></td>
      <td><code>rgba(246 188 87 / 1)</code></td>
    </tr>
  </tbody>
</table>
```

##### Result

Providing a declaration of `scope="col"` on a [`<th>`](th) element will
help describe that the cell is at the top of a column. Providing a
declaration of `scope="row"` on a [`<th>`](th) element will help
describe that the cell is the first in a row.

- [MDN Tables for visually impaired
    users](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Advanced#tables_for_visually_impaired_users)
- [Tables with two headers • Tables • W3C WAI Web Accessibility
    Tutorials](https://www.w3.org/WAI/tutorials/tables/two-headers/)
- [Tables with irregular headers • Tables • W3C WAI Web Accessibility
    Tutorials](https://www.w3.org/WAI/tutorials/tables/irregular/)
- [H63: Using the scope attribute to associate header cells and data
    cells in data tables \| W3C Techniques for WCAG
    2.0](https://www.w3.org/TR/WCAG20-TECHS/H63.html)

### Complicated tables

Assistive technology such as screen readers may have difficulty parsing
tables that are so complex that header cells can\'t be associated in a
strictly horizontal or vertical way. This is typically indicated by the
presence of the [`colspan`](td#colspan) and [`rowspan`](td#rowspan)
attributes.

Ideally, consider alternate ways to present the table\'s content,
including breaking it apart into a collection of smaller, related tables
that don\'t have to rely on using the `colspan` and `rowspan`
attributes. In addition to helping people who use assistive technology
understand the table\'s content, this may also benefit people with
cognitive concerns who may have difficulty understanding the
associations the table layout is describing.

If the table cannot be broken apart, use a combination of the
[`id`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#id) and [`headers`](td#headers) attributes
to programmatically associate each table cell with the header(s) the
cell is associated with.

- [MDN Tables for visually impaired
    users](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Advanced#tables_for_visually_impaired_users)
- [Tables with multi-level headers • Tables • W3C WAI Web
    Accessibility
    Tutorials](https://www.w3.org/WAI/tutorials/tables/multi-level/)
- [H43: Using id and headers attributes to associate data cells with
    header cells in data tables \| Techniques for W3C WCAG
    2.0](https://www.w3.org/TR/WCAG20-TECHS/H43.html)

Specifications
--------------

  ---------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-table-element]](https://html.spec.whatwg.org/multipage/tables.html#the-table-element)

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

`table`

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

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`bgcolor`

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

`border`

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

`cellpadding`

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

`cellspacing`

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

`frame`

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

`rules`

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

`summary`

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

`width`

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

See also
--------

- [HTML data table
    tutorial](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables)
- CSS properties that may be especially useful to style the `<table>`
    element:
  - [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width)
        to control the width of the table;
  - [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border),
        [`border-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-style),
        [`border-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-color),
        [`border-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-width),
        [`border-collapse`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse),
        [`border-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-spacing)
        to control the aspect of cell borders, rules, and frame;
  - [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)
        and
        [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding)
        to style the individual cell content;
  - [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
        and
        [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)
        to define the alignment of text and cell content.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table>>
