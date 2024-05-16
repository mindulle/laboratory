view-transition-name
====================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `view-transition-name`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
provides the selected element with a distinct identifying name (a
[`<custom-ident>`](custom-ident.md)) and causes it to participate in a
separate [view
transition](https://developer.mozilla.org/en-US/docs/Web/API/View_Transitions_API)
from the root view transition --- or no view transition if the `none`
value is specified.

Syntax
------

[css]

```css
/* <custom-ident> value examples */
view-transition-name: header;
view-transition-name: figure-caption;

/* Keyword value */
view-transition-name: none;
```

### Values

[`<custom-ident>`](custom-ident.md)

:   A distinct identifying name that causes the selected element to
    participate in a separate [view
    transition](https://developer.mozilla.org/en-US/docs/Web/API/View_Transitions_API)
    from the root view transition. The identifier must be unique. If two
    rendered elements have the same `view-transition-name` at the same
    time,
    [`ViewTransition.ready`](https://developer.mozilla.org/en-US/docs/Web/API/ViewTransition/ready)
    will reject and the transition will be skipped.

[`none`](#none)

:   The selected element will not participate in a view transition.

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
view-transition-name = 
  none            |
  <custom-ident>  
```

Examples
--------

[css]

```css
figcaption {
  view-transition-name: figure-caption;
}
```

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------

  [CSS View Transitions Module Level 1\
  [\#
  view-transition-name-prop]](https://drafts.csswg.org/css-view-transitions/#view-transition-name-prop)

  ---------------------------------------------------------------------------------------------------------------

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

`view-transition-name`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/view-transition-name>
