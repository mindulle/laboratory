:focus
======

The `:focus` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents an element (such as a form
input) that has received focus. It is generally triggered when the user
clicks or taps on an element or selects it with the keyboard\'s
[Tab] key.

Try it
------

**Note:** This pseudo-class applies only to the focused element itself.
Use [`:focus-within`](:focus-within) if you want to select an element
that *contains* a focused element.

Syntax
------

[css]

```css
:focus {
  /* ... */
}
```

Examples
--------

### HTML

[html]

```html
<div><input class="red-input" value="I'll be red when focused." /></div>
<div><input class="blue-input" value="I'll be blue when focused." /></div>
```

### CSS

[css]

```css
.red-input:focus {
  background: yellow;
  color: red;
}

.blue-input:focus {
  background: yellow;
  color: blue;
}
```

### Result

Accessibility concerns
----------------------

Make sure the visual focus indicator can be seen by people with low
vision. This will also benefit anyone use a screen in a brightly lit
space (like outside in the sun). [WCAG 2.1 SC 1.4.11 Non-Text
Contrast](https://www.w3.org/WAI/WCAG21/Understanding/non-text-contrast.html)
requires that the visual focus indicator be at least 3 to 1.

- Accessible Visual Focus Indicators: [Give Your Site Some Focus! Tips
    for Designing Useful and Usable Focus
    Indicators](https://www.deque.com/blog/give-site-focus-tips-designing-usable-focus-indicators/)

### `:focus`

Never just remove the focus outline (visible focus indicator) without
replacing it with a focus outline that will pass [WCAG 2.1 SC 1.4.11
Non-Text
Contrast](https://www.w3.org/WAI/WCAG21/Understanding/non-text-contrast.html).

- Quick Tip: [Never remove CSS
    outlines](https://www.a11yproject.com/posts/never-remove-css-outlines/)

Specifications
--------------

  ------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-focus]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-focus)

[Selectors Level 4\
  [\# focus-pseudo]](https://drafts.csswg.org/selectors/#focus-pseudo)
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

`:focus`

1

12

1

8

7

1

4.4

18

4

10.1

1

1.0

See also
--------

- [`:focus-visible`](:focus-visible)
- [`:focus-within`](:focus-within)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:focus>
