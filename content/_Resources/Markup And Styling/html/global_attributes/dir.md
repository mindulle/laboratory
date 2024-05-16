dir
===

The `dir` [global attribute](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) is an
[enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
attribute that indicates the directionality of the element\'s text.

Try it
------

It can have the following values:

- `ltr`, which means *left to right* and is to be used for languages
    that are written from the left to the right (like English);
- `rtl`, which means *right to left* and is to be used for languages
    that are written from the right to the left (like Arabic);
- `auto`, which lets the user agent decide. It uses a basic algorithm
    as it parses the characters inside the element until it finds a
    character with a strong directionality, then applies that
    directionality to the whole element.

**Note:** This attribute is mandatory for the [`<bdo>`](../element/bdo)
element where it has a different semantic meaning.

- This attribute is *not* inherited by the [`<bdi>`](../element/bdi)
    element. If not set, its value is `auto`.
- This attribute can be overridden by the CSS properties
    [`direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/direction)
    and
    [`unicode-bidi`](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi),
    if a CSS page is active and the element supports these properties.
- As the directionality of the text is semantically related to its
    content and not to its presentation, it is recommended that web
    developers use this attribute instead of the related CSS properties
    when possible. That way, the text will display correctly even on a
    browser that doesn\'t support CSS or has the CSS deactivated.
- The `auto` value should be used for data with an unknown
    directionality, like data coming from user input, eventually stored
    in a database.

**Note:** Browsers might allow users to change the directionality of
[`<input>`](../element/input) and [`<textarea>`](../element/textarea)s
in order to assist with authoring content. Chrome and Safari provide a
directionality option in the contextual menu of input fields while
Legacy Edge uses the key combinations [Ctrl]
and [Ctrl]. Firefox uses
[Ctrl] but does NOT update
the `dir` attribute value.

Specifications
--------------

  ------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-dir-attribute]](https://html.spec.whatwg.org/multipage/dom.html#the-dir-attribute)

  ------------------------------------------------------------------------------------------------

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

`dir`

1

79

1

No

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

- All [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).
- [`HTMLElement.dir`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/dir)
    that reflects this attribute.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir>>
