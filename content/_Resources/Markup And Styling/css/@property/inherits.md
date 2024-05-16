inherits
========

The `inherits` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
descriptor is required when using the [`@property`](@property.md)
[at-rule](at-rule.md) and controls whether the custom property
registration specified by `@property` inherits by default.

Syntax
------

[css]

```css
@property --property-name {
  syntax: "<color>";
  inherits: false;
  initial-value: #c0ffee;
}

@property --property-name {
  syntax: "<color>";
  inherits: true;
  initial-value: #c0ffee;
}
```

Values
------

[`true`](#true)

:   The property inherits by default.

[`false`](#false)

:   The property does not inherit by default.

Formal definition
-----------------

  ------------------------------------- -----------------------------
  Related [at-rule](at-rule.md)         [`@property`](@property.md)
  [Initial value](initial_value.md)     `auto`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- -----------------------------

Formal syntax
-------------

```
inherits = 
  true   |
  false  
```

Examples
--------

Add type checking to `--my-color` [`custom property`](../--*), as a
color, a default value, and not allow it to inherit its value:

Using [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[`@property`](@property.md) [at-rule](at-rule.md):

[css]

```css
@property --my-color {
  syntax: "<color>";
  inherits: false;
  initial-value: #c0ffee;
}
```

Using
[JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[`CSS.registerProperty()`](https://developer.mozilla.org/en-US/docs/Web/API/CSS/registerProperty_static):

[js]

```js
window.CSS.registerProperty({
  name: "--my-color",
  syntax: "<color>",
  inherits: false,
  initialValue: "#c0ffee",
});
```

Specifications
--------------

  --------------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------------

  [CSS Properties and Values API Level 1\
  [\#
  inherits-descriptor]](https://drafts.css-houdini.org/css-properties-values-api/#inherits-descriptor)

  --------------------------------------------------------------------------------------------------------------

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

`inherits`

85

85

preview

No

71

16.4

85

85

No

60

16.4

14.0

See also
--------

- [CSS Properties and Values
    API](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Properties_and_Values_API)
- [CSS Painting
    API](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Painting_API)
- [CSS Typed Object
    Model](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Typed_OM_API)
- [CSS
    Houdini](https://developer.mozilla.org/en-US/docs/Web/Guide/Houdini)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@property/inherits>
