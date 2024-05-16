::grammar-error
===============

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `::grammar-error`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-element](pseudo-elements.md) represents a text segment which the
[user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) has
flagged as grammatically incorrect.

Allowable properties
--------------------

Only a small subset of CSS properties can be used in a rule with
`::grammar-error` in its selector:

- [`color`](_Resources/Markup%20And%20Styling/css/color.md)
- [`background-color`](background-color.md)
- [`cursor`](cursor.md)
- [`caret-color`](caret-color.md)
- [`outline`](outline.md) and its longhands
- [`text-decoration`](text-decoration.md) and its associated properties
- [`text-emphasis-color`](text-emphasis-color.md)
- [`text-shadow`](text-shadow.md)

Syntax
------

[css]

```css
::grammar-error {
  /* ... */
}
```

Examples
--------

### Simple document grammar check

In this example, eventual supporting browsers should highlight any
flagged grammatical errors with the styles shown.

#### HTML

[html]

```html
<p>My friends is coming to the party tonight.</p>
```

#### CSS

[css]

```css
::grammar-error {
  text-decoration: underline red;
  color: red;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------

  [CSS Pseudo-Elements Module Level 4\
  [\#
  selectordef-grammar-error]](https://drafts.csswg.org/css-pseudo/#selectordef-grammar-error)

  -----------------------------------------------------------------------------------------------------

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

`::grammar-error`

No

No

No

No

No

No

No

No

No

No

No

No

See also
--------

- [`::spelling-error`](::spelling-error)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/::grammar-error>
