\<colgroup\>: The Table Column Group element
============================================

The `<colgroup>` [HTML](../index) element defines a group of columns
within a table.

Try it
------

Attributes
----------

This element\'s attributes include the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`span`](#span)

:   This attribute contains a positive integer indicating the number of
    consecutive columns the `<colgroup>` element spans. If not present,
    its default value is `1`.

    The `span` attribute is not permitted if there are one or more
    [`<col>`](col) elements within the `<colgroup>`.

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
    -   `char`, aligning the textual content on a special character with
        a minimal offset, defined by the [`char`](col#char) and
        [`charoff`](col#charoff) attributes.

    If this attribute is not set, the `left` value is assumed. The
    descendant [`<col>`](col) elements may override this value using
    their own [`align`](col#align) attribute.

     
    **Note:** Do not try to set the
    [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
    property on a selector giving a [`<colgroup>`](colgroup) element.
    Because [`<td>`](td) elements are not descendant of the
    [`<colgroup>`](colgroup) element, they won\'t inherit it.

    If the table doesn\'t use a [`colspan`](td#colspan) attribute, use
    one `td:nth-child(an+b)` CSS selector per column, where \'a\' is the
    total number of the columns in the table and \'b\' is the ordinal
    position of this column in the table. Only after this selector the
    `text-align` property can be used.

    If the table does use a [`colspan`](td#colspan) attribute, the
    effect can be achieved by combining adequate CSS attribute selectors
    like `[colspan=n]`, though this is not trivial.

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

:   This attribute specifies the alignment of the content in a column
    group to a character. Typical values for this include a period (.)
    when attempting to align numbers or monetary values. If
    [`align`](#align) is not set to `char`, this attribute is ignored,
    though it will still be used as the default value for the
    [`align`](col#align) of the [`<col>`](col) which are members of this
    column group.

[`charoff`](#charoff) [Deprecated]

:   This attribute is used to indicate the number of characters to
    offset the column data from the alignment character specified by the
    `char` attribute.

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
    property on a selector giving a `<colgroup>` element. Because
    [`<td>`](td) elements are not descendant of the `<colgroup>`
    element, they won\'t inherit it.

    If the table doesn\'t use a [`colspan`](td#colspan) attribute, use
    the `td:nth-child(an+b)` CSS selector per column, where \'a\' is the
    total number of the columns in the table and \'b\' is the ordinal
    position of the column in the table. Only after this selector the
    `vertical-align` property can be used.

    If the table does use a [`colspan`](td#colspan) attribute, the
    effect can be achieved by combining adequate CSS attribute selectors
    like `[colspan=n]`, though this is not trivial.

Examples
--------

Please see the [`<table>`](table) page for examples on `<colgroup>`.

Technical summary
-----------------

  ------------------------------------ -----------------------------------------------------------------------------------------------
  [Content                             None.
  categories](../content_categories)

  Permitted content                    If the [`span`](colgroup#span) attribute is present: none.\
                                       If the attribute is not present: zero or more [`<col>`](col) element

  Tag omission                         The start tag may be omitted, if it has a [`<col>`](col) element as its first child and if it
                                       is not preceded by a [`<colgroup>`](colgroup) whose end tag has been omitted.\
                                       The end tag may be omitted, if it is not followed by a space or a comment.

  Permitted parents                    A [`<table>`](table) element. The [`<colgroup>`](colgroup) must appear after any optional
                                       [`<caption>`](caption) element but before any [`<thead>`](thead), [`<th>`](th),
                                       [`<tbody>`](tbody), [`<tfoot>`](tfoot) and [`<tr>`](tr) element.

  Implicit ARIA role                   [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)

  Permitted ARIA roles                 No `role` permitted

  DOM interface                        [`HTMLTableColElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableColElement)
  ------------------------------------ -----------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-colgroup-element]](https://html.spec.whatwg.org/multipage/tables.html#the-colgroup-element)

  ---------------------------------------------------------------------------------------------------------

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

`colgroup`

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

- CSS properties and
    [pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
    that may be specially useful to style the `<col>` element:
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
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/colgroup>>
