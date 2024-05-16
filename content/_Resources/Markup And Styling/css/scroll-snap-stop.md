scroll-snap-stop
================

The `scroll-snap-stop`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
whether or not the scroll container is allowed to \"pass over\" possible
snap positions.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
scroll-snap-stop: normal;
scroll-snap-stop: always;

/* Global values */
scroll-snap-stop: inherit;
scroll-snap-stop: initial;
scroll-snap-stop: revert;
scroll-snap-stop: revert-layer;
scroll-snap-stop: unset;
```

### Values

[`normal`](#normal)

:   When the visual
    [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport)
    of this element\'s scroll container is scrolled, it may \"pass
    over\" possible snap positions.

[`always`](#always)

:   The scroll container must not \"pass over\" a possible snap
    position; and must snap to the first of this elements\' snap
    positions.

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
scroll-snap-stop = 
  normal  |
  always  
```

Examples
--------

### Setting different snap stops

The example below demonstrates the contrast between the `always` and
`normal` values of `scroll-snap-stop`. The difference in the two
`scroll-snap-stop` values is more noticeable when the `scroll-snap-type`
property is set to `mandatory`, which is what is used in this example.

#### HTML

[html]

```html
<p>scroll-snap-stop: always (X Mandatory)</p>
<div class="x mandatory-scroll-snapping always-stop">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
</div>

<p>scroll-snap-stop: always (X Mandatory) on odd child elements</p>
<div class="x mandatory-scroll-snapping always-stop-odd">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
</div>

<p>scroll-snap-stop: always (X Mandatory) on even child elements</p>
<div class="x mandatory-scroll-snapping always-stop-even">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
</div>

<p>scroll-snap-stop: normal (X Mandatory)</p>
<div class="x mandatory-scroll-snapping normal-stop">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
</div>

<p>scroll-snap-stop: always (Y Mandatory)</p>
<div class="y mandatory-scroll-snapping always-stop">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
</div>

<p>scroll-snap-stop: normal (Y Mandatory)</p>
<div class="y mandatory-scroll-snapping normal-stop">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
</div>
```

#### CSS

[css]

```css
/* setting up mandatory scroll-snap on parent */
.x.mandatory-scroll-snapping {
  scroll-snap-type: x mandatory;
}

.y.mandatory-scroll-snapping {
  scroll-snap-type: y mandatory;
}

/* defining scroll-snap alignment on children */
div > div {
  scroll-snap-align: center;
}

/* defining scroll-snap stop on children */
.always-stop > div {
  scroll-snap-stop: always;
}

.always-stop-odd > div:nth-of-type(odd) {
  scroll-snap-stop: always;
}

.always-stop-even > div:nth-of-type(even) {
  scroll-snap-stop: always;
}

.normal-stop > div {
  scroll-snap-stop: normal;
}
```

#### Result

Scroll from left to right and from top to bottom in the X and Y boxes
below, respectively. In the X and Y boxes where the `scroll-snap-stop`
property is set to `always`, the scrolling is forced to stop at the snap
point even when you scroll fast. However, in the boxes where the
`scroll-snap-stop` property is set to `normal`, the snap points are
skipped when you scroll fast.

If required, you can be selective about the items that are `always`
stopped at inside the scroll container. This is demonstrated in the
example below by targeting odd and even items; you can choose a
different strategy based on your requirement. In the example below,
scrolling does not \"pass over\" odd and even items in the second and
third boxes, respectively.

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [CSS Scroll Snap Module Level 1\
  [\#
  scroll-snap-stop]](https://drafts.csswg.org/css-scroll-snap/#scroll-snap-stop)

  ----------------------------------------------------------------------------------------

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

`scroll-snap-stop`

75

79

103

No

62

15

75

75

103

54

15

11.0

See also
--------

- [CSS scroll snap](css_scroll_snap.md)
- [Well-controlled scrolling with CSS scroll
    snap](https://web.dev/css-scroll-snap/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-stop>
