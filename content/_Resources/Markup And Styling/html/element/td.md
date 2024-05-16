\<td\>: The Table Data Cell element
===================================

The `<td>` [HTML](../index) element defines a cell of a table that
contains data. It participates in the *table model*.

Try it
------

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`colspan`](#colspan)

:   This attribute contains a non-negative integer value that indicates
    for how many columns the cell extends. Its default value is `1`.
    Values higher than 1000 will be considered as incorrect and will be
    set to the default value (1).

[`headers`](#headers)

:   This attribute contains a list of space-separated strings, each
    corresponding to the **id** attribute of the [`<th>`](th) elements
    that apply to this element.

[`rowspan`](#rowspan)

:   This attribute contains a non-negative integer value that indicates
    for how many rows the cell extends. Its default value is `1`; if its
    value is set to `0`, it extends until the end of the table section
    ([`<thead>`](thead), [`<tbody>`](tbody), [`<tfoot>`](tfoot), even if
    implicitly defined), that the cell belongs to. Values higher than
    65534 are clipped down to 65534.

### Deprecated attributes

[`abbr`](#abbr) [Deprecated]

:   This attribute contains a short abbreviated description of the
    cell\'s content. Some user-agents, such as speech readers, may
    present this description before the content itself.

    **Note:** Do not use this attribute as it is obsolete in the latest
    standard. Alternatively, you can put the abbreviated description
    inside the cell and place the long content in the **title**
    attribute.

[`align`](#align) [Deprecated]

:   This
    [enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
    attribute specifies how the cell content\'s horizontal alignment
    will be handled. Possible values are:

    -   `left`: The content is aligned to the left of the cell.
    -   `center`: The content is centered in the cell.
    -   `right`: The content is aligned to the right of the cell.
    -   `justify` (with text only): The content is stretched out inside
        the cell so that it covers its entire width.
    -   `char` (with text only): The content is aligned to a character
        inside the `<th>` element with minimal offset. This character is
        defined by the [`char`](#char) and [`charoff`](#charoff)
        attributes.

    The default value when this attribute is not specified is `left`.

     
    **Note:**

    -   To achieve the same effect as the `left`, `center`, `right` or
        `justify` values, apply the CSS
        [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
        property to the element.
    -   To achieve the same effect as the `char` value, give the
        [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
        property the same value you would use for the [`char`](#char).

[`axis`](#axis) [Deprecated]

:   This attribute contains a list of space-separated strings. Each
    string is the `id` of a group of cells that this header applies to.

[`bgcolor`](#bgcolor) [Deprecated]

:   This attribute defines the background color of each cell in a
    column. It is a [6-digit hexadecimal RGB
    code](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color),
    prefixed by a \'`#`\'. One of the predefined [color
    keywords](https://developer.mozilla.org/en-US/docs/Web/CSS/named-color)
    can also be used.

    To achieve a similar effect, use the CSS
    [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color)
    property.

[`char`](#char) [Deprecated]

:   The content in the cell element is aligned to a character. Typical
    values include a period (.) to align numbers or monetary values. If
    [`align`](#align) is not set to `char`, this attribute is ignored.

[`charoff`](#charoff) [Deprecated]

:   This attribute is used to shift column data to the right of the
    character specified by the **char** attribute. Its value specifies
    the length of this shift.

[`height`](#height) [Deprecated]

:   This attribute is used to define a recommended cell height. Use the
    CSS
    [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height)
    property instead.

[`scope`](#scope) [Deprecated]

:   This enumerated attribute defines the cells that the header (defined
    in the [`<th>`](th)) element relates to. Only use this attribute
    with the `<th>` element to define the row or column for which it is
    a header.

[`valign`](#valign) [Deprecated]

:   This attribute specifies how a text is vertically aligned inside a
    cell. Possible values for this attribute are:

    -   `baseline`: Positions the text near the bottom of the cell and
        aligns it with the
        [baseline](https://en.wikipedia.org/wiki/Baseline_%28typography%29)
        of the characters instead of the bottom. If characters don\'t
        descend below the baseline, the baseline value achieves the same
        effect as `bottom`.
    -   `bottom`: Positions the text near the bottom of the cell.
    -   `middle`: Centers the text in the cell.
    -   and `top`: Positions the text near the top of the cell.

    To achieve a similar effect, use the CSS
    [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)
    property.

[`width`](#width) [Deprecated]

:   This attribute is used to define a recommended cell width. Use the
    CSS
    [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width)
    property instead.

Examples
--------

See [`<table>`](table) for examples on `<td>`.

Technical summary
-----------------

  ------------------------------------ -------------------------------------------------------------------------------------------------
  [Content                             Sectioning root.
  categories](../content_categories)

  Permitted content                    [Flow content](../content_categories#flow_content).

  Tag omission                         The start tag is mandatory.\
                                       The end tag may be omitted, if it is immediately followed by a [`<th>`](th) or [`<td>`](td)
                                       element or if there are no more data in its parent element.

  Permitted parents                    A [`<tr>`](tr) element.

  Implicit ARIA role                   `cell` if a descendant of a [`<table>`](table) element

  Permitted ARIA roles                 Any

  DOM interface                        [`HTMLTableCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCellElement)
  ------------------------------------ -------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-td-element]](https://html.spec.whatwg.org/multipage/tables.html#the-td-element)

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

`td`

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

`abbr`

1

12

1

Yes

15

1

4.4

18

4

14

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

`axis`

1

12

1

Yes

15

1

4.4

18

4

14

1

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

`colspan`

1

12

1

Yes

15

1

4.4

18

4

14

1

1.0

`headers`

1

12

1

Yes

15

1

4.4

18

4

14

1

1.0

`rowspan`

1

12

1

Yes

15

1

4.4

18

4

14

1

1.0

`scope`

1

12

1

Yes

15

1

4.4

18

4

14

1

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

`width`

1

12

1

Yes

15

1

4.4

18

4

14

1

1.0

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td>>
