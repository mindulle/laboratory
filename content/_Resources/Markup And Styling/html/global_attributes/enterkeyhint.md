enterkeyhint
============

The `enterkeyhint` [global attribute](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) is an
[enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
attribute defining what action label (or icon) to present for the enter
key on virtual keyboards.

Try it
------

Description
-----------

[Form controls](https://developer.mozilla.org/en-US/docs/Learn/Forms)
(such as [`<textarea>`](../element/textarea) or
[`<input>`](../element/input) elements) or elements using
[`contenteditable`](contenteditable) can specify an
[`inputmode`](inputmode) attribute to control what kind of virtual
keyboard will be used. To further improve the user\'s experience, the
enter key can be customized specifically by providing an `enterkeyhint`
attribute indicating how the enter key should be labeled (or which icon
should be shown). The enter key usually represents what the user should
do next; typical actions are: sending text, inserting a new line, or
searching.

If no `enterkeyhint` attribute is provided, the user agent might use
contextual information from the [`inputmode`](inputmode),
[`type`](../element/input#input_types), or
[`pattern`](../element/input#pattern) attributes to display a suitable
enter key label (or icon).

### Values

The `enterkeyhint` attribute is an
[enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
attribute and only accepts the following values:

  Value                       Description                                                                                          Example label (depends on user agent and user language)
  --------------------------- ---------------------------------------------------------------------------------------------------- ---------------------------------------------------------
  `enterkeyhint="enter"`      Typically inserting a new line.                                                                      [↵]
  `enterkeyhint="done"`       Typically meaning there is nothing more to input and the input method editor (IME) will be closed.   [Done]
  `enterkeyhint="go"`         Typically meaning to take the user to the target of the text they typed.                             [Open]
  `enterkeyhint="next"`       Typically taking the user to the next field that will accept text.                                   [Next]
  `enterkeyhint="previous"`   Typically taking the user to the previous field that will accept text.                               [Previous]
  `enterkeyhint="search"`     Typically taking the user to the results of searching for the text they have typed.                  [Search]
  `enterkeyhint="send"`       Typically delivering the text to its target.                                                         [Send]

Specifications
--------------

  --------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  attr-enterkeyhint]](https://html.spec.whatwg.org/multipage/interaction.html#attr-enterkeyhint)

  --------------------------------------------------------------------------------------------------------

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

`enterkeyhint`

77

79

94

No

66

13.1

77

77

94

57

13.4

12.0

See also
--------

- [`HTMLElement.enterKeyHint`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/enterKeyHint)
    property reflecting this attribute
- [`inputmode`](inputmode) global attribute
- [`contenteditable`](contenteditable) global attribute
- [`type`](../element/input#input_types) and
    [`pattern`](../element/input#pattern) attributes on
    [`<input>`](../element/input) elements

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/enterkeyhint>>
