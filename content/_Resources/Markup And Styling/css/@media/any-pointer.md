any-pointer
===========

The `any-pointer`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](@media.md#media_features) tests whether the user has *any*
pointing device (such as a mouse), and if so, how accurate it is.

**Note:** If you want to test the accuracy of the *primary* pointing
device, use [`pointer`](pointer.md) instead.

Syntax
------

The `any-pointer` feature is specified as a keyword value chosen from
the list below.

[`none`](#none)

:   No pointing device is available.

[`coarse`](#coarse)

:   At least one input mechanism includes a pointing device of limited
    accuracy.

[`fine`](#fine)

:   At least one input mechanism includes an accurate pointing device.

**Note:** More than one value can match if the available devices have
different characteristics, although `none` only matches when none of
them are pointing devices.

Examples
--------

This example creates a small checkbox for users with at least one fine
pointer and a large checkbox for users with at least one coarse pointer.
The big checkbox takes precedence because it is declared after the small
one.

### HTML

[html]

```html
<input id="test" type="checkbox" /> <label for="test">Look at me!</label>
```

### CSS

```css
[css]

```css

input[type="checkbox"]:checked {
  background: gray;
}

@media (any-pointer: fine) {
  input[type="checkbox"] {
    appearance: none;
    width: 15px;
    height: 15px;
    border: 1px solid blue;
  }
}

@media (any-pointer: coarse) {
  input[type="checkbox"] {
    appearance: none;
    width: 30px;
    height: 30px;
    border: 2px solid red;
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
  [\#
  any-input]](https://drafts.csswg.org/mediaqueries/#any-input)

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

`any-pointer`

41

12

64

No

28

9

41

41

64

28

9

4.0

See also
--------

- [The `pointer` media feature](pointer.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/any-pointer>
