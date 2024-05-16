hyphenate-character
===================

The `hyphenate-character`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the character (or string) used at the end of a line before a hyphenation
break.

Both automatic and soft hyphens are displayed according to the specified
hyphenate-character value.

Try it
------

Syntax
------

[css]

```css
hyphenate-character: <string>;
hyphenate-character: auto;
```

The value either sets the string to use instead of a hyphen, or
indicates that the user agent should select an appropriate string based
on the current typographic conventions (default).

### Values

[`<string>`](#string)

:   The [`<string>`](string.md) to use at the end of the line before a
    hyphenation break. The user agent may truncate this value if too
    many characters are used.

[`auto`](#auto)

:   The user-agent selects an appropriate string based on the content
    language\'s typographic conventions. This is the default property
    value, and only needs to be explicitly set in order to override a
    different inherited value.

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
hyphenate-character = 
  auto      |
  <string>  
```

Examples
--------

This example shows two identical blocks of text that have
[`hyphens`](hyphens.md) set to ensure that they break wherever needed, and
on soft hyphen breaks (created using `&shy;`). The first block has the
value of the hyphen changed to the equals symbol (\"`=`\"). The second
block has no hyphenate-character set, which is equivalent to
`hyphenate-character: auto` for user agents that support this property.

### HTML

[html]

```html
<dl>
  <dt><code>hyphenate-character: "="</code></dt>
  <dd id="string" lang="en">Superc&shy;alifragilisticexpialidocious</dd>
  <dt><code>hyphenate-character is not set</code></dt>
  <dd lang="en">Superc&shy;alifragilisticexpialidocious</dd>
</dl>
```

### CSS

[css]

```css
dd {
  width: 90px;
  border: 1px solid black;
  hyphens: auto;
}

dd#string {
  -webkit-hyphenate-character: "=";
  hyphenate-character: "=";
}
```

### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [CSS Text Module Level 4\
  [\#
  propdef-hyphenate-character]](https://drafts.csswg.org/css-text-4/#propdef-hyphenate-character)

  ---------------------------------------------------------------------------------------------------------

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

`hyphenate-character`

1066

10679

98

No

9215

175.1

1064.4

10618

98

7214

175

20.01.0

See also
--------

- Related CSS properties: [`hyphens`](hyphens.md),
    [`overflow-wrap`](overflow-wrap.md).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/hyphenate-character>
