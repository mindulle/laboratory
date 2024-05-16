:first
======

The `:first` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md), used with the [`@page`](@page.md)
[at-rule](at-rule.md), represents the first page of a printed document.
(See [`:first-child`](:first-child) for general first element of a
node.)

[css]

```css
/* Selects the first page when printing */
@page :first {
  margin-left: 50%;
  margin-top: 50%;
}
```

**Note:** You can\'t change all CSS properties with this pseudo-class.
You can only change the margins, [`orphans`](orphans.md),
[`widows`](widows.md), and page breaks of the document. Furthermore, you
may only use [absolute-length](length.md#absolute_length_units) units when
defining the margins. All other properties will be ignored.

Syntax
------

[css]

```css
:first {
  /* ... */
}
```

Examples
--------

### HTML

[html]

```html
<p>First Page.</p>
<p>Second Page.</p>
<button>Print!</button>
```

### CSS

[css]

```css
@page :first {
  margin-left: 50%;
  margin-top: 50%;
}

p {
  page-break-after: always;
}
```

### JavaScript

[js]

```js
document.querySelector("button").addEventListener("click", () => {
  window.print();
});
```

### Result

Press the \"Print!\" button to print the example. The words on the first
page should be somewhere around the center, while other pages will have
their contents at the default position.

Specifications
--------------

  ---------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------

  [CSS Paged Media Module Level 3\
  [\#
  left-right-first]](https://drafts.csswg.org/css-page/#left-right-first)

  ---------------------------------------------------------------------------------

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

`:first`

18

12

116

8

9.2

6

4.4

18

116

10.1

6

1.0

See also
--------

- [`@page`](@page.md)
- Other page-related pseudo-classes: [`:left`](:left),
    [`:right`](:right)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:first>
