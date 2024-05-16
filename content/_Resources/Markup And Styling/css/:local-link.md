:local-link
===========

The `:local-link`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents a link to the same document.
Therefore an element that is the source anchor of a hyperlink whose
target\'s absolute URL matches the element\'s own document URL.

[css]

```css
/* Selects any <a> that links to the current document */
a:local-link {
  color: green;
}
```

Syntax
------

[css]

```css
:local-link {
  /* ... */
}
```

Examples
--------

### HTML

[html]

```html
<a href="#target">This is a link on the current page.</a><br />
<a href="https://example.com">This is an external link</a><br />
```

### CSS

[css]

```css
a:local-link {
  color: green;
}
```

### Result

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  local-link-pseudo]](https://drafts.csswg.org/selectors/#local-link-pseudo)

  ------------------------------------------------------------------------------------

Browser compatibility
---------------------

See also
--------

- Link-related pseudo-classes: [`:link`](:link),
    [`:visited`](:visited), [`:hover`](:hover), [`:active`](:active),
    [`:any-link`](:any-link)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:local-link>
