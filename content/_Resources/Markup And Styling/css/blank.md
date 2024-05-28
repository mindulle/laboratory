:blank
======

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

**Note:** The `:blank` selector is considered at risk, as the CSSWG
keeps changing it.

See [CSSWG issue
\#1967](https://github.com/w3c/csswg-drafts/issues/1967).

The `:blank` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) selects empty user input elements (e.g.
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
or
[`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)).

Syntax
------

[css]

```css
:blank {
  /* ... */
}
```

Examples
--------

### Simple :blank example

In eventual supporting browsers, the `:blank` pseudo-class will enable
developers to highlight in some way input controls that are not
required, but still have no content filled in, perhaps as a reminder to
users.

#### HTML

[html]

```html
<textarea></textarea>
```

#### CSS

[css]

```css
textarea:blank {
  border: 3px solid red;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  blank-pseudo]](https://drafts.csswg.org/selectors/#blank-pseudo)

  --------------------------------------------------------------------------

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

`:blank`

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

- [`:empty`](:empty)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:blank>
