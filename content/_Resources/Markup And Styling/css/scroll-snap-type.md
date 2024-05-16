scroll-snap-type
================

The `scroll-snap-type`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
how strictly snap points are enforced on the scroll container in case
there is one.

Try it
------

Specifying any precise animations or physics used to enforce those snap
points is not covered by this property but instead left up to the user
agent.

Syntax
------

[css]

```css
/* No snapping */
scroll-snap-type: none;

/* Keyword values for snap axes */
scroll-snap-type: x;
scroll-snap-type: y;
scroll-snap-type: block;
scroll-snap-type: inline;
scroll-snap-type: both;

/* Optional keyword values for snap strictness */
/* mandatory | proximity */
scroll-snap-type: x mandatory;
scroll-snap-type: y proximity;
scroll-snap-type: both mandatory;

/* Global values */
scroll-snap-type: inherit;
scroll-snap-type: initial;
scroll-snap-type: revert;
scroll-snap-type: revert-layer;
scroll-snap-type: unset;
```

### Values

[`none`](#none)

:   When the visual
    [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport)
    of this scroll container is scrolled, it must ignore snap points.

[`x`](#x)

:   The scroll container snaps to snap positions in its horizontal axis
    only.

[`y`](#y)

:   The scroll container snaps to snap positions in its vertical axis
    only.

[`block`](#block)

:   The scroll container snaps to snap positions in its block axis only.

[`inline`](#inline)

:   The scroll container snaps to snap positions in its inline axis
    only.

[`both`](#both)

:   The scroll container snaps to snap positions in both of its axes
    independently (potentially snapping to different elements in each
    axis).

[`mandatory`](#mandatory)

:   The visual viewport of this scroll container must snap to a snap
    position if it isn\'t currently scrolled.

[`proximity`](#proximity)

:   The visual viewport of this scroll container may snap to a snap
    position if it isn\'t currently scrolled. The user agent decides if
    it snaps or not based on scroll parameters. This is the default snap
    strictness if any snap axis is specified.

**Note:** If the content in the snap port is changed (e.g. added, moved,
deleted, or resized) or the value of any scroll snap-related property
(e.g. `scroll-snap-type` or `scroll-margin`) is changed, the scroll
container will be
[resnapped](https://drafts.csswg.org/css-scroll-snap/#re-snap) according
to the latest value of `scroll-snap-type`.

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
scroll-snap-type = 
  none                                                |
  [ x | y | block | inline | both ] [ mandatory | proximity ]?  
```

Examples
--------

### Snapping in different axes

#### HTML

[html]

```html
<div class="holster">
  <div class="container x mandatory-scroll-snapping" dir="ltr">
    <div>X Mand. LTR</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
  </div>
  <div class="container x proximity-scroll-snapping" dir="ltr">
    <div>X Prox. LTR</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
  </div>
  <div class="container y mandatory-scroll-snapping" dir="ltr">
    <div>Y Mand. LTR</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
  </div>
  <div class="container y proximity-scroll-snapping" dir="ltr">
    <div>Y Prox. LTR</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
  </div>
  <div class="container x mandatory-scroll-snapping" dir="rtl">
    <div>X Mand. RTL</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
  </div>
  <div class="container x proximity-scroll-snapping" dir="rtl">
    <div>X Prox. RTL</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
  </div>
  <div class="container y mandatory-scroll-snapping" dir="rtl">
    <div>Y Mand. RTL</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
  </div>
  <div class="container y proximity-scroll-snapping" dir="rtl">
    <div>Y Prox. RTL</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
  </div>
</div>
```

#### CSS

[css]

```css
/* scroll-snap */
.x.mandatory-scroll-snapping {
  scroll-snap-type: x mandatory;
}
.x.proximity-scroll-snapping {
  scroll-snap-type: x proximity;
}
.y.mandatory-scroll-snapping {
  scroll-snap-type: y mandatory;
}
.y.proximity-scroll-snapping {
  scroll-snap-type: y proximity;
}

.container > div {
  text-align: center;
  scroll-snap-align: center;
  flex: none;
}
```

#### Results

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [CSS Scroll Snap Module Level 1\
  [\#
  scroll-snap-type]](https://drafts.csswg.org/css-scroll-snap/#scroll-snap-type)

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

`scroll-snap-type`

69

79

12--79Edge supports an earlier draft of CSS Scroll Snap without axis
values.

99

68--99On macOS 12, scroll snapping does not complete reliably. See [bug
1749352](https://bugzil.la/1749352)

39--68An earlier draft of CSS Scroll Snap without axis values.

10Internet Explorer supports an earlier draft of CSS Scroll Snap without
axis values.

56

11

9Older Safari versions support an earlier draft of CSS Scroll Snap
without axis values.

69

69

68

39--68An earlier draft of CSS Scroll Snap without axis values.

48

11

9Older Safari versions support an earlier draft of CSS Scroll Snap
without axis values.

10.0

See also
--------

- [CSS scroll snap](css_scroll_snap.md)
- [Well-controlled scrolling with CSS scroll
    snap](https://web.dev/css-scroll-snap/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-type>
