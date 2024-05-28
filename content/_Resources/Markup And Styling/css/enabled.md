:enabled
========

The `:enabled` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents any enabled element. An
element is enabled if it can be activated (selected, clicked on, typed
into, etc.) or accept focus. The element also has a disabled state, in
which it can\'t be activated or accept focus.

Try it
------

Syntax
------

```
:enabled
```

Examples
--------

The following example makes the color of text and button
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)s
green when enabled, and gray when disabled. This helps the user
understand which elements can be interacted with.

### HTML

[html]

```html
<form action="url_of_form">
  <label for="FirstField">First field (enabled):</label>
  <input type="text" id="FirstField" value="Lorem" /><br />

  <label for="SecondField">Second field (disabled):</label>
  <input type="text" id="SecondField" value="Ipsum" disabled="disabled" /><br />

  <input type="button" value="Submit" />
</form>
```

### CSS

[css]

```css
input:enabled {
  color: #2b2;
}

input:disabled {
  color: #aaa;
}
```

### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-enabled]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-enabled)

[Selectors Level 4\
  [\# enableddisabled]](https://drafts.csswg.org/selectors/#enableddisabled)
  ----------------------------------------------------------------------------------------------------------

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

`:enabled`

1

12

1

9

9

3.1

2

18

4

10.1

2

1.0

See also
--------

- [`:disabled`](:disabled)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:enabled>
