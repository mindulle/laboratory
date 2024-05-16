\<display-outside\>
===================

The `<display-outside>` keywords specify the element\'s outer
[`display`](display.md) type, which is essentially its role in flow layout.
These keywords are used as values of the `display` property, and can be
used for legacy purposes as a single keyword, or as defined in the Level
3 specification alongside a value from the
[`<display-inside>`](display-inside.md) keywords.

Syntax
------

Valid `<display-outside>` values:

[`block`](#block)

:   The element generates a block element box, generating line breaks
    both before and after the element when in the normal flow.

[`inline`](#inline)

:   The element generates one or more inline element boxes that do not
    generate line breaks before or after themselves. In normal flow, the
    next element will be on the same line if there is space.

**Note:** Browsers that support the two value syntax, on finding the
outer value only, such as when `display: block` or `display: inline` is
specified, will set the inner value to `flow`. This will result in
expected behavior; for example if you specify an element to be block,
you would expect that the children of that element would participate in
block and inline normal flow layout.

Formal syntax
-------------

```
<display-outside> = 
  block   |
  inline  |
  run-in  
```

Examples
--------

In the following example, span elements (normally displayed as inline
elements) are set to `display: block` and so break onto new lines and
expand to fill their container in the inline dimension.

### HTML

[html]

```html
<span>span 1</span> <span>span 2</span>
```

### CSS

[css]

```css
span {
  display: block;
  border: 1px solid rebeccapurple;
}
```

### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------

  [CSS Display Module Level 3\
  [\#
  typedef-display-outside]](https://drafts.csswg.org/css-display/#typedef-display-outside)

  --------------------------------------------------------------------------------------------------

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

`display-outside`

1

12

1

4

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

- [`display`](display.md)
  - [`<display-inside>`](display-inside.md)
  - [`<display-listitem>`](display-listitem.md)
  - [`<display-internal>`](display-internal.md)
  - [`<display-box>`](display-box.md)
  - [`<display-legacy>`](display-legacy.md)
- [](block_and_inline_layout_in_normal_flow.md)
- [](introduction_to_formatting_contexts.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/display-outside>
