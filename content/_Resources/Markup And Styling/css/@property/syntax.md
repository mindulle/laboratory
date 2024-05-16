syntax
======

The `syntax` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
descriptor is required when using the [`@property`](@property.md)
[at-rule](at-rule.md) and describes the allowable syntax for the
property.

Syntax
------

The following are all valid syntax strings:

[css]

```css
syntax: "<color>"; /* accepts a color */

syntax: "<length> | <percentage>"; /* accepts lengths or percentages but not calc expressions with a combination of the two */

syntax: "small | medium | large"; /* accepts one of these values set as custom idents. */

syntax: "*"; /* any valid token */
```

Values
------

A string with a supported syntax as defined by the specification.
Supported syntaxes are a subset of [CSS types](css_types.md). These may
be used along, or a number of types can be used in combination.

[`"<length>"`](#length)

:   Any valid [`<length>`](length.md) values.

[`"<number>"`](#number)

:   Any valid [`<number>`](number.md) values.

[`"<percentage>"`](#percentage)

:   Any valid [`<percentage>`](percentage.md) values.

[`"<length-percentage>"`](#length-percentage)

:   Any valid [`<length-percentage>`](length-percentage.md) values.

[`"<color>"`](#color)

:   Any valid [`<color>`](color_value.md) values.

[`"<image>"`](#image)

:   Any valid [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) values.

[`"<url>"`](#url)

:   Any valid [`url()`](url.md) values.

[`"<integer>"`](#integer)

:   Any valid [`<integer>`](integer.md) values.

[`"<angle>"`](#angle)

:   Any valid [`<angle>`](angle.md) values.

[`"<time>"`](#time)

:   Any valid [`<time>`](time.md) values.

[`"<resolution>"`](#resolution)

:   Any valid [`<resolution>`](_Resources/Markup%20And%20Styling/css/resolution.md) values.

[`"<transform-function>"`](#transform-function)

:   Any valid [`<transform-function>`](transform-function.md) values.

[`"<custom-ident>"`](#custom-ident)

:   Any valid [`<custom-ident>`](custom-ident.md) values.

[`"<transform-list>"`](#transform-list)

:   A list of valid [`<transform-function>`](transform-function.md)
    values.

Formal definition
-----------------

  ------------------------------------- -----------------------------
  Related [at-rule](at-rule.md)         [`@property`](@property.md)
  [Initial value](initial_value.md)     `n/a (required)`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- -----------------------------

Formal syntax
-------------

```
syntax = 
  <string>  
```

Examples
--------

Add type checking to `--my-color` [`custom property`](../--*), using the
`<color>` syntax:

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

  ------------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------------

  [CSS Properties and Values API Level 1\
  [\#
  the-syntax-descriptor]](https://drafts.css-houdini.org/css-properties-values-api/#the-syntax-descriptor)

  ------------------------------------------------------------------------------------------------------------------

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

`syntax`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/@property/syntax>
