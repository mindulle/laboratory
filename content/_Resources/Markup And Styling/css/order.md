order
=====

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `order` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets the order to lay out an item in a flex or grid container.
Items in a container are sorted by ascending `order` value and then by
their source code order.

Try it
------

Syntax
------

[css]

```css
/* <integer> values */
order: 5;
order: -5;

/* Global values */
order: inherit;
order: initial;
order: revert;
order: revert-layer;
order: unset;
```

Since `order` is only meant to affect the *visual order* of elements and
not their logical or tab order. `order` must not be used on non-visual
media such as [speech](@media.md#speech).

### Values

[`<integer>`](integer.md)

:   Represents the ordinal group to be used by the item.

Accessibility concerns
----------------------

Using the `order` property will create a disconnect between the visual
presentation of content and DOM order. This will adversely affect users
experiencing low vision navigating with the aid of assistive technology
such as a screen reader. If the visual (css) order is important, then
screen reader users will not have access to the correct reading order.

- [Flexbox & the keyboard navigation disconnect ---
    Tink](https://tink.uk/flexbox-the-keyboard-navigation-disconnect/)
- [Source Order Matters \| Adrian
    Roselli](https://adrianroselli.com/2015/09/source-order-matters.html)
- [MDN Understanding WCAG, Guideline 1.3
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.3_%e2%80%94_create_content_that_can_be_presented_in_different_ways)
- [Understanding Success Criterion 1.3.2 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-sequence.html)

Formal definition
-----------------

  ---------------------------------- ------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         Flex items, grid items, and absolutely-positioned flex and grid container children
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     an [integer](integer.md#interpolation)
  ---------------------------------- ------------------------------------------------------------------------------------

Formal syntax
-------------

```
order = 
  <integer>  
```

Examples
--------

### Ordering items in a flex container

This example uses CSS to create a classic two-sidebar layout surrounding
a content block. The Flexible Box Layout Module automatically creates
blocks of equal vertical size and uses as much horizontal space as
available.

#### HTML

[html]

```html
<header>…</header>
<main>
  <article>Article</article>
  <nav>Nav</nav>
  <aside>Aside</aside>
</main>
<footer>…</footer>
```

#### CSS

[css]

```css
main {
  display: flex;
  text-align: center;
}
main > article {
  flex: 1;
  order: 2;
}
main > nav {
  width: 200px;
  order: 1;
}
main > aside {
  width: 200px;
  order: 3;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------

  [CSS Display Module Level 3\
  [\#
  order-property]](https://drafts.csswg.org/css-display/#order-property)

  --------------------------------------------------------------------------------

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

`order`

2921

1212

49

20Since Firefox 28, multi-line flexbox is supported.

1110

12.1

97

≤374.4

2925

49

20Since Firefox 28, multi-line flexbox is supported.

12.1

97

2.01.5

See also
--------

- CSS Flexbox Guide: *[](basic_concepts_of_flexbox.md)*
- CSS Flexbox Guide: *[](ordering_flex_items.md)*
- CSS Grid Guide: *[](grid_layout_and_accessibility.md)*

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/order>
