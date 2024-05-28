::spelling-error
================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `::spelling-error`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-element](pseudo-elements.md) represents a text segment which the
[user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) has
flagged as incorrectly spelled.

Allowable properties
--------------------

Only a small subset of CSS properties can be used in a rule with
`::spelling-error` in its selector:

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
::spelling-error {
  /* ... */
}
```

Examples
--------

### Simple document spell check

In this example, eventual supporting browsers should highlight any
flagged spelling errors with the styles shown.

#### HTML

[html]

```html
<p contenteditable spellcheck="true">
  My friends are coegdfgfddffbgning to the party tonight.
</p>
```

#### CSS

[css]

```css
::spelling-error {
  text-decoration: wavy red;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [CSS Pseudo-Elements Module Level 4\
  [\#
  selectordef-spelling-error]](https://drafts.csswg.org/css-pseudo/#selectordef-spelling-error)

  -------------------------------------------------------------------------------------------------------

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

`::spelling-error`

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

- [`::grammar-error`](::grammar-error)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/::spelling-error>
