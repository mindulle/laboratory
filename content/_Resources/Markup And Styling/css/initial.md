initial
=======

The `initial` CSS keyword applies the [](initial_value.md) of a property to an element. It can be applied to
any CSS property, including the CSS shorthand property [`all`](all.md).
With `all` set to `initial`, all CSS properties can be restored to their
respective initial values in one go instead of restoring each one
separately.

On [inherited properties](inheritance.md#inherited_properties), the initial
value may be unexpected. You should consider using the
[`inherit`](inherit.md), [`unset`](unset.md), [`revert`](revert.md), or
[`revert-layer`](revert-layer.md) keywords instead.

Examples
--------

### Using initial to reset color for an element

#### HTML

[html]

```html
<p>
  <span>This text is red.</span>
  <em>This text is in the initial color (typically black).</em>
  <span>This is red again.</span>
</p>
```

#### CSS

[css]

```css
p {
  color: red;
}

em {
  color: initial;
}
```

#### Result

With the `initial` keyword in this example, `color` value on the `em`
element is restored to the initial value of
[`color`](_Resources/Markup%20And%20Styling/css/color.md#formal_definition), as defined in the specification.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Cascading and Inheritance Level 4\
  [\# initial]](https://drafts.csswg.org/css-cascade/#initial)

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

`initial`

1

13

191--24

No

15

1.2

4.4

18

194--24

14

1

1.0

See also
--------

- Use the [`inherit`](inherit.md) keyword to make an element\'s property
    the same as its parent.
- Use the [`revert`](revert.md) keyword to reset a property to the value
    established by the user-agent stylesheet (or by user styles, if any
    exist).
- Use the [`revert-layer`](revert-layer.md) keyword to reset a property
    to the value established in a previous cascade layer.
- Use the [`unset`](unset.md) keyword to set a property to its inherited
    value if it inherits or to its initial value if not.
- The [`all`](all.md) property lets you reset all properties to their
    initial, inherited, reverted, or unset state at once.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/initial>
