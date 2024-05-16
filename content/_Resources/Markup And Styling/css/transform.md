transform
=========

The `transform` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property lets you rotate, scale, skew, or translate an element. It
modifies the coordinate space of the CSS [](visual_formatting_model.md).

Try it
------

If the property has a value different than `none`, a [](stacking_context.md)
will be created. In that case, the element will act as a [](containing_block.md) for any `position: fixed;` or
`position: absolute;` elements that it contains.

**Warning:** Only transformable elements can be `transform`ed. That is,
all elements whose layout is governed by the CSS box model except for:
[non-replaced inline
boxes](https://developer.mozilla.org/en-US/docs/Glossary/Inline-level_content),
[table-column
boxes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col),
and [table-column-group
boxes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/colgroup).

Syntax
------

[css]

```css
/* Keyword values */
transform: none;

/* Function values */
transform: matrix(1, 2, 3, 4, 5, 6);
transform: matrix3d(1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1);
transform: perspective(17px);
transform: rotate(0.5turn);
transform: rotate3d(1, 2, 3, 10deg);
transform: rotateX(10deg);
transform: rotateY(10deg);
transform: rotateZ(10deg);
transform: translate(12px, 50%);
transform: translate3d(12px, 50%, 3em);
transform: translateX(2em);
transform: translateY(3in);
transform: translateZ(2px);
transform: scale(2, 0.5);
transform: scale3d(2.5, 1.2, 0.3);
transform: scaleX(2);
transform: scaleY(0.5);
transform: scaleZ(0.3);
transform: skew(30deg, 20deg);
transform: skewX(30deg);
transform: skewY(1.07rad);

/* Multiple function values */
transform: translateX(10px) rotate(10deg) translateY(5px);
transform: perspective(500px) translate(10px, 0, 20px) rotateY(3deg);

/* Global values */
transform: inherit;
transform: initial;
transform: revert;
transform: revert-layer;
transform: unset;
```

The `transform` property may be specified as either the keyword value
`none` or as one or more `<transform-function>` values.

If [`perspective()`](_Resources/Markup%20And%20Styling/css/transform-function/perspective.md) is one of multiple
function values, it must be listed first.

### Values

[`<transform-function>`](transform-function.md)

:   One or more of the [CSS transform functions](transform-function.md) to
    be applied. The transform functions are multiplied in order from
    left to right, meaning that composite transforms are effectively
    [applied in order from right to left](#transform_order).

[`none`](#none)

:   Specifies that no transform should be applied.

Accessibility concerns
----------------------

Scaling/zooming animations are problematic for accessibility, as they
are a common trigger for certain types of migraine. If you need to
include such animations on your website, you should provide a control to
allow users to turn off animations, preferably site-wide.

Also, consider making use of the
[`prefers-reduced-motion`](prefers-reduced-motion.md) media feature
--- use it to write a [media query](css_media_queries.md) that will turn
off animations if the user has reduced animation specified in their
system preferences.

Find out more:

- [MDN Understanding WCAG, Guideline 2.3
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#guideline_2.3_%E2%80%94_seizures_and_physical_reactions_do_not_design_content_in_a_way_that_is_known_to_cause_seizures_or_physical_reactions)
- [Understanding Success Criterion 2.3.3 \| W3C Understanding WCAG
    2.1](https://www.w3.org/WAI/WCAG21/Understanding/animation-from-interactions)

Formal definition
-----------------

  ------------------------------------------------------------------------------------------ -------------------------------------------------------------------------
  [Initial value](initial_value.md)                                                             `none`
  Applies to                                                                                 transformable elements
  [Inherited](inheritance.md)                                                                   no
  Percentages                                                                                refer to the size of bounding box
  [Computed value](computed_value.md)                                                           as specified, but with relative lengths converted into absolute lengths
  Animation type                                                                             a transform
  Creates [stacking context](stacking_context.md)   yes
  ------------------------------------------------------------------------------------------ -------------------------------------------------------------------------

Formal syntax
-------------

```
transform = 
  none              |
  <transform-list>  

<transform-list> = 
  <transform-function>+  
```

Examples
--------

### Translating and rotating an element

#### HTML

[html]

```html
<div>Transformed element</div>
```

#### CSS

[css]

```css
div {
  border: solid red;
  transform: translate(30px, 20px) rotate(20deg);
  width: 140px;
  height: 60px;
}
```

#### Result

### Transform order

The order of transform functions matters. In this example, two boxes are
rotated and translated by the same values; only the transform function
order is different.

#### HTML

[html]

```html
<div class="original"></div>
<div class="one">1</div>
<div class="two">2</div>
```

#### CSS

[css]

```css
.one {
  transform: translateX(200px) rotate(135deg);
}
.two {
  transform: rotate(135deg) translateX(200px);
}
```

#### Result

When an element is rotated before being translated, the translate
direction is on the rotated axis. The axis as indicated with the dotted
lines.

### More examples

Please see [Using CSS transforms](using_css_transforms.md)
and [`<transform-function>`](transform-function.md) for more examples.

Specifications
--------------

  -----------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------

  [CSS Transforms Module Level 2\
  [\#
  transform-functions]](https://drafts.csswg.org/css-transforms-2/#transform-functions)

[CSS Transforms Module Level 1\
  [\# transform-property]](https://drafts.csswg.org/css-transforms/#transform-property)
  -----------------------------------------------------------------------------------------------

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

`3d`

12

12

16

10

15

4

4.4

18

16

14

3.2

1.0

`transform`

361

1212

4916

11

10Internet Explorer does not support the global values `initial` and
`unset`.

9Internet Explorer 5.5 or later supports a proprietary [Matrix
Filter](https://msdn.microsoft.com/en-us/library/ms533014(VS.85,loband).aspx)
which can be used to achieve a similar effect.

231512.1--1510.5--15

93.1

4.4

2Android 2.3 has a bug where input forms will \"jump\" when typing, if
any container element has a `-webkit-transform`.

3618

4916

241412.1--1411--14

93.2

3.01.0

See also
--------

- [Using CSS transforms](using_css_transforms.md)
- [`<transform-function>`](transform-function.md) data type with all the
    transform functions explained.
- Individual CSS properties: [`translate`](_Resources/Markup%20And%20Styling/css/translate.md),
    [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md), and [`scale`](_Resources/Markup%20And%20Styling/css/scale.md) (there is no `skew`
    property).
- Online tool to visualize CSS Transform functions: [CSS Transform
    Playground](https://css-transform.moro.es/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transform>
