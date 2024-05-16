spellcheck
==========

The `spellcheck` [global attribute](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) is an
[enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
attribute that defines whether the element may be checked for spelling
errors.

Try it
------

It may have the following values:

- empty string or `true`, which indicates that the element should be,
    if possible, checked for spelling errors;
- `false`, which indicates that the element should not be checked for
    spelling errors.

If this attribute is not set, its default value is element-type and
browser-defined. This default value may also be *inherited*, which means
that the element content will be checked for spelling errors only if its
nearest ancestor has a *spellcheck* state of `true`.

This attribute is merely a hint for the browser: browsers are not
required to check for spelling errors. Typically non-editable elements
are not checked for spelling errors, even if the `spellcheck` attribute
is set to `true` and the browser supports spellchecking.

Security and privacy concerns
-----------------------------

Using spellchecking can have consequences for users\' security and
privacy. The specification does not regulate *how* spellchecking is done
and the content of the element may be sent to a third party for
spellchecking results (see [enhanced spellchecking and
\"spell-jacking\"](https://www.otto-js.com/news/article/chrome-and-edge-enhanced-spellcheck-features-expose-pii-even-your-passwords)).

You should consider setting `spellcheck` to `false` for elements that
can contain sensitive information.

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  attr-spellcheck]](https://html.spec.whatwg.org/multipage/interaction.html#attr-spellcheck)

  ----------------------------------------------------------------------------------------------------

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

`spellcheck`

9

12

Yes

11

Yes

Yes

47

47

57

37

9.3

5.0

See also
--------

- All [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/spellcheck>>
