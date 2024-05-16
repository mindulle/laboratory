overflow-clip-margin
====================

The `overflow-clip-margin`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
determines how far outside its bounds an element with
[`overflow: clip`](overflow.md) may be painted before being clipped. The
bound defined by this property is called the *overflow clip edge* of the
box.

Syntax
------

[css]

```css
/* <length> values */
overflow-clip-margin: 20px;
overflow-clip-margin: 1em;

/* <visual-box> | <length> */
overflow-clip-margin: content-box 5px;

/* Global values */
overflow-clip-margin: inherit;
overflow-clip-margin: initial;
overflow-clip-margin: revert;
overflow-clip-margin: revert-layer;
overflow-clip-margin: unset;
```

The `<visual-box>` value, which defaults to `padding-box`, specifies the
box edge to use as the overflow clip edge origin. The
[`<length>`](length.md) value specified in `overflow-clip-margin` must be
nonnegative.

**Note:** If the element does not have `overflow: clip` then this
property will be ignored.

Formal definition
-----------------

  ---------------------------------- ------------------------------------------------------
  [Initial value](initial_value.md)     `0px`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   the computed \<length\> and a \<visual-box\> keyword
  Animation type                     discrete
  ---------------------------------- ------------------------------------------------------

Formal syntax
-------------

```
overflow-clip-margin = 
  <visual-box>    ||
  <length [0,∞]>  

<visual-box> = 
  content-box  |
  padding-box  |
  border-box   
```

Examples
--------

### HTML

[html]

```html
<div class="box">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
  tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
  quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
  consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
  cillum dolore eu fugiat nulla pariatur.
</div>
```

### CSS

[css]

```css
.box {
  border: 3px solid black;
  width: 250px;
  height: 100px;
  overflow: clip;
  overflow-clip-margin: 20px;
}
```

### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------

  [CSS Overflow Module Level 3\
  [\#
  overflow-clip-margin]](https://drafts.csswg.org/css-overflow/#overflow-clip-margin)

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

`overflow-clip-margin`

90Only works when both axes are using `overflow: clip`. See [bug
1354474](https://crbug.com/1354474).

90Only works when both axes are using `overflow: clip`. See [bug
1354474](https://crbug.com/1354474).

102Only supports using a length, not a visual box. See [bug
1661582](https://bugzil.la/1661582).

No

76Only works when both axes are using `overflow: clip`. See [bug
1354474](https://crbug.com/1354474).

No

90Only works when both axes are using `overflow: clip`. See [bug
1354474](https://crbug.com/1354474).

90Only works when both axes are using `overflow: clip`. See [bug
1354474](https://crbug.com/1354474).

102Only supports using a length, not a visual box. See [bug
1661582](https://bugzil.la/1661582).

64Only works when both axes are using `overflow: clip`. See [bug
1354474](https://crbug.com/1354474).

No

15.0Only works when both axes are using `overflow: clip`. See [bug
1354474](https://crbug.com/1354474).

See also
--------

- Related CSS properties: [`text-overflow`](text-overflow.md),
    [`white-space`](white-space.md), [`overflow`](overflow.md),
    [`overflow-inline`](_Resources/Markup%20And%20Styling/css/overflow-inline.md), [`overflow-x`](overflow-x.md),
    [`overflow-y`](overflow-y.md), [`clip`](clip.md), [`display`](display.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-clip-margin>
