::view-transition-image-pair
============================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `::view-transition-image-pair`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-element](pseudo-elements.md) represents a container for a [view
transition\'s](https://developer.mozilla.org/en-US/docs/Web/API/View_Transitions_API)
\"old\" and \"new\" view states --- before and after the transition.

During a view transition, `::view-transition-image-pair` is included in
the associated pseudo-element tree as explained in [The view transition
process](https://developer.mozilla.org/en-US/docs/Web/API/View_Transitions_API#the_view_transition_process).
It is only ever a child of a
[`::view-transition-group`](::view-transition-group). In terms of
children, it can have a [`::view-transition-new`](::view-transition-new)
or a [`::view-transition-old`](::view-transition-old), or both.

`::view-transition-image-pair` is given the following default styling in
the UA stylesheet:

[css]

```css
html::view-transition-image-pair(*) {
  position: absolute;
  inset: 0;

  animation-duration: inherit;
  animation-fill-mode: inherit;
}
```

During a view transition, `::view-transition-image-pair` has
[`isolation: isolate`](isolation.md) set on it in the view transition style
sheet so that its children can be blended with non-normal blend modes
without affecting other visual outputs.

Syntax
------

[css]

```css
::view-transition-image-pair(<pt-name-selector>) {
  /* ... */
}
```

`<pt-name-selector>` can be one of the following values:

[`*`](#sect2)

:   Causes the pseudo-element to match all view transition groups.

[`root`](#root)

:   Causes the pseudo-element to match the default `root` view
    transition group created by the user agent to contain the view
    transition for the overall page, meaning any element not assigned to
    its own specific view transition group via the
    [`view-transition-name`](view-transition-name.md) property.

[`<custom-ident>`](custom-ident.md)

:   Causes the pseudo-element to match a specific view transition group
    created by assigning the given [`<custom-ident>`](custom-ident.md) to
    an element via the [`view-transition-name`](view-transition-name.md)
    property.

Examples
--------

[css]

```css
::view-transition-image-pair(root) {
  isolation: auto;
}
```

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------------

  [CSS View Transitions Module Level 1\
  [\#
  ::view-transition-image-pair]](https://drafts.csswg.org/css-view-transitions/#::view-transition-image-pair)

  ---------------------------------------------------------------------------------------------------------------------

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

`::view-transition-image-pair`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/::view-transition-image-pair>
