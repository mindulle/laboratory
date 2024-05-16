CSS namespaces
==============

The **CSS namespaces** module defines the syntax for using
[namespaces](https://developer.mozilla.org/en-US/docs/Glossary/Namespace)
in CSS.

CSS isn\'t just for styling HTML. A stylesheet may be used to style SVG,
MathML, XML, or HTML, each of which has a different namespace or a
document containing multiple namespaces.

The [`@namespace`](@namespace.md) at-rule defined in this module enables
distinguishing between same-named elements in different namespaces.
Element tag names are not unique to a single language. For example, the
`<a>` element isn\'t limited to HTML. You may want to style the `<a>`s
within your SVGs differently from the links in your HTML. You also will
likely want to ensure that
[`querySelectorAll("a")`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)
selects the right kind of element. Namespacing can help.

The `@namespace` rule is used for declaring a default namespace and for
binding namespaces to namespace prefixes. The namespaces module also
defines the syntax for using these prefixes to represent
namespace-qualified names. That\'s it. What a name means or if the name
is even valid depends on the context and host language.

Reference
---------

### At-rules

- [`@namespace`](@namespace.md)

Guides
------

[Namespaces crash course](https://developer.mozilla.org/en-US/docs/Web/SVG/Namespaces_Crash_Course)

:   Deep dive into what a namespace is and how they are used in XML and
    XML-based markup languages.

Related concepts
----------------

- CSS [namespace separator (`|`)](namespace_separator.md) combinator
- CSS [type selectors](type_selectors.md)
- CSS [universal selector](universal_selectors.md)
- [`CSSNamespaceRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSNamespaceRule)
    interface
  - [`CSSNamespaceRule.namespaceURI`](https://developer.mozilla.org/en-US/docs/Web/API/CSSNamespaceRule/namespaceURI)
        property
  - [`CSSNamespaceRule.prefix`](https://developer.mozilla.org/en-US/docs/Web/API/CSSNamespaceRule/prefix)
        property
- [`Document.createAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createAttributeNS)
    method
- [`Document.createElementNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElementNS)
    method
- [`Document.getElementsByTagNameNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByTagNameNS)
    method
- [`Element.getAttributeNodeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNodeNS)
    method
- [`Element.getAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNS)
    method
- [`Element.getElementsByTagNameNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByTagNameNS)
    method
- [`Element.hasAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/hasAttributeNS)
    method
- [`Element.namespaceURI`](https://developer.mozilla.org/en-US/docs/Web/API/Element/namespaceURI)
    property
- [`Element.removeAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttributeNS)
    method
- [`Element.setAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNS)
    method
- [`Element.setAttributeNodeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNodeNS)
    method
- [`NamedNodeMap.getNamedItemNS()`](https://developer.mozilla.org/en-US/docs/Web/API/NamedNodeMap/getNamedItemNS)
    method
- [`NamedNodeMap.removeNamedItemNS()`](https://developer.mozilla.org/en-US/docs/Web/API/NamedNodeMap/removeNamedItemNS)
    method
- [`NamedNodeMap.setNamedItemNS()`](https://developer.mozilla.org/en-US/docs/Web/API/NamedNodeMap/setNamedItemNS)
    method
- [Namespace](https://developer.mozilla.org/en-US/docs/Glossary/Namespace)
    glossary term

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [CSS Namespaces Module Level 3\
  [\#
  declaration]](https://drafts.csswg.org/css-namespaces/#declaration)

  -----------------------------------------------------------------------------

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

`CSS_namespaces`

1

12

1

9

8

1

37

18

4

14

1

1.0

See also
--------

- [`<a>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/a#example)
    SVG element
- [CSS `url()` function](url.md)
- [CSS at-rules](at-rule.md)
- [CSS at-rule functions](at-rule-functions.md)
- [CSS selectors](css_selectors.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_namespaces>
