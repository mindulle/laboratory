flex-shrink
===========

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `flex-shrink`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the flex shrink factor of a flex item. If the size of all flex items is
larger than the flex container, items shrink to fit according to
`flex-shrink`.

In use, `flex-shrink` is used alongside the other flex properties
[`flex-grow`](flex-grow.md) and [`flex-basis`](flex-basis.md), and normally
defined using the [`flex`](flex.md) shorthand.

Try it
------

Syntax
------

[css]

```css
/* <number> values */
flex-shrink: 2;
flex-shrink: 0.6;

/* Global values */
flex-shrink: inherit;
flex-shrink: initial;
flex-shrink: revert;
flex-shrink: revert-layer;
flex-shrink: unset;
```

The `flex-shrink` property is specified as a single `<number>`.

### Values

[`<number>`](#number)

:   See [`<number>`](number.md). Negative values are invalid. Defaults
    to 1.

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------
  [Initial value](initial_value.md)     `1`
  Applies to                         flex items, including in-flow pseudo-elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     a [number](number.md#interpolation)
  ---------------------------------- -----------------------------------------------

Formal syntax
-------------

```
flex-shrink = 
  <number [0,∞]>  
```

Examples
--------

### Setting flex item shrink factor

#### HTML

[html]

```html
<p>The width of content is 500px; the flex-basis of the flex items is 120px.</p>
<p>A, B, C have flex-shrink:1 set. D and E have flex-shrink:2 set</p>
<p>The width of D and E is less than the others.</p>
<div id="content">
  <div class="box" style="background-color:red;">A</div>
  <div class="box" style="background-color:lightblue;">B</div>
  <div class="box" style="background-color:yellow;">C</div>
  <div class="box1" style="background-color:brown;">D</div>
  <div class="box1" style="background-color:lightgreen;">E</div>
</div>
```

#### CSS

[css]

```css
#content {
  display: flex;
  width: 500px;
}

#content div {
  flex-basis: 120px;
  border: 3px solid rgba(0, 0, 0, 0.2);
}

.box {
  flex-shrink: 1;
}

.box1 {
  flex-shrink: 2;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------

  [CSS Flexible Box Layout Module Level 1\
  [\#
  flex-shrink-property]](https://drafts.csswg.org/css-flexbox/#flex-shrink-property)

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

`flex-shrink`

2922

1212

49

20\[\"Since Firefox 28, multi-line flexbox is supported.\", \"Before
Firefox 32, Firefox wasn\'t able to animate values starting or stopping
at `0`.\"\]

10Internet Explorer 10 uses `0` instead of `1` as the initial value for
the `flex-shrink` property. A workaround is to always set an explicit
value for `flex-shrink`. See [Flexbug
\#6](https://github.com/philipwalton/flexbugs#6-the-default-flex-value-has-changed)
for more info.

1512.1

98

≤374.4

2925

49

20\[\"Since Firefox 28, multi-line flexbox is supported.\", \"Before
Firefox 32, Firefox wasn\'t able to animate values starting or stopping
at `0`.\"\]

1412.1

98

2.01.5

See also
--------

- CSS Flexbox Guide: *[](basic_concepts_of_flexbox.md)*
- CSS Flexbox Guide: *[](controlling_ratios_of_flex_items_along_the_main_axis.md)*

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/flex-shrink>
