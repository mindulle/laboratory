:only-of-type
=============

The `:only-of-type` CSS [pseudo-class](pseudo-classes.md) represents an
element that has no siblings of the same type.

Try it
------

**Note:** As originally defined, the selected element had to have a
parent. Beginning with Selectors Level 4, this is no longer required.

Syntax
------

[css]

```css
:only-of-type {
  /* ... */
}
```

Examples
--------

### Styling elements with no siblings of the same type

#### HTML

[html]

```html
<main>
  <div>I am `div` #1.</div>
  <p>I am the only `p` among my siblings.</p>
  <div>I am `div` #2.</div>
  <div>
    I am `div` #3.
    <i>I am the only `i` child.</i>
    <em>I am `em` #1.</em>
    <em>I am `em` #2.</em>
  </div>
</main>
```

#### CSS

[css]

```css
main :only-of-type {
  color: red;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  only-of-type-pseudo]](https://drafts.csswg.org/selectors/#only-of-type-pseudo)

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

`:only-of-type`

1

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

- [`:only-child`](:only-child)
- [`:first-of-type`](:first-of-type)
- [`:last-of-type`](:last-of-type)
- [`:nth-of-type`](:nth-of-type)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:only-of-type>
