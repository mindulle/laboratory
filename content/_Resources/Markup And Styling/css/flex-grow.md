flex-grow
=========

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `flex-grow` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets the flex grow factor, which specifies how much of the flex
container\'s remaining space should be assigned to the flex item\'s
[main size](https://www.w3.org/TR/css-flexbox/#main-size).

When the flex-container\'s main size is larger than the combined main
size\'s of the flex items, the extra space is distributed among the flex
items, with each item growth being their growth factor value as a
proportion of the sum total of all the container\'s items\' flex grow
factors.

Try it
------

Syntax
------

[css]

```css
/* <number> values */
flex-grow: 3;
flex-grow: 0.6;

/* Global values */
flex-grow: inherit;
flex-grow: initial;
flex-grow: revert;
flex-grow: revert-layer;
flex-grow: unset;
```

The `flex-grow` property is specified as a single `<number>`.

### Values

[`<number>`](#number)

:   See [`<number>`](number.md). Negative values are invalid. Defaults
    to 0.

Description
-----------

This property specifies how much of the remaining space in the flex
container should be assigned to the item (the flex grow factor).

The [main size](https://www.w3.org/TR/css-flexbox/#main-size) is either
width or height of the item which is dependent on the
[`flex-direction`](flex-direction.md) value.

The remaining space is the size of the flex container minus the size of
all flex items\' sizes together. If all sibling items have the same flex
grow factor, then all items will receive the same share of remaining
space, otherwise it is distributed according to the ratio defined by the
different flex grow factors.

`flex-grow` is used alongside the other flex properties
[`flex-shrink`](flex-shrink.md) and [`flex-basis`](flex-basis.md), and
normally defined using the [`flex`](flex.md) shorthand to ensure all values
are set.

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         flex items, including in-flow pseudo-elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     a [number](number.md#interpolation)
  ---------------------------------- -----------------------------------------------

Formal syntax
-------------

```
flex-grow = 
  <number [0,∞]>  
```

Examples
--------

### Setting flex item grow factor

In this example, there is a total of 8 growth factors distributed among
the 6 flex items, meaning each growth factor is 12.5% of the remaining
space.

#### HTML

[html]

```html
<h4>This is a Flex-Grow</h4>
<h5>A,B,C and F are flex-grow:1 . D and E are flex-grow:2 .</h5>
<div id="content">
  <div class="small" style="background-color:red;">A</div>
  <div class="small" style="background-color:lightblue;">B</div>
  <div class="small" style="background-color:yellow;">C</div>
  <div class="double" style="background-color:brown;">D</div>
  <div class="double" style="background-color:lightgreen;">E</div>
  <div class="small" style="background-color:brown;">F</div>
</div>
```

#### CSS

[css]

```css
#content {
  display: flex;

  justify-content: space-around;
  flex-flow: row wrap;
  align-items: stretch;
}

.small {
  flex-grow: 1;
  border: 3px solid rgba(0, 0, 0, 0.2);
}

.double {
  flex-grow: 2;
  border: 3px solid rgba(0, 0, 0, 0.2);
}
```

#### Result

When the six flex items are distributed along the container\'s main
axis, if the sum of the main content of those flex items is less than
the size of the container\'s main axis, the extra space is distributed
among the size flex items, with A, B, C, and F, each getting 12.5% of
the remaining space and D and E each getting 25% of the extra space.

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [CSS Flexible Box Layout Module Level 1\
  [\#
  flex-grow-property]](https://drafts.csswg.org/css-flexbox/#flex-grow-property)

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

`flex-grow`

2922

1212

20Since Firefox 28, multi-line flexbox is supported.

1110

1512.1

97

≤374.4

2925

20Since Firefox 28, multi-line flexbox is supported.

1412.1

97

2.01.5

`less_than_zero_animate`

49

79

32Before Firefox 32, Firefox wasn\'t able to animate values starting or
stopping at `0`.

No

36

No

49

49

32Before Firefox 32, Firefox wasn\'t able to animate values starting or
stopping at `0`.

36

No

5.0

See also
--------

- CSS Flexbox Guide: *[](basic_concepts_of_flexbox.md)*
- CSS Flexbox Guide: *[](controlling_ratios_of_flex_items_along_the_main_axis.md)*
- [`flex-grow` is weird. Or is
    it?](https://css-tricks.com/flex-grow-is-weird/) article by Manuel
    Matuzovic on CSS-Tricks, which illustrates how flex-grow works

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow>
