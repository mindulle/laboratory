overscroll-behavior-block
=========================

The `overscroll-behavior-block` CSS property sets the browser\'s
behavior when the block direction boundary of a scrolling area is
reached.

See [`overscroll-behavior`](overscroll-behavior.md) for a full explanation.

Syntax
------

[css]

```css
/* Keyword values */
overscroll-behavior-block: auto; /* default */
overscroll-behavior-block: contain;
overscroll-behavior-block: none;

/* Global values */
overscroll-behavior-block: inherit;
overscroll-behavior-block: initial;
overscroll-behavior-block: revert;
overscroll-behavior-block: revert-layer;
overscroll-behavior-block: unset;
```

The `overscroll-behavior-block` property is specified as a keyword
chosen from the list of values below.

### Values

[`auto`](#auto)

:   The default scroll overflow behavior occurs as normal.

[`contain`](#contain)

:   Default scroll overflow behavior (e.g., \"bounce\" effects) is
    observed inside the element where this value is set. However, no
    scroll chaining occurs on neighboring scrolling areas; the
    underlying elements will not scroll. The `contain` value disables
    native browser navigation, including the vertical pull-to-refresh
    gesture and horizontal swipe navigation.

[`none`](#none)

:   No scroll chaining occurs to neighboring scrolling areas, and
    default scroll overflow behavior is prevented.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         non-replaced block-level elements and non-replaced inline-block elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------------------------------------------------------------------

Formal syntax
-------------

```
overscroll-behavior-block = 
  contain  |
  none     |
  auto     
```

Examples
--------

### Preventing block overscrolling

In this demo we have two block-level boxes, one inside the other. The
outer box has a large [`height`](_Resources/Markup%20And%20Styling/css/height.md) set on it so the page will
scroll vertically. The inner box has a small [`width`](_Resources/Markup%20And%20Styling/css/width.md) (and
`height`) set on it so it sits comfortably inside the viewport, but its
content is given a large `height` so it will also scroll vertically.

By default, when the inner box is scrolled and a scroll boundary is
reached, the whole page will begin to scroll, which is probably not what
we want. To avoid this happening in the block direction, we\'ve set
`overscroll-behavior-block: contain` on the inner box.

#### HTML

[html]

```html
<main>
  <div>
    <div>
      <p>
        <code>overscroll-behavior-block</code> has been used to make it so that
        when the scroll boundaries of the yellow inner box are reached, the
        whole page does not begin to scroll.
      </p>
    </div>
  </div>
</main>
```

#### CSS

[css]

```css
main {
  height: 3000px;
  width: 500px;
  background-color: white;
  background-image: repeating-linear-gradient(
    to bottom,
    rgba(0, 0, 0, 0) 0px,
    rgba(0, 0, 0, 0) 19px,
    rgba(0, 0, 0, 0.5) 20px
  );
}

main > div {
  height: 300px;
  width: 400px;
  overflow: auto;
  position: relative;
  top: 50px;
  left: 50px;
  overscroll-behavior-block: contain;
}

div > div {
  height: 1500px;
  width: 100%;
  background-color: yellow;
  background-image: repeating-linear-gradient(
    to bottom,
    rgba(0, 0, 0, 0) 0px,
    rgba(0, 0, 0, 0) 19px,
    rgba(0, 0, 0, 0.5) 20px
  );
}

p {
  padding: 10px;
  background-color: rgba(255, 0, 0, 0.5);
  margin: 0;
  width: 340px;
  position: relative;
  top: 10px;
  left: 10px;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------------------------

  [CSS Overscroll Behavior Module Level 1\
  [\#
  overscroll-behavior-longhands-logical]](https://drafts.csswg.org/css-overscroll/#overscroll-behavior-longhands-logical)

  ---------------------------------------------------------------------------------------------------------------------------------

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

`overscroll-behavior-block`

77

79

73

No

64

16

77

77

79

55

16

12.0

See also
--------

- [Take control of your scroll: customizing pull-to-refresh and
    overflow
    effects](https://developer.chrome.com/blog/overscroll-behavior/#full-demo)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-block>
