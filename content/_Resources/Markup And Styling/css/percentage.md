\<percentage\>
==============

The `<percentage>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](css_types.md) represents a percentage value. It is often used to
define a size as relative to an element\'s parent object. Numerous
properties can use percentages, such as [`width`](_Resources/Markup%20And%20Styling/css/width.md),
[`height`](_Resources/Markup%20And%20Styling/css/height.md), [`margin`](margin.md), [`padding`](padding.md), and
[`font-size`](font-size.md).

**Note:** Only calculated values can be inherited. Thus, even if a
percentage value is used on the parent property, a real value (such as a
width in pixels for a [`<length>`](length.md) value) will be accessible on
the inherited property, not the percentage value.

Syntax
------

The `<percentage>` data type consists of a [`<number>`](number.md) followed
by the percentage sign (`%`). Optionally, it may be preceded by a single
`+` or `-` sign, although negative values are not valid for all
properties. As with all CSS dimensions, there is no space between the
symbol and the number.

Interpolation
-------------

When animated, values of the `<percentage>` data type are
[interpolated](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation)
as real, floating-point numbers. The speed of the interpolation is
determined by the [easing function](easing-function.md) associated with the
animation.

Examples
--------

### Width and margin-left

[html]

```html
<div style="background-color:navy;">
  <div style="width:50%; margin-left:20%; background-color:chartreuse;">
    Width: 50%, Left margin: 20%
  </div>
  <div style="width:30%; margin-left:60%; background-color:pink;">
    Width: 30%, Left margin: 60%
  </div>
</div>
```

The above HTML will output:

### Font-size

[html]

```html
<div style="font-size:18px;">
  <p>Full-size text (18px)</p>
  <p><span style="font-size:50%;">50% (9px)</span></p>
  <p><span style="font-size:200%;">200% (36px)</span></p>
</div>
```

The above HTML will output:

Specifications
--------------

  -------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\#
  percentages]](https://drafts.csswg.org/css-values/#percentages)

  -------------------------------------------------------------------------

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

`percentage`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

See also
--------

- [`<length-percentage>`](length-percentage.md)
- [CSS Values and Units](css_values_and_units.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/percentage>
