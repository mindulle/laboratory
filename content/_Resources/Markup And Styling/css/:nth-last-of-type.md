:nth-last-of-type()
===================

The `:nth-last-of-type()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) matches elements based on their position
among siblings of the same type (tag name), counting from the end.

Try it
------

Syntax
------

The `nth-last-of-type` pseudo-class is specified with a single argument,
which represents the pattern for matching elements, counting from the
end.

See [`:nth-last-child`](:nth-last-child) for a more detailed explanation
of its syntax.

[css]

```css
:nth-last-of-type(<an-plus-b> | even | odd) {
  /* ... */
}
```

Examples
--------

### HTML

[html]

```html
<div>
  <span>This is a span.</span>
  <span>This is another span.</span>
  <em>This is emphasized.</em>
  <span>Wow, this span gets limed!!!</span>
  <del>This is struck through.</del>
  <span>Here is one last span.</span>
</div>
```

### CSS

[css]

```css
span:nth-last-of-type(2) {
  background-color: lime;
}
```

### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  nth-last-of-type-pseudo]](https://drafts.csswg.org/selectors/#nth-last-of-type-pseudo)

  ------------------------------------------------------------------------------------------------

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

`:nth-last-of-type`

4

12Before Edge 16, Microsoft Edge treats all unknown elements (such as
custom elements) as the same element type.

3.5

9Internet Explorer treats all unknown elements (such as custom elements)
as the same element type.

9.5

3.1

2

18

4

10.1

2

1.0

See also
--------

- [`:nth-last-child`](:nth-last-child), [`:nth-of-type`](:nth-of-type)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-last-of-type>
