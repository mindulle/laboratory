\<col\>: The Table Column element
=================================

The `<col>` [HTML](../index) element defines a column within a table and
is used for defining common semantics on all common cells. It is
generally found within a [`<colgroup>`](colgroup) element.

Try it
------

`<col>` allows styling columns using CSS, but only a few properties will
have an effect on the column ([see the CSS 2.1
specification](https://www.w3.org/TR/CSS21/tables.html#columns) for a
list).

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`span`](#span)

:   This attribute contains a positive integer indicating the number of
    consecutive columns the `<col>` element spans. If not present, its
    default value is `1`.

### Deprecated attributes

The following attributes are deprecated and should not be used. They are
documented below for reference when updating existing code and for
historical interest only.

[`align`](#align) [Deprecated]

:   This
    [enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
    attribute specifies how horizontal alignment of each column cell
    content will be handled. Possible values are:

    -   `left`, aligning the content to the left of the cell
    -   `center`, centering the content in the cell
    -   `right`, aligning the content to the right of the cell
    -   `justify`, inserting spaces into the textual content so that the
        content is justified in the cell

    If this attribute is not set, its value is inherited from the
    [`align`](colgroup#align) of the [`<colgroup>`](colgroup) element
    this `<col>` element belongs too. If there are none, the `left`
    value is assumed.

     
    **Note:** To achieve the same effect as the `left`, `center`,
    `right` or `justify` values, do not try to set the
    [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
    property on a selector giving a `<col>` element. Because
    [`<td>`](td) elements are not descendant of the `<col>` element,
    they won\'t inherit it.

    If the table doesn\'t use a [`colspan`](td#colspan) attribute, use
    the `td:nth-child(an+b)` CSS selector. Set `a` to zero and `b` to
    the position of the column in the table, e.g.
    `td:nth-child(2) { text-align: right; }` to right-align the second
    column.

    If the table does use a [`colspan`](td#colspan) attribute, the
    effect can be achieved by combining adequate CSS attribute selectors
    like `[colspan=n]`, though this is not trivial.

[`bgcolor`](#bgcolor) [Deprecated]

:   The background color of the table. It is a [6-digit hexadecimal RGB
    code](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color),
    prefixed by a \'`#`\'. One of the predefined [color
    keywords](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#named_colors)
    can also be used.

    To achieve a similar effect, use the CSS
    [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color)
    property.

[`char`](#char) [Deprecated]

:   This attribute sets the character to align the cells in a column on.
    Typical values for this include a period (.) when attempting to
    align numbers or monetary values. If [`align`](#align) is not set to
    `char`, this attribute is ignored.

[`charoff`](#charoff) [Deprecated]

:   This attribute is used to indicate the number of characters to
    offset the column data from the alignment characters specified by
    the `char` attribute.

[`valign`](#valign) [Deprecated]

:   This attribute specifies the vertical alignment of the text within
    each cell of the column. Possible values for this attribute are:

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

     
    **Note:** Do not try to set the
    [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)
    property on a selector giving a `<col>` element. Because
    [`<td>`](td) elements are not descendant of the `<col>` element,
    they won\'t inherit it.

    If the table doesn\'t use a [`colspan`](td#colspan) attribute, use
    the `td:nth-child(an+b)` CSS selector where \'a\' is the total
    number of the columns in the table and \'b\' is the ordinal position
    of the column in the table. Only after this selector the
    `vertical-align` property can be used.

    If the table does use a [`colspan`](td#colspan) attribute, the
    effect can be achieved by combining adequate CSS attribute selectors
    like `[colspan=n]`, though this is not trivial.

[`width`](#width) [Deprecated]

:   This attribute specifies a default width for each column in the
    current column group. In addition to the standard pixel and
    percentage values, this attribute might take the special form `0*`,
    which means that the width of each column in the group should be the
    minimum width necessary to hold the column\'s contents. Relative
    widths such as `5*` also can be used.

Examples
--------

Please see the [`<table>`](table) page for examples on `<col>`.

Technical summary
-----------------

  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   None.
  Permitted content                             None; it is a [void element](https://developer.mozilla.org/en-US/docs/Glossary/Void_element).
  Tag omission                                  It must have start tag, but must not have an end tag.
  Permitted parents                             [`<colgroup>`](colgroup) only, though it can be implicitly defined as its start tag is not mandatory. The [`<colgroup>`](colgroup) must not have a [`span`](colgroup#span) attribute.
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLTableColElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableColElement)
  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -----------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-col-element]](https://html.spec.whatwg.org/multipage/tables.html#the-col-element)

  -----------------------------------------------------------------------------------------------

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

`col`

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

15

1

4.4

18

4

14

1

1.0

`char`

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

`charoff`

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

`span`

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

`width`

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

See also
--------

- CSS properties and pseudo-classes that may be specially useful to
    style the `<col>` element:
  - the
        [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width)
        property to control the width of the column;
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
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col>>
