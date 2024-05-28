::view-transition
=================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `::view-transition`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-element](pseudo-elements.md) represents the root of the [view
transitions](https://developer.mozilla.org/en-US/docs/Web/API/View_Transitions_API)
overlay, which contains all view transitions and sits over the top of
all other page content.

During a view transition, `::view-transition` is included in the
associated pseudo-element tree as explained in [The view transition
process](https://developer.mozilla.org/en-US/docs/Web/API/View_Transitions_API#the_view_transition_process).
It is the top-level node of this tree, and has one or more
[`::view-transition-group`](::view-transition-group)s as children.

`::view-transition` is given the following default styling in the UA
stylesheet:

[css]

```css
html::view-transition {
  position: fixed;
  inset: 0;
}
```

All [`::view-transition-group`](::view-transition-group) pseudo-elements
are positioned relative to the view transition root.

Syntax
------

[css]

```css
::view-transition {
  /* ... */
}
```

Examples
--------

[css]

```css
::view-transition {
  background-color: rgba(0, 0, 0, 0.25);
}
```

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------------

  [CSS View Transitions Module Level 1\
  [\#
  selectordef-view-transition]](https://drafts.csswg.org/css-view-transitions/#selectordef-view-transition)

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

`::view-transition`

111

111

No

No

97

No

111

111

No

No

No

22.0

See also
--------

- [View Transitions
    API](https://developer.mozilla.org/en-US/docs/Web/API/View_Transitions_API)
- [Smooth and simple transitions with the View Transitions
    API](https://developer.chrome.com/docs/web-platform/view-transitions/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/::view-transition>
