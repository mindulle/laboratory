autocapitalize
==============

The `autocapitalize` [global attribute](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) is an
[enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
attribute that controls whether and how text input is automatically
capitalized as it is entered/edited by the user.

The attribute must take one of the following values:

- `off` or `none`: No autocapitalization is applied (all letters
    default to lowercase)
- `on` or `sentences`: The first letter of each sentence defaults to a
    capital letter; all other letters default to lowercase
- `words`: The first letter of each word defaults to a capital letter;
    all other letters default to lowercase
- `characters`: All letters should default to uppercase

The `autocapitalize` attribute doesn\'t affect behavior when typing on a
physical keyboard. Instead, it affects the behavior of other input
mechanisms, such as virtual keyboards on mobile devices and voice input.
The behavior of such mechanisms is that they often assist users by
automatically capitalizing the first letter of sentences. The
`autocapitalize` attribute enables authors to override that behavior
per-element.

The `autocapitalize` attribute never causes autocapitalization to be
enabled for an [`<input>`](../element/input) element with a
[`type`](../element/input#type) attribute whose value is `url`, `email`,
or `password`.

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  attr-autocapitalize]](https://html.spec.whatwg.org/multipage/interaction.html#attr-autocapitalize)

  ------------------------------------------------------------------------------------------------------------

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

`autocapitalize`

43

79

111

No

30

No

43

43

111

30

5

4.0

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/autocapitalize>>
