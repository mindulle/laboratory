\<caption\>: The Table Caption element
======================================

The `<caption>` [HTML](../index) element specifies the caption (or
title) of a table.

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
    attribute indicates how the caption must be aligned with respect to
    the table. It may have one of the following values:

    [`left`](#left)

    :   The caption is displayed to the left of the table.

    [`top`](#top)

    :   The caption is displayed above the table.

    [`right`](#right)

    :   The caption is displayed to the right of the table.

    [`bottom`](#bottom)

    :   The caption is displayed below the table.

     
    **Warning:** Do not use this attribute, as it has been deprecated.
    The [`<caption>`](caption) element should be styled using the
    [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) properties
    [`caption-side`](https://developer.mozilla.org/en-US/docs/Web/CSS/caption-side)
    and
    [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align).

Usage notes
-----------

If used, the `<caption>` element must be the first child of its parent
[`<table>`](table) element.

When the `<table>` element that contains the `<caption>` is the only
descendant of a [`<figure>`](figure) element, you should use the
[`<figcaption>`](figcaption) element instead of `<caption>`.

A
[`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color)
on the table will not include the caption. Add a `background-color` to
the `<caption>` element as well if you want the same color to be behind
both.

Example
-------

This simple example presents a table that includes a caption.

[html]

```html
<table>
  <caption>
    Example Caption
  </caption>
  <tr>
    <th>Login</th>
    <th>Email</th>
  </tr>
  <tr>
    <td>user1</td>
    <td>user1@sample.com</td>
  </tr>
  <tr>
    <td>user2</td>
    <td>user2@sample.com</td>
  </tr>
</table>
```

Technical summary
-----------------

  --------------------------------------------- ---------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   None.
  Permitted content                             [Flow content](../content_categories#flow_content).
  Tag omission                                  The end tag can be omitted if the element is not immediately followed by ASCII whitespace or a comment.
  Permitted parents                             A [`<table>`](table) element, as its first descendant.
  Implicit ARIA role                            `caption`
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLTableCaptionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCaptionElement)
  --------------------------------------------- ---------------------------------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-caption-element]](https://html.spec.whatwg.org/multipage/tables.html#the-caption-element)

  -------------------------------------------------------------------------------------------------------

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

`caption`

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

≤4

4.4

18

4

14

≤3.2

1.0

See also
--------

- CSS properties that may be specially useful to style the
    [`<caption>`](caption) element:
  - [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align),
        [`caption-side`](https://developer.mozilla.org/en-US/docs/Web/CSS/caption-side).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption>>
