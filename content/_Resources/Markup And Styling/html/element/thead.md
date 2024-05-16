\<thead\>: The Table Head element
=================================

The `<thead>` [HTML](../index) element defines a set of rows defining
the head of the columns of the table.

Try it
------

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

     
    **Warning:** Do not use this attribute as it is obsolete (not
    supported) in the latest standard.

    -   To align values, use the CSS
        [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
        property instead.

[`bgcolor`](#bgcolor) [Deprecated]

:   This attribute defines the background color of each column cell. It
    accepts a 6-digit hexadecimal color or a named color. Alpha
    transparency is not supported.

    **Note:** Do not use this attribute, as it is non-standard. The
    `thead` element should be styled using the CSS
    [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color)
    property, which can be applied to any element, including the
    `thead`, [`<tr>`](tr), [`<td>`](td) and [`<th>`](th) elements.

[`char`](#char) [Deprecated]

:   This attribute is used to set the character to align the cells in a
    column on. Typical values for this include a period (.) when
    attempting to align numbers or monetary values. If [`align`](#align)
    is not set to `char`, this attribute is ignored.

    **Note:** Do not use this attribute as it is obsolete (and not
    supported) in the latest standard.

[`charoff`](#charoff) [Deprecated]

:   This attribute is used to indicate the number of characters to
    offset the column data from the alignment characters specified by
    the **char** attribute.

    **Note:** Do not use this attribute as it is obsolete (and not
    supported) in the latest standard.

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
    -   `top`, which will put the text as close to the top of the cell
        as it is possible.

     
    **Note:** Do not use this attribute as it is obsolete (and not
    supported) in the latest standard: instead set the CSS
    [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)
    property on it.

Examples
--------

See [`<table>`](table) for examples on `<thead>`.

Technical summary
-----------------

  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   None.
  Permitted content                             Zero or more [`<tr>`](tr) elements.
  Tag omission                                  The start tag is mandatory. The end tag may be omitted if the [`<thead>`](thead) element is immediately followed by a [`<tbody>`](tbody) or [`<tfoot>`](tfoot) element.
  Permitted parents                             A [`<table>`](table) element. The [`<thead>`](thead) must appear after any [`<caption>`](caption) or [`<colgroup>`](colgroup) element, even implicitly defined, but before any [`<tbody>`](tbody), [`<tfoot>`](tfoot) and [`<tr>`](tr) element.
  Implicit ARIA role                            `rowgroup`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLTableSectionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableSectionElement)
  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-thead-element]](https://html.spec.whatwg.org/multipage/tables.html#the-thead-element)

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

`thead`

1

12

1

Yes

≤12.1

1Backgrounds applied to `<thead>` elements will be applied to each table
cell, rather than the entire header. To mimic the behavior of other
browsers, set the `background-attachment` CSS property to `fixed`.

4.4

18

4

≤12.1

1Backgrounds applied to `<thead>` elements will be applied to each table
cell, rather than the entire header. To mimic the behavior of other
browsers, set the `background-attachment` CSS property to `fixed`.

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

- Other table-related HTML Elements: [`<caption>`](caption),
    [`<col>`](col), [`<colgroup>`](colgroup), [`<table>`](table),
    [`<tbody>`](tbody), [`<td>`](td), [`<tfoot>`](tfoot), [`<th>`](th),
    [`<tr>`](tr);
- CSS properties and pseudo-classes that may be specially useful to
    style the `<thead>` element:
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
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead>>
