\@charset
=========

The `@charset` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[at-rule](at-rule.md) specifies the character encoding used in the style
sheet. It must be the first element in the style sheet and not be
preceded by any character; as it is not a [](_Resources/Markup%20And%20Styling/css/syntax.md#nested_statements), it cannot be used inside
[conditional group at-rules](at-rule.md#conditional_group_rules). If
several `@charset` at-rules are defined, only the first one is used, and
it cannot be used inside a `style` attribute on an HTML element or
inside the
[`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style)
element where the character set of the HTML page is relevant.

[css]

```css
@charset "utf-8";
```

This at-rule is useful when using
non-[ASCII](https://developer.mozilla.org/en-US/docs/Glossary/ASCII)
characters in some CSS properties, like [`content`](content.md).

As there are several ways to define the character encoding of a style
sheet, the browser will try the following methods in the following order
(and stop as soon as one yields a result) :

1. The value of the [Unicode
    byte-order](https://en.wikipedia.org/wiki/Byte_order_mark) character
    placed at the beginning of the file.
2. The value given by the `charset` attribute of the `Content-Type:`
    HTTP header or the equivalent in the protocol used to serve the
    style sheet.
3. The `@charset` CSS at-rule.
4. Use the character encoding defined by the referring document: the
    `charset` attribute of the
    [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link)
    element. This method is obsolete and should not be used.
5. Assume that the document is UTF-8

Syntax
------

[css]

```css
@charset "UTF-8";
@charset "iso-8859-15";
```

### Formal syntax

```
@charset "<charset>";
```

[*charset*](#charset)

:   A [`<string>`](string.md) denoting the character encoding to be used.
    It must be the name of a web-safe character encoding defined in the
    [IANA-registry](https://www.iana.org/assignments/character-sets/character-sets.xhtml),
    and must be double-quoted, following exactly one space character
    (U+0020), and immediately terminated with a semicolon. If several
    names are associated with an encoding, only the one marked with
    *preferred* must be used.

Examples
--------

### Valid and invalid charset declarations

[css]

```css
@charset "UTF-8"; /* Set the encoding of the style sheet to Unicode UTF-8 */
```

[css]

```css
@charset 'iso-8859-15'; /* Invalid, wrong quotes used */
@charset  "UTF-8"; /* Invalid, more than one space */
 @charset "UTF-8"; /* Invalid, there is a character (a space) before the at-rule */
@charset UTF-8; /* Invalid, the charset is a CSS <string> and requires double-quotes */
```

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Cascading Style Sheets Level 2 Revision 2 (CSS 2.2) Specification\
  [\# charset①]](#)

  -----------------------------------------------------------------------

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

`@charset`

2

12

1.5Firefox 1 supported an invalid syntax where the character encoding is
not between single or double quotes.

5.5From Internet Explorer 5.5 to IE 7 (inclusive), Internet Explorer
supported an invalid syntax where the character encoding is not between
single or double quotes.

9

4

2

18

4

10.1

4

1.0

See also
--------

- [Character
    set](https://developer.mozilla.org/en-US/docs/Glossary/Character_set)
    glossary entry
- [Unicode](https://developer.mozilla.org/en-US/docs/Glossary/Unicode)
    glossary entry

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@charset>
