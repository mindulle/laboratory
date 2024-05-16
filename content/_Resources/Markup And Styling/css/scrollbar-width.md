scrollbar-width
===============

The `scrollbar-width` property allows the author to set the maximum
thickness of an element\'s scrollbars when they are shown.

Syntax
------

[css]

```css
/* Keyword values */
scrollbar-width: auto;
scrollbar-width: thin;
scrollbar-width: none;

/* Global values */
scrollbar-width: inherit;
scrollbar-width: initial;
scrollbar-width: revert;
scrollbar-width: revert-layer;
scrollbar-width: unset;
```

### Values

[`<scrollbar-width>`](#scrollbar-width)

:   Defines the width of the scrollbar as a keyword. It must be one of
    the following values:

      -------- -----------------------------------------------------------------------------------------------------------------------------------------
      `auto`   The default scrollbar width for the platform.
      `thin`   A thin scrollbar width variant on platforms that provide that option, or a thinner scrollbar than the default platform scrollbar width.
      `none`   No scrollbar shown, however the element will still be scrollable.
      -------- -----------------------------------------------------------------------------------------------------------------------------------------

**Note:** User Agents must apply any `scrollbar-width` value set on the
root element to the viewport.

Accessibility concerns
----------------------

Use this property with caution --- setting `scrollbar-width` to `thin`
or `none` can make content hard or impossible to scroll if the author
does not provide an alternative scrolling mechanism. While swiping
gestures or mouse wheels can enable scrolling on such content, some
devices have no scroll alternative.

WCAG criterion 2.1.1 (Keyboard) has been in place for a long time to
advise on basic keyboard accessibility, and this should include
scrolling of content areas. And introduced in WCAG 2.1, criterion 2.5.5
(Target Size) advises that touch targets should be at least 44px in
width and height (although the problem is compounded on high-resolution
screens; thorough testing is advised).

- [MDN Understanding WCAG, Guideline 2.1
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#guideline_2.1_%E2%80%94_keyboard_accessible_make_all_functionality_available_from_a_keyboard)
- [MDN Understanding WCAG, Guideline 2.5
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#guideline_2.5_input_modalities_make_it_easier_for_users_to_operate_functionality_through_various_inputs_beyond_keyboard)
- [Understanding Success Criterion 2.1.1 \| W3C Understanding WCAG
    2.1](https://www.w3.org/WAI/WCAG21/Understanding/keyboard)
- [Understanding Success Criterion 2.5.5 \| W3C Understanding WCAG
    2.1](https://www.w3.org/WAI/WCAG21/Understanding/target-size.html)

Formal definition
-----------------

  ---------------------------------- ------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         scrolling boxes
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     by computed value type
  ---------------------------------- ------------------------

Formal syntax
-------------

```
scrollbar-width = 
  auto  |
  thin  |
  none  
```

Examples
--------

### Sizing overflow scrollbars

#### CSS

[css]

```css
.scroller {
  width: 300px;
  height: 100px;
  overflow-y: scroll;
  scrollbar-width: thin;
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
  scrollbar-width]](https://drafts.csswg.org/css-scrollbars/#scrollbar-width)

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

`scrollbar-width`

115

115

64

No

101

No

No

115

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
- [`scrollbar-color`](scrollbar-color.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-width>
