video-dynamic-range
===================

The `video-dynamic-range`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](@media.md#media_features) can be used to test the combination
of brightness, contrast ratio, and color depth that are supported by the
video plane of the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) and
the output device.

Some user agents, including many TVs, render video and graphics in two
separate planes (bi-plane) with distinct screen characteristics. The
`video-dynamic-range` feature is used to test the characteristics in the
video plane.

Syntax
------

The `video-dynamic-range` feature is specified as a keyword value chosen
from the list below.

[`standard`](#standard)

:   This value matches any visual device and excludes devices lacking
    visual capabilities. A user agent or an output device that matches
    `high` will also match the `standard` value.

[`high`](#high)

:   This value matches user agents and output devices that support high
    peak brightness, high contrast ratio, and color depth greater than
    24 bit or 8 bit per color component of RGB. **Peak brightness**
    refers to how bright the brightest point a light-emitting device,
    such as an LCD screen, can produce. In the case of a
    light-reflective device, such as paper or e-ink, peak brightness
    refers to the point that at least absorbs light. **Contrast ratio**
    refers to the ratio of the luminance of the brightest color to that
    of the darkest color that the system is capable of producing.
    Currently, there is no precise way to measure peak brightness and
    contrast ratio, and the determination of what counts as high peak
    brightness and high contrast ratio depends on the user agent.

Specifications
--------------

  ---------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------

  [Media Queries Level 5\
  [\#
  video-dynamic-range]](https://drafts.csswg.org/mediaqueries-5/#video-dynamic-range)

  ---------------------------------------------------------------------------------------------

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

`video-dynamic-range`

98

98

100

No

84

No

No

98

100

No

No

No

See also
--------

- [Using Media Queries](using_media_queries.md)
- [\@media](@media.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/video-dynamic-range>
