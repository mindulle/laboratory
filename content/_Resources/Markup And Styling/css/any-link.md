:any-link
=========

The `:any-link` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) selector represents an element that acts
as the source anchor of a hyperlink, independent of whether it has been
visited. In other words, it matches every
[`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) or
[`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area)
element that has an `href` attribute. Thus, it matches all elements that
match [`:link`](:link) or [`:visited`](:visited).

Try it
------

Syntax
------

[css]

```css
:any-link {
  /* ... */
}
```

Examples
--------

### HTML

[html]

```html
<a href="https://example.com">External link</a><br />
<a href="#">Internal target link</a><br />
<a>Placeholder link (won't get styled)</a>
```

### CSS

[css]

```css
a:any-link {
  border: 1px solid blue;
  color: orange;
}

/* WebKit browsers */
a:-webkit-any-link {
  border: 1px solid blue;
  color: orange;
}
```

### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  the-any-link-pseudo]](https://drafts.csswg.org/selectors/#the-any-link-pseudo)

  ----------------------------------------------------------------------------------------

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

`:any-link`

651

7979

501--50

No

5215

931.2--3

65≤37

6518

504--50

4714

91

9.01.0

`not_match_link`

65

79

87

No

52

NoSafari currently matches `<link>` elements with link pseudo-classes.
See [Bug: 220740](https://webkit.org/b/220740).

65

65

87

47

NoSafari currently matches `<link>` elements with link pseudo-classes.
See [Bug: 220740](https://webkit.org/b/220740).

9.0

See also
--------

- [Creating
    hyperlinks](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks)
- Matches HTML elements:
    [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)
    and
    [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area)
    with an
    [`href`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#href)
    attribute
- Related CSS selectors:
  - [`:visited`](:visited)
  - [`:link`](:link)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:any-link>
