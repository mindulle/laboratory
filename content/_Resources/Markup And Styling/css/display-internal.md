\<display-internal\>
====================

Some layout models such as `table` and `ruby` have a complex internal
structure, with several different roles that their children and
descendants can fill. This page defines those \"internal\" display
values, which only have meaning within that particular layout mode.

Syntax
------

Valid `<display-internal>` values:

[`table-row-group`](#table-row-group)

:   These elements behave like
    [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody)
    HTML elements.

[`table-header-group`](#table-header-group)

:   These elements behave like
    [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead)
    HTML elements.

[`table-footer-group`](#table-footer-group)

:   These elements behave like
    [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot)
    HTML elements.

[`table-row`](#table-row)

:   These elements behave like
    [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr)
    HTML elements.

[`table-cell`](#table-cell)

:   These elements behave like
    [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td)
    HTML elements.

[`table-column-group`](#table-column-group)

:   These elements behave like
    [`<colgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/colgroup)
    HTML elements.

[`table-column`](#table-column)

:   These elements behave like
    [`<col>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col)
    HTML elements.

[`table-caption`](#table-caption)

:   These elements behave like
    [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption)
    HTML elements.

[`ruby-base`](#ruby-base) [Experimental]

:   These elements behave like
    [`<rb>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rb)
    HTML elements.

[`ruby-text`](#ruby-text) [Experimental]

:   These elements behave like
    [`<rt>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rt)
    HTML elements.

[`ruby-base-container`](#ruby-base-container) [Experimental]

:   These elements are generated as anonymous boxes.

[`ruby-text-container`](#ruby-text-container) [Experimental]

:   These elements behave like
    [`<rtc>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rtc)
    HTML elements.

Formal syntax
-------------

```
<display-internal> = 
  table-row-group      |
  table-header-group   |
  table-footer-group   |
  table-row            |
  table-cell           |
  table-column-group   |
  table-column         |
  table-caption        |
  ruby-base            |
  ruby-text            |
  ruby-base-container  |
  ruby-text-container  
```

Examples
--------

### CSS tables example

The following example demonstrates laying out a simple form using CSS
table layout.

#### HTML

[html]

```html
<main>
  <div>
    <label for="name">Name</label>
    <input type="text" id="name" name="name" />
  </div>
  <div>
    <label for="age">Age</label>
    <input type="text" id="age" name="age" />
  </div>
</main>
```

#### CSS

[css]

```css
main {
  display: table;
}

div {
  display: table-row;
}

label,
input {
  display: table-cell;
  margin: 5px;
}
```

#### Result

Specifications
--------------

**No specification found**

No specification data found for
`css.properties.display.table_values,css.properties.display.ruby_values`.\
[Check for problems with this page](#on-github) or contribute a missing
`spec_url` to
[mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).
Also make sure the specification is included in
[w3c/browser-specs](https://github.com/w3c/browser-specs).

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

`display-internal`

No

12--79

38

7

No

No

No

No

38

No

No

No

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

`display-internal`

1

12

1

8

7

1

≤37

18

4

14

1

1.0

### css.properties.display.table\_values

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.properties.display.ruby\_values

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

See also
--------

- [`display`](display.md)
  - [`<display-outside>`](display-outside.md)
  - [`<display-inside>`](display-inside.md)
  - [`<display-listitem>`](display-listitem.md)
  - [`<display-box>`](display-box.md)
  - [`<display-legacy>`](display-legacy.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal>
