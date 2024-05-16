exportparts
===========

The `exportparts` [global attribute](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) allows you to
select and style elements existing in nested [shadow
trees](https://developer.mozilla.org/en-US/docs/Glossary/Shadow_tree),
by exporting their `part` names.

The shadow tree is an isolated structure where identifiers, classes, and
styles cannot be reached by selectors or queries belonging to a regular
DOM. To apply a style to an element living in a shadow tree, by CSS rule
created outside of it, [`part`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#part) global
attribute has to be used. It has to be assigned to an element present in
Shadow Tree, and its value should be some identifier. Rules present
outside of the shadow tree, must use the
[`::part`](https://developer.mozilla.org/en-US/docs/Web/CSS/::part)
pseudo-element, containing the same identifier as the argument.

The global attribute [`part`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#part) makes the
element visible on just a single level of depth. When the shadow tree is
nested, parts will be visible only to the parent of the shadow tree but
not to its ancestor. Exporting parts further down is exactly what
`exportparts` attribute is for.

Attribute `exportparts` must be placed on a *shadow Host*, which is the
element to which the *shadow tree* is attached. The value of the
attribute should be a comma-separated list of part names present in the
shadow tree and which should be made available via a DOM outside of the
current structure.

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------------------------------

  [CSS Shadow Parts\
  [\#
  element-attrdef-html-global-exportparts]](https://drafts.csswg.org/css-shadow-parts/#element-attrdef-html-global-exportparts)

  ---------------------------------------------------------------------------------------------------------------------------------------

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

`exportparts`

73

79

72

No

60

13.1

73

73

79

?

13.4

11.0

See also
--------

- All [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/exportparts>>
