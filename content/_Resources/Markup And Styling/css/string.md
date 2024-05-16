\<string\>
==========

The `<string>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[data type](css_types.md) represents a sequence of characters. Strings are
used in numerous CSS properties, such as [`content`](content.md),
[`font-family`](_Resources/Markup%20And%20Styling/css/font-family.md), and [`quotes`](quotes.md).

Syntax
------

The `<string>` data type is composed of any number of
[Unicode](https://en.wikipedia.org/wiki/Unicode) characters surrounded
by either double (`"`) or single (`'`) quotes.

Most characters can be represented literally. All characters can also be
represented with their respective [Unicode code
points](https://en.wikipedia.org/wiki/Unicode#Code_point_planes_and_blocks)
in hexadecimal, in which case they are preceded by a backslash (`\`).
For example, `\22` represents a double quote, `\27` a single quote
(`'`), and `\A9` the copyright symbol (`©`).

Importantly, certain characters which would otherwise be invalid can be
escaped with a backslash. These include double quotes when used inside a
double-quoted string, single quotes when used inside a single-quoted
string, and the backslash itself. For example, `\\` will create a single
backslash.

To output new lines, you must escape them with a line feed character
such as `\A` or `\00000A`. In your code, however, strings can span
multiple lines, in which case each new line must be escaped with a `\`
as the last character of the line.

However, to get new lines, you must also set the
[`white-space`](white-space.md) property to appropriate value.

**Note:** [HTML
entities](https://developer.mozilla.org/en-US/docs/Glossary/Entity)
(such as `&nbsp;` or `&#8212;`) cannot be used in a CSS `<string>`.

Examples
--------

### Examples of valid strings

[css]

```css
/* Simple strings */
"This string is demarcated by double quotes."
'This string is demarcated by single quotes.'

/* Character escaping */
"This is a string with \" an escaped double quote."
"This string also has \22 an escaped double quote."
'This is a string with \' an escaped single quote.'
'This string also has \27 an escaped single quote.'
"This is a string with \\ an escaped backslash."

/* New line in a string */
"This string has a \Aline break in it."

/* String spanning two lines of code (these two strings will have identical output) */
"A really long \
awesome string"
"A really long awesome string"
```

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\# strings]](https://drafts.csswg.org/css-values/#strings)

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

`string`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

`unicode_escaped_characters`

1

12

1

6

7

1

≤37

18

4

10.1

1

1.0

See also
--------

- [CSS Units and Values](css_values_and_units.md)
- [CSS Basic Data Types](css_types.md)
- [Introduction to CSS: Values and
    Units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/string>
