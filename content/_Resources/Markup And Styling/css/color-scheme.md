color-scheme
============

The `color-scheme` CSS property allows an element to indicate which
color schemes it can comfortably be rendered in.

Common choices for operating system color schemes are \"light\" and
\"dark\", or \"day mode\" and \"night mode\". When a user selects one of
these color schemes, the operating system makes adjustments to the user
interface. This includes form controls, scrollbars, and the used values
of CSS system colors.

Try it
------

Syntax
------

[css]

```css
color-scheme: normal;
color-scheme: light;
color-scheme: dark;
color-scheme: light dark;
color-scheme: only light;

/* Global values */
color-scheme: inherit;
color-scheme: initial;
color-scheme: revert;
color-scheme: revert-layer;
color-scheme: unset;
```

The `color-scheme` property\'s value must be one of the following
keywords.

### Values

[`normal`](#normal)

:   Indicates that the element isn\'t aware of any color schemes, and so
    should be rendered using the browser\'s default color scheme.

[`light`](#light)

:   Indicates that the element can be rendered using the operating
    system light color scheme.

[`dark`](#dark)

:   Indicates that the element can be rendered using the operating
    system dark color scheme.

[`only`](#only)

:   Forbids the user agent from overriding the color scheme for the
    element.

    Can be used to turn off color overrides caused by Chrome\'s [Auto
    Dark
    Theme](https://developer.chrome.com/blog/auto-dark-theme/#per-element-opt-out),
    by applying `color-scheme: only light;` on a specific element or
    `:root`.

Formal definition
-----------------

  ---------------------------------- -----------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements and text
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -----------------------

Formal syntax
-------------

```
color-scheme = 
  normal                                       |
  [ light | dark | <custom-ident> ]+ && only?  
```

Examples
--------

### Adapting to color schemes

To opt the entire page into the user\'s color scheme preferences declare
`color-scheme` on the [`:root`](:root) element.

[css]

```css
:root {
  color-scheme: light dark;
}
```

Specifications
--------------

  -------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------

  [CSS Color Adjustment Module Level 1\
  [\#
  color-scheme-prop]](https://drafts.csswg.org/css-color-adjust/#color-scheme-prop)

  -------------------------------------------------------------------------------------------

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

`color-scheme`

81

81

96

No

68

13

81

81

96

58

13

13.0

`only_dark`

81

81

96

No

68

13

81

81

96

58

13

13.0

`only_light`

81--85

81--85

96

No

68--71

13

81--85

81--85

96

58--60

13

13.0--14.0

See also
--------

- [`prefers-color-scheme`](prefers-color-scheme.md) media query to
    detect user preferences for color schemes.
- [](applying_color.md)
- Other color-related properties: [`color`](_Resources/Markup%20And%20Styling/css/color.md),
    [`background-color`](background-color.md),
    [`border-color`](border-color.md), [`outline-color`](outline-color.md),
    [`text-decoration-color`](text-decoration-color.md),
    [`text-emphasis-color`](text-emphasis-color.md),
    [`text-shadow`](text-shadow.md), [`caret-color`](caret-color.md), and
    [`column-rule-color`](column-rule-color.md)
- [`background-image`](background-image.md)
- [`print-color-adjust`](print-color-adjust.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/color-scheme>
