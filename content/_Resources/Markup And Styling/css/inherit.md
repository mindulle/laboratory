inherit
=======

The `inherit` CSS keyword causes the element to take the [](computed_value.md) of the property from its parent element. It can
be applied to any CSS property, including the CSS shorthand property
[`all`](all.md).

For [inherited properties](inheritance.md#inherited_properties), this
reinforces the default behavior, and is only needed to override another
rule.

**Note:** Inheritance is always from the parent element in the document
tree, even when the parent element is not the containing block.

Examples
--------

### Exclude selected elements from a rule

[css]

```css
/* Make second-level headers green */
h2 {
  color: green;
}

/* Leave those in the sidebar alone so they use their parent's color */
#sidebar h2 {
  color: inherit;
}
```

In this example, the `h2` elements inside the sidebar might be different
colors. For example, consider one of them that would by the child of a
`div` matched by the rule:

[css]

```css
div#current {
  color: blue;
}
```

Then, it would be blue.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Cascading and Inheritance Level 4\
  [\# inherit]](https://drafts.csswg.org/css-cascade/#inherit)

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

`inherit`

1

12

1

8

4

1

4.4

18

4

14

1

1.0

See also
--------

- [Inheritance](inheritance.md)
- Use the [`initial`](initial.md) keyword to set a property to its
    initial value.
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
https://developer.mozilla.org/en-US/docs/Web/CSS/inherit>
