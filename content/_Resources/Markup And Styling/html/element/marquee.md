\<marquee\>: The Marquee element
================================

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

The `<marquee>` [HTML](../index) element is used to insert a scrolling
area of text. You can control what happens when the text reaches the
edges of its content area using its attributes.

Attributes
----------

[`behavior`](#behavior) [Deprecated]

:   Sets how the text is scrolled within the marquee. Possible values
    are `scroll`, `slide` and `alternate`. If no value is specified, the
    default value is `scroll`.

[`bgcolor`](#bgcolor) [Deprecated]

:   Sets the background color through color name or hexadecimal value.

[`direction`](#direction) [Deprecated]

:   Sets the direction of the scrolling within the marquee. Possible
    values are `left`, `right`, `up` and `down`. If no value is
    specified, the default value is `left`.

[`height`](#height) [Deprecated]

:   Sets the height in pixels or percentage value.

[`hspace`](#hspace) [Deprecated]

:   Sets the horizontal margin

[`loop`](#loop) [Deprecated]

:   Sets the number of times the marquee will scroll. If no value is
    specified, the default value is −1, which means the marquee will
    scroll continuously.

[`scrollamount`](#scrollamount) [Deprecated]

:   Sets the amount of scrolling at each interval in pixels. The default
    value is 6.

[`scrolldelay`](#scrolldelay) [Deprecated]

:   Sets the interval between each scroll movement in milliseconds. The
    default value is 85. Note that any value smaller than 60 is ignored
    and the value 60 is used instead unless `truespeed` is specified.

[`truespeed`](#truespeed) [Deprecated]

:   By default, `scrolldelay` values lower than 60 are ignored. If
    `truespeed` is present, those values are not ignored.

[`vspace`](#vspace) [Deprecated]

:   Sets the vertical margin in pixels or percentage value.

[`width`](#width) [Deprecated]

:   Sets the width in pixels or percentage value.

Event handlers
--------------

[`onbounce`](#onbounce)

:   Fires when the marquee has reached the end of its scroll position.
    It can only fire when the behavior attribute is set to `alternate`.

[`onfinish`](#onfinish)

:   Fires when the marquee has finished the amount of scrolling that is
    set by the loop attribute. It can only fire when the loop attribute
    is set to some number that is greater than 0.

[`onstart`](#onstart)

:   Fires when the marquee starts scrolling.

Methods
-------

[`start()`](#start)

:   Starts scrolling of the marquee.

[`stop()`](#stop)

:   Stops scrolling of the marquee.

Examples
--------

[html]

```html
<marquee>This text will scroll from right to left</marquee>

<marquee direction="up">This text will scroll from bottom to top</marquee>

<marquee
  direction="down"
  width="250"
  height="200"
  behavior="alternate"
  style="border:solid">
  <marquee behavior="alternate"> This text will bounce </marquee>
</marquee>
```

### Result

Technical summary
-----------------

  --------------- ---------------------------------------------------------------------------------------------
  DOM interface   [`HTMLMarqueeElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMarqueeElement)
  --------------- ---------------------------------------------------------------------------------------------

Specifications
--------------

  --------------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-marquee-element-2]](https://html.spec.whatwg.org/multipage/rendering.html#the-marquee-element-2)

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

`marquee`

1

12

65

1Implements the `HTMLDivElement` interface.

2

7.2

1.2

4.4

18

65

4Implements the `HTMLDivElement` interface.

10.1

1

1.0

`behavior`

1

12

1

2

7.2

1.2

4.4

18

4

10.1

1

1.0

`bgcolor`

1

12

1

2

7.2

1.2

4.4

18

4

10.1

1

1.0

`direction`

1

12

1

2

7.2

1.2

4.4

18

4

10.1

1

1.0

`height`

1

12

1

2

7.2

1.2

4.4

18

4

10.1

1

1.0

`hspace`

1

12

3

5.5

15

1.2

4.4

18

4

14

1

1.0

`loop`

1

12

3

5.5

15

1.2

4.4

18

4

14

1

1.0

`scrollamount`

1

12

1

2

7.2

1.2

4.4

18

4

10.1

1

1.0

`scrolldelay`

1

12

1

2

7.2

1.2

4.4

18

4

10.1

1

1.0

`truespeed`

1

12

3

4

15

1.2

4.4

18

4

14

1

1.0

`vspace`

1

12

3

5.5

15

1.2

4.4

18

4

14

1

1.0

`width`

1

12

1

2

7.2

1.2

4.4

18

4

10.1

1

1.0

See also
--------

- [`HTMLMarqueeElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMarqueeElement)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/marquee>>
