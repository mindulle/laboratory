contain-intrinsic-width
=======================

The `contain-intrinsic-width`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the width of an element that a browser will use for layout when the
element is subject to [](css_containment.md#size_containment).

Syntax
------

[css]

```css
/* Keyword values */
contain-intrinsic-width: none;

/* <length> values */
contain-intrinsic-width: 1000px;
contain-intrinsic-width: 10rem;

/* auto <length> */
contain-intrinsic-width: auto 300px;

/* Global values */
contain-intrinsic-width: inherit;
contain-intrinsic-width: initial;
contain-intrinsic-width: revert;
contain-intrinsic-width: revert-layer;
contain-intrinsic-width: unset;
```

### Values

The following values may be specified for an element.

[`none`](#none)

:   The element has no intrinsic width.

[`<length>`](#length)

:   The element has the specified width ([`<length>`](length.md)).

[`auto <length>`](#auto_length)

:   A remembered value of the \"normally rendered\" element width if one
    exists and the element is skipping its contents (for example, when
    it is offscreen); otherwise the specified `<length>`.

Description
-----------

The property is commonly applied alongside elements that can trigger
size containment, such as [`contain: size`](contain.md) and
[`content-visibility`](content-visibility.md), and may also be set using
the [`contain-intrinsic-size`](contain-intrinsic-size.md) [](shorthand_properties.md).

Size containment allows a user agent to layout an element as though it
had a fixed size, preventing unnecessary reflows by avoiding the
re-rendering of child elements to determine the actual size (thereby
improving user experience). By default, size containment treats elements
as though they had no contents, and may collapse the layout in the same
way as if the contents had no width or height. The
`contain-intrinsic-width` property allows authors to specify an
appropriate value to be used as the width for layout.

The `auto <length>` value allows the width of the element to be stored
if the element is ever \"normally rendered\" (with its child elements),
and then used instead of the specified width when the element is
skipping its contents. This allows offscreen elements with
[`content-visibility: auto`](content-visibility.md) to benefit from size
containment without developers having to be as precise in their
estimates of element size. The remembered value is not used if the child
elements are being rendered (if size containment is enabled, the
`<length>` will be used).

Formal definition
-----------------

  ---------------------------------- ------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         elements for which size containment can apply
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified, with \<length\>s values computed
  Animation type                     by computed value type
  ---------------------------------- ------------------------------------------------

Formal syntax
-------------

```
contain-intrinsic-width = 
  none           |
  <length>       |
  auto <length>  
```

Examples
--------

In addition to the example below, the
[`contain-intrinsic-size`](contain-intrinsic-size.md) page contains a live
example that demonstrates the effect of modifying the intrinsic width
and height.

### Setting the intrinsic width

The HTML below defines an element \"contained\_element\" that will be
subject to size constraint, and which contains a child element.

[html]

```html
<div id="contained_element">
  <div class="child_element"></div>
</div>
```

The CSS below sets the [`content-visibility`](content-visibility.md) of
`contained_element` to `auto`, so if the element is hidden it will be
size constrained. The width and height that are used when it is size
constrained are set at the same time using `contain-intrinsic-width` and
`contain-intrinsic-height`, respectively.

[css]

```css
#contained_element {
  border: 2px solid green;
  width: 151px;
  content-visibility: auto;
  contain-intrinsic-width: 152px;
  contain-intrinsic-height: 52px;
}
.child_element {
  border: 1px solid red;
  background: blue;
  height: 50px;
  width: 150px;
}
```

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------------

  [CSS Box Sizing Module Level 4\
  [\#
  propdef-contain-intrinsic-width]](https://drafts.csswg.org/css-sizing-4/#propdef-contain-intrinsic-width)

  -------------------------------------------------------------------------------------------------------------------

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

`contain-intrinsic-width`

95

95

107

No

81

17

95

95

107

67

17

17.0

See also
--------

- [content-visibility: the new CSS property that boosts your rendering
    performance](https://web.dev/content-visibility/) (web.dev)
- [`contain-intrinsic-size`](contain-intrinsic-size.md)
- [`contain-intrinsic-height`](contain-intrinsic-height.md)
- [`contain-intrinsic-block-size`](contain-intrinsic-block-size.md)
- [`contain-intrinsic-inline-size`](contain-intrinsic-inline-size.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/contain-intrinsic-width>
