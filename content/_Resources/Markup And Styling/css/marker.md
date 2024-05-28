::marker
========

The `::marker` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-element](pseudo-elements.md) selects the marker box of a list item,
which typically contains a bullet or number. It works on any element or
pseudo-element set to [`display: list-item`](display.md), such as the
[`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li)
and
[`<summary>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary)
elements.

Try it
------

Allowable properties
--------------------

Only certain CSS properties can be used in a rule with `::marker` as a
selector:

- All [font properties](css_fonts.md)
- The [`white-space`](white-space.md) property
- [`color`](_Resources/Markup%20And%20Styling/css/color.md)
- [`text-combine-upright`](text-combine-upright.md),
    [`unicode-bidi`](unicode-bidi.md) and [`direction`](direction.md)
    properties
- The [`content`](content.md) property
- All [animation](css_animations.md#properties) and
    [transition](css_transitions.md#properties) properties

**Note:** The specification states that additional CSS properties may be
supported in future.

Syntax
------

[css]

```css
::marker {
  /* ... */
}
```

Examples
--------

### HTML

[html]

```html
<ul>
  <li>Peaches</li>
  <li>Apples</li>
  <li>Plums</li>
</ul>
```

### CSS

[css]

```css
ul li::marker {
  color: red;
  font-size: 1.5em;
}
```

### Result

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [CSS Pseudo-Elements Module Level 4\
  [\#
  marker-pseudo]](https://drafts.csswg.org/css-pseudo/#marker-pseudo)

  -----------------------------------------------------------------------------

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

`::marker`

86

86

68

No

72

11.1Safari support is limited to `color` and `font-size`. See [bug
204163](https://webkit.org/b/204163).

86

86

68

61

11.3Safari support is limited to `color` and `font-size`. See [bug
204163](https://webkit.org/b/204163).

14.0

`animation_and_transition_support`

86

86

80

No

72

No

86

86

No

61

No

14.0

See also
--------

- HTML elements that have marker boxes by default:
    [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol),
    [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li),
    [`<summary>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/::marker>
