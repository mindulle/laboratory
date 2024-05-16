\<tfoot\>: The Table Foot element
=================================

The `<tfoot>` [HTML](../index) element defines a set of rows summarizing
the columns of the table.

Try it
------

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

### Deprecated attributes

The following attributes are deprecated and should not be used. They are
documented below for reference when updating existing code and for
historical interest only.

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

     
    **Note:**

    -   To achieve the same effect as the `left`, `center`, `right` or
        `justify` values, use the CSS
        [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
        property on it.
    -   To achieve the same effect as the `char` value, in CSS, you can
        use the value of the [`char`](#char) as the value of the
        [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
        property.

[`bgcolor`](#bgcolor) [Deprecated]

:   The background color of the table. It is a [6-digit hexadecimal RGB
    code](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color),
    prefixed by a \'`#`\'. One of the predefined [color
    keywords](https://developer.mozilla.org/en-US/docs/Web/CSS/named-color)
    can also be used.

    To achieve a similar effect, use the CSS
    [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color)
    property.

[`char`](#char) [Deprecated]

:   This attribute specifies the alignment of the content in a column to
    a character. Typical values for this include a period (.) when
    attempting to align numbers or monetary values. If [`align`](#align)
    is not set to `char`, this attribute is ignored.

[`charoff`](#charoff) [Deprecated]

:   This attribute is used to indicate the number of characters to
    offset the column data from the alignment characters specified by
    the `char` attribute.

[`valign`](#valign) [Deprecated]

:   This attribute specifies the vertical alignment of the text within
    each row of cells of the table footer. Possible values for this
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

     
    **Note:** Do not use this attribute as it is obsolete (and not
    supported) in the latest standard: instead set the CSS
    [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)
    property on it.

Examples
--------

Please see the [`<table>`](table) page for examples on `<tfoot>`.

Technical summary
-----------------

  ------------------------------------ -------------------------------------------------------------------------------------------------------
  [Content                             None.
  categories](../content_categories)

  Permitted content                    Zero or more [`<tr>`](tr) elements.

  Tag omission                         The start tag is mandatory. The end tag may be omitted if there is no more content in the parent
                                       [`<table>`](table) element.

  Permitted parents                    A [`<table>`](table) element. The [`<tfoot>`](tfoot) must appear after any [`<caption>`](caption),
                                       [`<colgroup>`](colgroup), [`<thead>`](thead), [`<tbody>`](tbody), or [`<tr>`](tr) element. Note that
                                       this is the requirement in HTML.\
                                       Originally, in HTML4, the opposite was true: the [`<tfoot>`](tfoot) element could not be placed after
                                       any [`<tbody>`](tbody) or [`<tr>`](tr) element.

  Implicit ARIA role                   `rowgroup`

  Permitted ARIA roles                 Any

  DOM interface                        [`HTMLTableSectionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableSectionElement)
  ------------------------------------ -------------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-tfoot-element]](https://html.spec.whatwg.org/multipage/tables.html#the-tfoot-element)

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

`tfoot`

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

- Other table-related HTML Elements: [`<caption>`](caption),
    [`<col>`](col), [`<colgroup>`](colgroup), [`<table>`](table),
    [`<tbody>`](tbody), [`<td>`](td), [`<th>`](th), [`<thead>`](thead),
    [`<tr>`](tr);
- CSS properties and pseudo-classes that may be specially useful to
    style the `<tfoot>` element:
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
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot>>
