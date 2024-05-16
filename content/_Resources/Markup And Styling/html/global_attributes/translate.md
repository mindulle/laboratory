translate
=========

The `translate` [global attribute](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) is an
[enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
attribute that is used to specify whether an element\'s *translatable
attribute* values and its
[`Text`](https://developer.mozilla.org/en-US/docs/Web/API/Text) node
children should be translated when the page is localized, or whether to
leave them unchanged.

It can have the following values:

- empty string or `yes`, which indicates that the element should be
    translated when the page is localized.
- `no`, which indicates that the element must not be translated.

Although not all browsers recognize this attribute, it is respected by
automatic translation systems such as Google Translate, and may also be
respected by tools used by human translators. As such it\'s important
that web authors use this attribute to mark content that should not be
translated.

Examples
--------

In this example, the `translate` attribute is used to ask translation
tools not to translate the company\'s brand name in the footer.

[html]

```html
<footer>
  <small>© 2020 <span translate="no">BrandName</span></small>
</footer>
```

Specifications
--------------

  ------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  attr-translate]](https://html.spec.whatwg.org/multipage/dom.html#attr-translate)

  ------------------------------------------------------------------------------------------

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

`translate`

19

79

111

No

15

6

4.4

25

111

14

6

1.5

See also
--------

- All [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).
- The [`HTMLElement.translate`] property that
    reflects this attribute.
- [Using HTML\'s translate
    attribute](https://www.w3.org/International/questions/qa-translate-flag).
- HTML [`lang`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#lang) attribute

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/translate>>
