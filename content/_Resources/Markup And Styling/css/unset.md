unset
=====

The `unset` CSS keyword resets a property to its inherited value if the
property naturally inherits from its parent, and to its [](initial_value.md) if not. In other words, it behaves like the
[`inherit`](inherit.md) keyword in the first case, when the property is an
[inherited property](inheritance.md#inherited_properties), and like the
[`initial`](initial.md) keyword in the second case, when the property is a
[non-inherited property](inheritance.md#non-inherited_properties).

`unset` can be applied to any CSS property, including the CSS shorthand
property [`all`](all.md).

Examples
--------

### Color

[`color`](_Resources/Markup%20And%20Styling/css/color.md#formal_definition) is an inherited property.

#### HTML

[html]

```html
<p>This text is red.</p>
<div class="foo">
  <p>This text is also red.</p>
</div>
<div class="bar">
  <p>This text is green (default inherited value).</p>
</div>
```

#### CSS

[css]

```css
.foo {
  color: blue;
}

.bar {
  color: green;
}

p {
  color: red;
}

.bar p {
  color: unset;
}
```

#### Result

### Border

[`border`](border.md#formal_definition) is a non-inherited property.

#### HTML

[html]

```html
<p>This text has a red border.</p>
<div>
  <p>This text has a red border.</p>
</div>
<div class="bar">
  <p>This text has a black border (initial default, not inherited).</p>
</div>
```

#### CSS

[css]

```css
div {
  border: 1px solid green;
}

p {
  border: 1px solid red;
}

.bar p {
  border-color: unset;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------

  [CSS Cascading and Inheritance Level 4\
  [\#
  inherit-initial]](https://drafts.csswg.org/css-cascade/#inherit-initial)

  ----------------------------------------------------------------------------------

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

`unset`

41

13

27

No

28

9.1

41

41

27

28

9.3

4.0

See also
--------

- Use the [`initial`](initial.md) keyword to set a property to its
    initial value.
- Use the [`inherit`](inherit.md) keyword to make an element\'s property
    the same as its parent.
- Use the [`revert`](revert.md) keyword to reset a property to the value
    established by the user-agent stylesheet (or by user styles, if any
    exist).
- Use the [`revert-layer`](revert-layer.md) keyword to reset a property
    to the value established in a previous cascade layer.
- The [`all`](all.md) property lets you reset all properties to their
    initial, inherited, reverted, or unset state at once.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/unset>
