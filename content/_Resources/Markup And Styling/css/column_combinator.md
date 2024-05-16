Column combinator
=================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The **column combinator** (`||`) is placed between two CSS selectors. It
matches only those elements matched by the second selector that belong
to the column elements matched by the first.

[css]

```css
/* Table cells that belong to the "selected" column */
col.selected||td {
  background: gray;
}
```

Syntax
------

[css]

```css
/* The white space around the || combinator is optional but recommended. */
column-selector || cell-selector {
  /* style properties */
}
```

Examples
--------

### HTML

[html]

```html
<table border="1">
  <colgroup>
    <col span="2" />
    <col class="selected" />
  </colgroup>
  <tbody>
    <tr>
      <td>A</td>
      <td>B</td>
      <td>C</td>
    </tr>

    <tr>
      <td colspan="2">D</td>
      <td>E</td>
    </tr>
    <tr>
      <td>F</td>
      <td colspan="2">G</td>
    </tr>
  </tbody>
</table>
```

### CSS

[css]

```css
col.selected||td {
  background: gray;
  color: white;
  font-weight: bold;
}
```

### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  the-column-combinator]](https://drafts.csswg.org/selectors/#the-column-combinator)

  --------------------------------------------------------------------------------------------

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

`Column_combinator`

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

- [`<col>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col)
- [`<colgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/colgroup)
- [`grid`](_Resources/Markup%20And%20Styling/css/grid.md)
- [`:nth-col`](:nth-of-type)
- [`:nth-last-col`](:nth-last-of-type)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Column_combinator>
