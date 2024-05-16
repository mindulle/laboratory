scrollbar-color
===============

The `scrollbar-color`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the color of the scrollbar track and thumb.

The **track** refers to the background of the scrollbar, which is
generally fixed regardless of the scrolling position.

The **thumb** refers to the moving part of the scrollbar, which usually
floats on top of the track.

When `scrollbar-color` value is set on the document\'s root element, the
values are applied to the viewport scrollbars.

Syntax
------

[css]

```css
/* Keyword values */
scrollbar-color: auto;

/* <color> values */
scrollbar-color: rebeccapurple green; /* Two valid colors.
The first applies to the thumb of the scrollbar, the second to the track. */

/* Global values */
scrollbar-color: inherit;
scrollbar-color: initial;
scrollbar-color: revert;
scrollbar-color: revert-layer;
scrollbar-color: unset;
```

### Values

[`<scrollbar-color>`](#scrollbar-color)

:   Defines the color of the scrollbar.

      ------------------- ------------------------------------------------------------------------------------------------------------------------------------
      `auto`              Default platform rendering for the track portion of the scrollbar, in the absence of any other related scrollbar color properties.
      `<color> <color>`   Applies the first color to the scrollbar thumb, the second to the scrollbar track.
      ------------------- ------------------------------------------------------------------------------------------------------------------------------------

**Note:** [`@media (forced-colors: active)`](forced-colors.md) sets
[`scrollbar-color`](scrollbar-color.md) to `auto`.

Accessibility concerns
----------------------

When using `scrollbar-color` property with specific color values,
authors should ensure the specified colors have enough contrast between
them. For keyword values, UAs should ensure the colors they use have
enough contrast. See [Techniques for WCAG 2.0: G183: Using a contrast
ratio of 3:1](https://www.w3.org/TR/WCAG20-TECHS/G183.html).

Formal definition
-----------------

  ---------------------------------- ------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         scrolling boxes
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     by computed value type
  ---------------------------------- ------------------------

Formal syntax
-------------

```
scrollbar-color = 
  auto        |
  <color>  
```

Examples
--------

### Coloring overflow scrollbars

#### CSS

[css]

```css
.scroller {
  width: 300px;
  height: 100px;
  overflow-y: scroll;
  scrollbar-color: #007 #bada55;
}
```

#### HTML

[html]

```html
<div class="scroller">
  Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion
  daikon amaranth tatsoi tomatillo melon azuki bean garlic. Gumbo beet greens
  corn soko endive gumbo gourd. Parsley shallot courgette tatsoi pea sprouts
  fava bean collard greens dandelion okra wakame tomato. Dandelion cucumber
  earthnut pea peanut soko zucchini.
</div>
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------

  [CSS Scrollbars Styling Module Level 1\
  [\#
  scrollbar-color]](https://drafts.csswg.org/css-scrollbars/#scrollbar-color)

  -------------------------------------------------------------------------------------

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

`scrollbar-color`

118

118

64

No

104

No

No

118

64

No

No

No

See also
--------

- [CSS overflow](css_overflow.md) module
- [CSS scrollbars styling](css_scrollbars_styling.md) module
- [`overflow`](overflow.md)
- [`scrollbar-gutter`](scrollbar-gutter.md)
- [`scrollbar-width`](scrollbar-width.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-color>
