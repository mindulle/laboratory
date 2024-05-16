text-size-adjust
================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `text-size-adjust`
[CSS](https://developer.mozilla.org/en-US/docs/Web/API/CSS) property
controls the text inflation algorithm used on some smartphones and
tablets. Other browsers will ignore this property.

Because many websites have not been developed with small devices in
mind, mobile browsers differ from desktop browsers in the way they
render web pages. Instead of laying out pages at the width of the device
screen, they lay them out using a
[viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport)
that is much wider, usually 800 or 1000 pixels. To map the extra-wide
layout back to the original device size, they either show only part of
the whole render or scale the viewport down to fit.

Since text that has been scaled down to fit a mobile screen may be very
small, many mobile browsers apply a text inflation algorithm to enlarge
the text to make it more readable. When an element containing text uses
100% of the screen\'s width, the algorithm increases its text size, but
without modifying the layout. The `text-size-adjust` property allows web
authors to disable or modify this behavior, as web pages designed with
small screens in mind do not need it.

Syntax
------

[css]

```css
/* Keyword values */
text-size-adjust: none;
text-size-adjust: auto;

/* <percentage> value */
text-size-adjust: 80%;

/* Global values */
text-size-adjust: inherit;
text-size-adjust: initial;
text-size-adjust: revert;
text-size-adjust: revert-layer;
text-size-adjust: unset;
```

The `text-size-adjust` property is specified as `none`, `auto`, or a
`<percentage>`.

### Values

[`none`](#none)

:   Disables the browser\'s inflation algorithm.

[`auto`](#auto)

:   Enables the browser\'s inflation algorithm. This value is used to
    cancel a `none` value previously set with CSS.

[`<percentage>`](#percentage)

:   Enables the browser\'s inflation algorithm, specifying a percentage
    value with which to increase the font size.

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto` for smartphone browsers supporting inflation, `none` in other cases (and then not modifiable).
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  Percentages                        yes, refer to the corresponding size of the text font
  [Computed value](computed_value.md)   as specified
  Animation type                     by computed value type
  ---------------------------------- -------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
text-size-adjust = 
  auto                |
  none                |
  <percentage [0,∞]>  
```

Examples
--------

### Basic disabling usage

As hinted at above, on a properly designed responsive site the
`text-size-adjust` behavior is not needed, so developers can elect to
turn it off by specifying a value of none:

[css]

```css
p {
  -webkit-text-size-adjust: none;
  text-size-adjust: none;
}
```

Specifications
--------------

  --------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------

  [CSS Mobile Text Size Adjustment Module Level 1\
  [\#
  adjustment-control]](https://drafts.csswg.org/css-size-adjust/#adjustment-control)

  --------------------------------------------------------------------------------------------

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

`text-size-adjust`

54

7912--79

No

No

41

No

54

54

4914

41

1

6.0

`percentages`

54

12

No

No

41

No

54

54

No

41

No

6.0

See also
--------

- [Apple\'s
    documentation](https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariWebContent/AdjustingtheTextSize/AdjustingtheTextSize.html#//apple_ref/doc/uid/TP40006510-SW16)
- [Google Chrome behavior
    description](https://docs.google.com/document/d/1PPcEwAhXJJ1TQShor29KWB17KJJq7UJOM34oHwYP3Zg/edit)
- [Gecko\'s behavior
    description](https://dbaron.org/log/20111126-font-inflation), by L.
    David Baron

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-size-adjust>
