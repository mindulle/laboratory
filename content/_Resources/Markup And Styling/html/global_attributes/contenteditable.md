contenteditable
===============

The `contenteditable` [global attribute](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) is an
enumerated attribute indicating if the element should be editable by the
user. If so, the browser modifies its widget to allow editing.

Try it
------

The attribute must take one of the following values:

- `true` or an *empty string*, which indicates that the element is
    editable.
- `false`, which indicates that the element is not editable.
- `plaintext-only`, which indicates that the element\'s raw text is
    editable, but rich text formatting is disabled.

If the attribute is given without a value, like
`<label contenteditable>Example Label</label>`, its value is treated as
an empty string.

If this attribute is missing or its value is invalid, its value is
*inherited* from its parent element: so the element is editable if its
parent is editable.

Note that although its allowed values include `true` and `false`, this
attribute is an
*[enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)*
one and not a *Boolean* one.

You can set the color used to draw the text insertion
[caret](https://developer.mozilla.org/en-US/docs/Glossary/Caret) with
the CSS
[`caret-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color)
property.

Elements that are made editable, and therefore interactive, by using the
`contenteditable` attribute can be focused. They participate in
sequential keyboard navigation. However, elements with the
`contenteditable` attribute nested within other `contenteditable`
elements are not added to the tabbing sequence by default. You can add
the nested `contenteditable` elements to the keyboard navigation
sequence by specifying the `tabindex` value
([`tabindex="0"`](tabindex)).

Specifications
--------------

  --------------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  attr-contenteditable]](https://html.spec.whatwg.org/multipage/interaction.html#attr-contenteditable)

  --------------------------------------------------------------------------------------------------------------

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

`contenteditable`

1

12

3

5.5

9

≤4

4.4

18

4

14

≤3.2

1.0

`plaintext-only`

51

≤79

No

No

38

Yes

51

51

No

41

Yes

5.0

See also
--------

- All [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md)
- [`HTMLElement.contentEditable`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/contentEditable)
    and
    [`HTMLElement.isContentEditable`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/isContentEditable)
- The CSS
    [`caret-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color)
    property
- [HTMLElement `input`
    event](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/contenteditable>>
