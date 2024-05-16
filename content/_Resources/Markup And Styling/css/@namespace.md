\@namespace
===========

`@namespace` is an [at-rule](at-rule.md) that defines XML
[namespaces](https://developer.mozilla.org/en-US/docs/Glossary/Namespace)
to be used in a
[CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS) [style
sheet](https://developer.mozilla.org/en-US/docs/Web/API/StyleSheet).

Try it
------

Syntax
------

[css]

```css
/* Default namespace */
@namespace url(XML-namespace-URL);
@namespace "XML-namespace-URL";

/* Prefixed namespace */
@namespace prefix url(XML-namespace-URL);
@namespace prefix "XML-namespace-URL";
```

Description
-----------

The defined namespaces can be used to restrict the
[universal](universal_selectors.md), [type](type_selectors.md), and
[attribute](attribute_selectors.md)
[selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)
to only select elements within that namespace. The `@namespace` rule is
generally only useful when dealing with documents containing multiple
namespaces---such as HTML with inline SVG or MathML, or XML that mixes
multiple vocabularies.

Any `@namespace` rules must follow all [`@charset`](@charset.md) and
[`@import`](@import.md) rules, and precede all other at-rules and [style
declarations](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration)
in a style sheet.

`@namespace` can be used to define the **default namespace** for the
style sheet. When a default namespace is defined, all universal and type
selectors (but not attribute selectors, see note below) apply only to
elements in that namespace.

The `@namespace` rule can also be used to define a **namespace prefix**.
When a universal, type, or attribute selector is prefixed with a
namespace prefix, then that selector only matches if the namespace *and*
name of the element or attribute matches.

In HTML, known [foreign
elements](https://html.spec.whatwg.org/multipage/syntax.html#foreign-elements)
will automatically be assigned namespaces. This means that HTML elements
will act as though they are in the XHTML namespace
(`http://www.w3.org/1999/xhtml`), even if there is no `xmlns` attribute
anywhere in the document, and the
[`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg)
and
[`<math>`](https://developer.mozilla.org/en-US/docs/Web/MathML/Element/math)
elements will be assigned their proper namespaces
(`http://www.w3.org/2000/svg` and `http://www.w3.org/1998/Math/MathML`,
respectively).

**Note:** In XML, unless a prefix is defined directly on an attribute
(*e.g.*, `xlink:href`), that attribute has no namespace. In other words,
attributes do not inherit the namespace of the element they\'re on. To
match this behavior, the default namespace in CSS does not apply to
attribute selectors.

Formal syntax
-------------

Error: could not find syntax for this item

Examples
--------

### Specifying default and prefixed namespaces

[css]

```css
@namespace url(http://www.w3.org/1999/xhtml);
@namespace svg url(http://www.w3.org/2000/svg);

/* This matches all XHTML <a> elements, as XHTML is the default unprefixed namespace */
a {
}

/* This matches all SVG <a> elements */
svg|a {
}

/* This matches both XHTML and SVG <a> elements */
*|a {
}
```

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

`@namespace`

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

- [Namespaces crash
    course](https://developer.mozilla.org/en-US/docs/Web/SVG/Namespaces_Crash_Course)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@namespace>
