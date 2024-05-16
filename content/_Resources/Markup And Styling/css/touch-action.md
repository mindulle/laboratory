touch-action
============

The `touch-action` CSS property sets how an element\'s region can be
manipulated by a touchscreen user (for example, by zooming features
built into the browser).

By default, panning (scrolling) and pinching gestures are handled
exclusively by the browser. An application using [Pointer
events](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events)
will receive a
[`pointercancel`](https://developer.mozilla.org/en-US/docs/Web/API/Element/pointercancel_event)
event when the browser starts handling a touch gesture. By explicitly
specifying which gestures should be handled by the browser, an
application can supply its own behavior in
[`pointermove`](https://developer.mozilla.org/en-US/docs/Web/API/Element/pointermove_event)
and
[`pointerup`](https://developer.mozilla.org/en-US/docs/Web/API/Element/pointerup_event)
listeners for the remaining gestures. Applications using [Touch
events](https://developer.mozilla.org/en-US/docs/Web/API/Touch_events)
disable the browser handling of gestures by calling
[`preventDefault()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault),
but should also use `touch-action` to ensure the browser knows the
intent of the application before any event listeners have been invoked.

When a gesture is started, the browser intersects the `touch-action`
values of the touched element and its ancestors, up to the one that
implements the gesture (in other words, the first containing scrolling
element). This means that in practice, `touch-action` is typically
applied only to top-level elements which have some custom behavior,
without needing to specify `touch-action` explicitly on any of that
element\'s descendants.

**Note:** After a gesture starts, changes to `touch-action` will not
have any impact on the behavior of the current gesture.

Syntax
------

[css]

```css
/* Keyword values */
touch-action: auto;
touch-action: none;
touch-action: pan-x;
touch-action: pan-left;
touch-action: pan-right;
touch-action: pan-y;
touch-action: pan-up;
touch-action: pan-down;
touch-action: pinch-zoom;
touch-action: manipulation;

/* Global values */
touch-action: inherit;
touch-action: initial;
touch-action: revert;
touch-action: revert-layer;
touch-action: unset;
```

The `touch-action` property may be specified as either:

- One of the keywords `auto`, `none`, [`manipulation`](#manipulation),
    *or*
- One of the keywords `pan-x`, `pan-left`, `pan-right`, and/or one of
    the keywords `pan-y`, `pan-up`, `pan-down`, plus optionally the
    keyword `pinch-zoom`.

### Values

[`auto`](#auto)

:   Enable browser handling of all panning and zooming gestures.

[`none`](#none)

:   Disable browser handling of all panning and zooming gestures.

[`pan-x`](#pan-x)

:   Enable single-finger horizontal panning gestures. May be combined
    with **pan-y**, **pan-up**, **pan-down** and/or **pinch-zoom**.

[`pan-y`](#pan-y)

:   Enable single-finger vertical panning gestures. May be combined with
    **pan-x**, **pan-left**, **pan-right** and/or **pinch-zoom**.

[`manipulation`](#manipulation)

:   Enable panning and pinch zoom gestures, but disable additional
    non-standard gestures such as double-tap to zoom. Disabling
    double-tap to zoom removes the need for browsers to delay the
    generation of **click** events when the user taps the screen. This
    is an alias for \"**pan-x pan-y pinch-zoom**\" (which, for
    compatibility, is itself still valid).

[`pan-left`](#pan-left), `pan-right`, `pan-up`, `pan-down` [Experimental]

:   Enable single-finger gestures that begin by scrolling in the given
    direction(s). Once scrolling has started, the direction may still be
    reversed. Note that scrolling \"up\" (**pan-up**) means that the
    user is dragging their finger downward on the screen surface, and
    likewise **pan-left** means the user is dragging their finger to the
    right. Multiple directions may be combined except when there is a
    simpler representation (for example, **\"pan-left pan-right**\" is
    invalid since \"**pan-x**\" is simpler, but \"**pan-left
    pan-down**\" is valid).

[`pinch-zoom`](#pinch-zoom)

:   Enable multi-finger panning and zooming of the page. This may be
    combined with any of the **pan-** values.

Accessibility concerns
----------------------

A declaration of `touch-action: none;` may inhibit operating a
browser\'s zooming capabilities. This will prevent people experiencing
low vision conditions from being able to read and understand page
content.

- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.4 \| Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html)

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements except: non-replaced inline elements, table rows, row groups, table columns, and column groups
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- -------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
touch-action = 
  auto                                                |
  none                                                |
  [ [ pan-x | pan-left | pan-right ] || [ pan-y | pan-up | pan-down ] || pinch-zoom ]  |
  manipulation                                        
```

Examples
--------

### Disabling all gestures

The most common usage is to disable all gestures on an element (and its
non-scrollable descendants) that provides its own dragging and zooming
behavior -- such as a map or game surface.

#### HTML

[html]

```html
<div id="map"></div>
```

#### CSS

[css]

```css
#map {
  height: 150vh;
  width: 70vw;
  background: linear-gradient(blue, green);
  touch-action: none;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------

  [Compatibility Standard\
  [\# touch-action]](https://compat.spec.whatwg.org/#touch-action)

[Pointer Events\
  [\#
  the-touch-action-css-property]](https://w3c.github.io/pointerevents/#the-touch-action-css-property)
  -------------------------------------------------------------------------------------------------------------

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

`touch-action`

36

12

52Not applicable to Firefox platforms that support neither pointer nor
touch events.

1110

23

13

37

36

52

24

9.3

3.0

`axis-pan`

36

12

52Not applicable to Firefox platforms that support neither pointer nor
touch events.

1110

23

13

37

36

52

24

13

3.0

`double-tap-zoom`

No

12--79

No

1110

No

No

No

No

No

No

No

No

`manipulation`

36

12

52Not applicable to Firefox platforms that support neither pointer nor
touch events.

1110

23

13

37

36

52

24

9.3

3.0

`none`

36

12

52Not applicable to Firefox platforms that support neither pointer nor
touch events.

1110

23

13

37

36

52

24

13

3.0

`pinch-zoom`

56

12

85Not applicable to Firefox platforms that support neither pointer nor
touch events.

1110

43

13

56

56

85Not applicable to Firefox platforms that support neither pointer nor
touch events.

43

13

6.0

`unidirectional-pan`

55

79

No

No

42

No

55

55

No

42

No

6.0

See also
--------

- [`pointer-events`](pointer-events.md)
- [`Pointer Events`](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events)
- WebKit Blog [More Responsive Tapping on
    iOS](https://webkit.org/blog/5610/more-responsive-tapping-on-ios/)
- Google Developers Blog [Making touch scrolling fast by
    default](https://developer.chrome.com/blog/scrolling-intervention/)
- [Scroll Snap](css_scroll_snap.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action>
