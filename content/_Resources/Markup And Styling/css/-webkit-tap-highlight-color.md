-webkit-tap-highlight-color
===========================

**Non-standard:** This feature is non-standard and is not on a standards
track. Do not use it on production sites facing the Web: it will not
work for every user. There may also be large incompatibilities between
implementations and the behavior may change in the future.

`-webkit-tap-highlight-color` is a non-standard CSS property that sets
the color of the highlight that appears over a link while it\'s being
tapped. The highlighting indicates to the user that their tap is being
successfully recognized, and indicates which element they\'re tapping
on.

Syntax
------

[css]

```css
-webkit-tap-highlight-color: red;
-webkit-tap-highlight-color: transparent; /* for removing the highlight */

/* Global values */
-webkit-tap-highlight-color: inherit;
-webkit-tap-highlight-color: initial;
-webkit-tap-highlight-color: revert;
-webkit-tap-highlight-color: revert-layer;
-webkit-tap-highlight-color: unset;
```

### Values

A [`<color>`](color_value.md).

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `black`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
-webkit-tap-highlight-color =
  <color>
```

Specifications
--------------

Not part of any standard. Apple has [a description in the Safari Web
Content
Guide](https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariWebContent/AdjustingtheTextSize/AdjustingtheTextSize.html#//apple_ref/doc/uid/TP40006510-SW5).

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

`-webkit-tap-highlight-color`

16

12

No

No

15

No

≤37

18

No

14

4

1.0

See also
--------

- [WebKit CSS
    extensions](https://developer.mozilla.org/en-US/docs/Web/CSS/WebKit_Extensions)
- Related CSS pseudo-classes:
  - [`:hover`](:hover)
  - [`:active`](:active)
  - [`:visited`](:visited)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-tap-highlight-color>
