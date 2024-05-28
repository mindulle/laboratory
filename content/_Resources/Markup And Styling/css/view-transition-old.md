::view-transition-old
=====================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `::view-transition-old`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-element](pseudo-elements.md) represents the \"old\" view state of a
view transition --- a static screenshot of the old view, before the
transition.

During a view transition, `::view-transition-old` is included in the
associated pseudo-element tree as explained in [The view transition
process](https://developer.mozilla.org/en-US/docs/Web/API/View_Transitions_API#the_view_transition_process),
provided there\'s an \"old\" view state to represent. It is only ever a
child of a
[`::view-transition-image-pair`](::view-transition-image-pair), and
never has any children.

It is a replaced element, and therefore can be manipulated with
properties such as [`object-fit`](object-fit.md) and
[`object-position`](object-position.md). It has natural dimensions equal to
the content\'s size.

The following default styling is included in the UA stylesheet:

[css]

```css
@keyframes -ua-view-transition-fade-out {
  to {
    opacity: 0;
  }
}

html::view-transition-old(*) {
  position: absolute;
  inset-block-start: 0;
  inline-size: 100%;
  block-size: auto;

  animation-name: -ua-view-transition-fade-out;
  animation-duration: inherit;
  animation-fill-mode: inherit;
}
```

**Note:** Additional view transition style sheet styles are also setup
to animate `::view-transition-old`. These are dynamically generated
during the view transition; see the specification [setup transition
pseudo-elements](https://drafts.csswg.org/css-view-transitions-1/#setup-transition-pseudo-elements)
and [update pseudo-element
styles](https://drafts.csswg.org/css-view-transitions-1/#update-pseudo-element-styles)
sections for more details.

Syntax
------

[css]

```css
::view-transition-old(<pt-name-selector>) {
  /* ... */
}
```

`<pt-name-selector>` can be one of the following values:

[`*`](#sect3)

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
figcaption {
  view-transition-name: figure-caption;
}

@keyframes grow-x {
  from {
    transform: scaleX(0);
  }
  to {
    transform: scaleX(1);
  }
}

@keyframes shrink-x {
  from {
    transform: scaleX(1);
  }
  to {
    transform: scaleX(0);
  }
}

::view-transition-old(figure-caption),
::view-transition-new(figure-caption) {
  height: auto;
  right: 0;
  left: auto;
  transform-origin: right center;
}

::view-transition-old(figure-caption) {
  animation: 0.25s linear both shrink-x;
}

::view-transition-new(figure-caption) {
  animation: 0.25s 0.25s linear both grow-x;
}
```

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [CSS View Transitions Module Level 1\
  [\#
  ::view-transition-old]](https://drafts.csswg.org/css-view-transitions/#::view-transition-old)

  -------------------------------------------------------------------------------------------------------

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

`::view-transition-old`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/::view-transition-old>
