:active
=======

The `:active` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents an element (such as a button)
that is being activated by the user. When using a mouse, \"activation\"
typically starts when the user presses down the primary mouse button.

Try it
------

The `:active` pseudo-class is commonly used on
[`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) and
[`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)
elements. Other common targets of this pseudo-class include elements
that are *contained in* an activated element, and form elements that are
being activated through their associated
[`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label).

Styles defined by the `:active` pseudo-class will be overridden by any
subsequent link-related pseudo-class ([`:link`](:link),
[`:hover`](:hover), or [`:visited`](:visited)) that has at least equal
specificity. To style links appropriately, put the `:active` rule after
all other link-related rules, as defined by the *LVHA-order*: `:link`
--- `:visited` --- `:hover` --- `:active`.

**Note:** On systems with multi-button mice, CSS specifies that the
`:active` pseudo-class must only apply to the primary button; on
right-handed mice, this is typically the leftmost button.

Syntax
------

[css]

```css
:active {
  /* ... */
}
```

Examples
--------

### Active links

#### HTML

[html]

```html
<p>
  This paragraph contains a link:
  <a href="#">This link will turn red while you click on it.</a>
  The paragraph will get a gray background while you click on it or the link.
</p>
```

#### CSS

[css]

```css
/* Unvisited links */
a:link {
  color: blue;
}
/* Visited links */
a:visited {
  color: purple;
}
/* Hovered links */
a:hover {
  background: yellow;
}
/* Active links */
a:active {
  color: red;
}

/* Active paragraphs */
p:active {
  background: #eee;
}
```

#### Result

### Active form elements

#### HTML

[html]

```html
<form>
  <label for="my-button">My button: </label>
  <button id="my-button" type="button">Try Clicking Me or My Label!</button>
</form>
```

#### CSS

[css]

```css
form :active {
  color: red;
}

form button {
  background: white;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-active]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-active)

[Selectors Level 4\
  [\# the-active-pseudo]](https://drafts.csswg.org/selectors/#the-active-pseudo)
  --------------------------------------------------------------------------------------------------------

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

`:active`

1

12

1

4

5

1

4.4

18

4

10.1

1

1.0

`non_a_elements`

1

12

1

8

7

1

4.4

18

4

14

1By default, Safari on iOS does not use the
[`:active`](https://developer.mozilla.org/docs/Web/CSS/:active) state
unless there is a
[`touchstart`](https://developer.mozilla.org/docs/Web/Reference/Events/touchstart)
event handler on the relevant element or on the
[`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body)
element.

1.0

See also
--------

- Link-related pseudo-classes: [`:link`](:link),
    [`:visited`](:visited), and [`:hover`](:hover)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:active>
