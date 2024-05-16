flex-basis
==========

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `flex-basis` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets the initial main size of a flex item. It sets the size of
the content box unless otherwise set with [`box-sizing`](box-sizing.md).

Try it
------

In this example, the [`flex-grow`](flex-grow.md) and
[`flex-shrink`](flex-shrink.md) properties are both set to `1` on all three
items, indicating that the flex item can grow and shrink from the
initial `flex-basis`.

The demo then changes the `flex-basis` on the first item. It will then
grow and shrink from that flex-basis. This means that, for example, when
the `flex-basis` of the first item is `200px`, it will start out at
200px but then shrink to fit the space available with the other items
being at least `min-content` sized.

The image below shows how the Firefox [Flexbox Inspector](https://firefox-source-docs.mozilla.org/devtools-user/page_inspector/how_to/examine_flexbox_layouts/index.html)
helps you understand the size items become:

![The Firefox Flexbox Inspector showing the size of the item once it has
shrunk.](data:image/png;base64,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)

**Note:** In case both `flex-basis` (other than `auto`) and `width` (or
`height` in case of `flex-direction: column`) are set for an element,
`flex-basis` has priority.

Syntax
------

[css]

```css
/* Specify <'width'> */
flex-basis: 10em;
flex-basis: 3px;
flex-basis: 50%;
flex-basis: auto;

/* Intrinsic sizing keywords */
flex-basis: max-content;
flex-basis: min-content;
flex-basis: fit-content;

/* Automatically size based on the flex item's content */
flex-basis: content;

/* Global values */
flex-basis: inherit;
flex-basis: initial;
flex-basis: revert;
flex-basis: revert-layer;
flex-basis: unset;
```

The `flex-basis` property is specified as either the keyword `content`
or a `<'width'>`.

### Values

[`<'width'>`](#width)

:   Any of the following units:

    -   [`<length>`](length) sets an absolute value
    -   [`<percentage>`](percentage) sets a percentage of the width or
        height of a containing block\'s content area
    -   `auto` uses the value of the
        [width](https://drafts.csswg.org/css2/#the-width-property) in
        horizontal writing mode, and the value of the
        [height](https://drafts.csswg.org/css2/#the-height-property) in
        vertical writing mode; when the corresponding value is also
        `auto`, the `content` value is used instead
    -   `max-content` sets the intrinsic preferred width
    -   `min-content` sets the intrinsic minimum width
    -   `fit-content` sets the maximum possible size of a containing
        block\'s content area, bounded by the `min-content` and
        `max-content` values, and calculated based on the content of the
        current element

[`content`](#content)

:   Indicates automatic sizing, based on the flex item\'s content.

    **Note:** This value was not present in the initial release of
    Flexible Box Layout, and thus some older implementations will not
    support it. The equivalent effect can be had by using `auto`
    together with a main size
    ([width](https://drafts.csswg.org/css2/#the-width-property) or
    [height](https://drafts.csswg.org/css2/#the-height-property)) of
    `auto`.

    -   Originally, `flex-basis:auto` meant \"look at my `width` or
        `height` property\".
    -   Then, `flex-basis:auto` was changed to mean automatic sizing,
        and \"main-size\" was introduced as the \"look at my `width` or
        `height` property\" keyword. It was implemented in [Firefox bug
        1032922](https://bugzil.la/1032922).
    -   Then, that change was reverted in [Firefox bug
        1093316](https://bugzil.la/1093316), so `auto` once again means
        \"look at my `width` or `height` property\"; and a new `content`
        keyword is being introduced to trigger automatic sizing.
        ([Firefox bug 1105111](https://bugzil.la/1105111) covers adding
        that keyword).

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         flex items, including in-flow pseudo-elements
  [Inherited](inheritance.md)           no
  Percentages                        refer to the flex container\'s inner main size
  [Computed value](computed_value.md)   as specified, but with relative lengths converted into absolute lengths
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- -------------------------------------------------------------------------------------

Formal syntax
-------------

```
flex-basis = 
  content    |
  <'width'>  
```

Examples
--------

### Setting flex item initial sizes

#### HTML

[html]

```html
<ul class="container">
  <li class="flex flex1">1: flex-basis test</li>
  <li class="flex flex2">2: flex-basis test</li>
  <li class="flex flex3">3: flex-basis test</li>
  <li class="flex flex4">4: flex-basis test</li>
  <li class="flex flex5">5: flex-basis test</li>
</ul>

<ul class="container">
  <li class="flex flex6">6: flex-basis test</li>
</ul>
```

#### CSS

[css]

```css
.container {
  font-family: arial, sans-serif;
  margin: 0;
  padding: 0;
  list-style-type: none;
  display: flex;
  flex-wrap: wrap;
}

.flex {
  background: #6ab6d8;
  padding: 10px;
  margin-bottom: 50px;
  border: 3px solid #2e86bb;
  color: white;
  font-size: 14px;
  text-align: center;
  position: relative;
}

.flex::after {
  position: absolute;
  z-index: 1;
  left: 0;
  top: 100%;
  margin-top: 10px;
  width: 100%;
  color: #333;
  font-size: 12px;
}

.flex1 {
  flex-basis: auto;
}

.flex1::after {
  content: "auto";
}

.flex2 {
  flex-basis: max-content;
}

.flex2::after {
  content: "max-content";
}

.flex3 {
  flex-basis: min-content;
}

.flex3::after {
  content: "min-content";
}

.flex4 {
  flex-basis: fit-content;
}

.flex4::after {
  content: "fit-content";
}

.flex5 {
  flex-basis: content;
}

.flex5::after {
  content: "content";
}
```

#### Results

Specifications
--------------

  ------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------

  [CSS Flexible Box Layout Module Level 1\
  [\#
  flex-basis-property]](https://drafts.csswg.org/css-flexbox/#flex-basis-property)

  ------------------------------------------------------------------------------------------

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

`flex-basis`

2922

1212

49

22Since Firefox 28, multi-line flexbox is supported.

11When a non-`auto` `flex-basis` is specified, Internet Explorer 10 and
11 always uses a `content-box` box model to calculate the size of a flex
item, even if
[`box-sizing: border-box`](https://developer.mozilla.org/docs/Web/CSS/box-sizing)
is applied to the element. See [Flexbug
\#7](https://github.com/philipwalton/flexbugs#7-flex-basis-doesnt-account-for-box-sizingborder-box)
for more info.

1512.1

97

≤374.4

2925

49

22Since Firefox 28, multi-line flexbox is supported.

1412.1

97

2.01.5

`auto`

22

12

22

11

12.1

97

4.4

25

22

12.1

97

1.5

`content`

94

9412--79

61

No

80

15.4

94

94

61

66

15.4

17.0

`fit-content`

94

94

9422

No

80

16

94

94

9422

66

16

17.0

`max-content`

94

94

6622

No

80

16

94

94

6622

66

16

17.0

`min-content`

94

94

6622

No

80

16

94

94

6622

66

16

17.0

See also
--------

- CSS Flexbox Guide: *[](basic_concepts_of_flexbox.md)*
- CSS Flexbox Guide: *[](controlling_ratios_of_flex_items_along_the_main_axis.md)*
- [`width`](_Resources/Markup%20And%20Styling/css/width.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/flex-basis>
