\<filter-function\>
===================

The `<filter-function>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](css_types.md) represents a graphical effect that can change the
appearance of an input image. It is used in the [`filter`](filter.md) and
[`backdrop-filter`](backdrop-filter.md) properties.

Syntax
------

The `<filter-function>` data type is specified using one of the filter
functions listed below. Each function requires an argument which, if
invalid, results in no filter being applied.

[`blur()`](blur.md)

:   Blurs the image.

[`brightness()`](brightness.md)

:   Makes the image brighter or darker.

[`contrast()`](contrast.md)

:   Increases or decreases the image\'s contrast.

[`drop-shadow()`](drop-shadow.md)

:   Applies a drop shadow behind the image.

[`grayscale()`](grayscale.md)

:   Converts the image to grayscale.

[`hue-rotate()`](hue-rotate.md)

:   Changes the overall hue of the image.

[`invert()`](invert.md)

:   Inverts the colors of the image.

[`opacity()`](_Resources/Markup%20And%20Styling/css/filter-function/opacity.md)

:   Makes the image transparent.

[`saturate()`](saturate.md)

:   Super-saturates or desaturates the input image.

[`sepia()`](sepia.md)

:   Converts the image to sepia.

Formal syntax
-------------

```
<filter-function> = 
  <blur()>         |
  <brightness()>   |
  <contrast()>     |
  <drop-shadow()>  |
  <grayscale()>    |
  <hue-rotate()>   |
  <invert()>       |
  <opacity()>      |
  <sepia()>        |
  <saturate()>     
```

Examples
--------

### Filter function comparison

This example provides a simple graphic, along with a select menu to
allow you to choose between the different types of filter function, and
a slider to allow you to vary the values used inside the filter
function. Updating the controls updates the filter effect in real time,
allowing you to investigate the effects of different filters.

[css]

```css
div {
  width: 300px;
  height: 300px;
  background: url(firefox.png) no-repeat center;
  filter: <filter-function>(<value>);
}
```

Where the `<filter-function>` is the filter you select from the drop
down and the `<value>` is the values you set with the slider: \'

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [Filter Effects Module Level 1\
  [\#
  typedef-filter-function]](https://drafts.fxtf.org/filter-effects/#typedef-filter-function)

  ----------------------------------------------------------------------------------------------------

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

`filter-function`

18

12

35

No

15

6

4.4

53

35

14

6

6.0

`blur`

18

12

35

No

15

6

4.4

53

35

14

6

6.0

`brightness`

18

12

35

No

15

6

4.4

53

35

14

6

6.0

`contrast`

18

12

35

No

15

6

4.4

53

35

14

6

6.0

`drop-shadow`

18

12

35

No

15

6

4.4

53

35

14

6

6.0

`grayscale`

18

12

35

No

15

6

4.4

53

35

14

6

6.0

`hue-rotate`

18

12

35

No

15

6

4.4

53

35

14

6

6.0

`invert`

18

12

35

No

15

6

4.4

53

35

14

6

6.0

`opacity`

18

12

35

No

15

6

4.4

53

35

14

6

6.0

`saturate`

18

12

35

No

15

6

4.4

53

35

14

6

6.0

`sepia`

18

12

35

No

15

6

4.4

53

35

14

6

6.0

See also
--------

- Properties that use this data type: [`filter`](filter.md) and
    [`backdrop-filter`](backdrop-filter.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function>
