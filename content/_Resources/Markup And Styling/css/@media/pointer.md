pointer
=======

The `pointer` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[media feature](@media.md#media_features) tests whether the user has a
pointing device (such as a mouse), and if so, how accurate the *primary*
pointing device is.

**Note:** If you want to test the accuracy of *any* pointing device, use
[`any-pointer`](any-pointer.md) instead.

Syntax
------

The `pointer` feature is specified as a keyword value chosen from the
list below.

[`none`](#none)

:   The primary input mechanism does not include a pointing device.

[`coarse`](#coarse)

:   The primary input mechanism includes a pointing device of limited
    accuracy, such as a finger on a touchscreen.

[`fine`](#fine)

:   The primary input mechanism includes an accurate pointing device,
    such as a mouse.

Examples
--------

This example creates a small checkbox for users with fine primary
pointers and a large checkbox for users with coarse primary pointers.

### HTML

[html]

```html
<input id="test" type="checkbox" /> <label for="test">Look at me!</label>
```

### CSS

[css]

```css
input[type="checkbox"] {
  appearance: none;
  border: solid;
  margin: 0;
}

input[type="checkbox"]:checked {
  background: gray;
}

@media (pointer: fine) {
  input[type="checkbox"] {
    width: 15px;
    height: 15px;
    border-width: 1px;
    border-color: blue;
  }
}

@media (pointer: coarse) {
  input[type="checkbox"] {
    width: 30px;
    height: 30px;
    border-width: 2px;
    border-color: red;
  }
}
```

### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Media Queries Level 4\
  [\# pointer]](https://drafts.csswg.org/mediaqueries/#pointer)

  -----------------------------------------------------------------------

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

`pointer`

41

12

64

No

28

9

41

50

64

28

9

5.0

See also
--------

- [The `any-pointer` media feature](any-pointer.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/pointer>
