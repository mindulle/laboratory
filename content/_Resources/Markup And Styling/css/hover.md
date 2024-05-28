:hover
======

The `:hover` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) matches when the user interacts with an
element with a pointing device, but does not necessarily activate it. It
is generally triggered when the user hovers over an element with the
cursor (mouse pointer).

Try it
------

Styles defined by the `:hover` pseudo-class will be overridden by any
subsequent link-related pseudo-class ([`:link`](:link),
[`:visited`](:visited), or [`:active`](:active)) that has at least equal
specificity. To style links appropriately, put the `:hover` rule after
the `:link` and `:visited` rules but before the `:active` one, as
defined by the *LVHA-order*: `:link` --- `:visited` --- `:hover` ---
`:active`.

**Note:** The `:hover` pseudo-class is problematic on touchscreens.
Depending on the browser, the `:hover` pseudo-class might never match,
match only for a moment after touching an element, or continue to match
even after the user has stopped touching and until the user touches
another element. Web developers should make sure that content is
accessible on devices with limited or non-existent hovering
capabilities.

Syntax
------

[css]

```css
:hover {
  /* ... */
}
```

Examples
--------

### Basic example

#### HTML

[html]

```html
<a href="#">Try hovering over this link.</a>
```

#### CSS

[css]

```css
a {
  background-color: powderblue;
  transition: background-color 0.5s;
}

a:hover {
  background-color: gold;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-hover]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-hover)

[Selectors Level 4\
  [\# the-hover-pseudo]](https://drafts.csswg.org/selectors/#the-hover-pseudo)
  ------------------------------------------------------------------------------------------------------

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

`:hover`

1

12

1

4

4

2

4.4

18

4

10.1

1As of Safari for iOS 7.1.2, tapping a [clickable
element](https://developer.mozilla.org/docs/Web/Events/click#Safari_Mobile)
causes the element to enter the `:hover` state. The element will remain
in the `:hover` state until a different element has entered the `:hover`
state.

1.0

`a_elements`

1

12

1

4

4

2

37

18

4

10.1

1

1.0

`all_elements`

1

12In Edge, hovering over an element and then scrolling up or down
without moving the pointer will leave the element in the `:hover` state
until the pointer is moved. See [bug
5381673](https://developer.microsoft.com/microsoft-edge/platform/issues/5381673/).

1

7\[\"In Internet Explorer 8 to Internet Explorer 11, hovering over an
element and then scrolling up or down without moving the pointer will
leave the element in the `:hover` state until the pointer is moved. See
[bug
926665](https://connect.microsoft.com/IE/feedbackdetail/view/926665).\",
\"In Internet Explorer 9 (and possibly earlier), if a
[`<table>`](https://developer.mozilla.org/docs/Web/HTML/Element/table)
has a parent with a non-`auto`
[`width`](https://developer.mozilla.org/docs/Web/CSS/width),
[`overflow-x`](https://developer.mozilla.org/docs/Web/CSS/overflow-x)`: auto;`,
the
[`<table>`](https://developer.mozilla.org/docs/Web/HTML/Element/table)
has enough content to horizontally overflow its parent, and there are
[`:hover`](https://developer.mozilla.org/docs/Web/CSS/:hover) styles set
on elements within the table, then hovering over said elements will
cause the
[`<table>`](https://developer.mozilla.org/docs/Web/HTML/Element/table)\'s
height to increase. See [a live demo that triggers the
bug](https://output.jsbin.com/diwiqe). One workaround for the bug is to
set `min-height: 0%;` (the `%` unit must be specified, since unitless
and `px` don\'t work) on the `<table>`\'s parent element.\"\]

7

2

37

18

4

10.1

1

1.0

See also
--------

- [Chromium bug \#370155: Don\'t make `:hover` sticky on tap on sites
    that set a mobile viewport](https://crbug.com/370155)
- [Chromium bug \#306581: Immediately show hover and active states on
    touch when page isn\'t scrollable.](https://crbug.com/306581)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:hover>
