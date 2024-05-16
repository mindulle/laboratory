overflow-anchor
===============

The `overflow-anchor`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
provides a way to opt out of the browser\'s scroll anchoring behavior,
which adjusts scroll position to minimize content shifts.

Scroll anchoring behavior is enabled by default in any browser that
supports it. Therefore, changing the value of this property is typically
only required if you are experiencing problems with scroll anchoring in
a document or part of a document and need to turn the behavior off.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
overflow-anchor: auto;
overflow-anchor: none;

/* Global values */
overflow-anchor: inherit;
overflow-anchor: initial;
overflow-anchor: revert;
overflow-anchor: revert-layer;
overflow-anchor: unset;
```

### Values

[`auto`](#auto)

:   The element becomes a potential anchor when adjusting scroll
    position.

[`none`](#none)

:   The element won\'t be selected as a potential anchor.

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
overflow-anchor = 
  auto  |
  none  
```

Examples
--------

### Prevent scroll anchoring

To prevent scroll anchoring in a document, use the `overflow-anchor`
property.

[css]

```css
* {
  overflow-anchor: none;
}
```

Specifications
--------------

  ---------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------

  [CSS Scroll Anchoring Module Level 1\
  [\#
  exclusion-api]](https://drafts.csswg.org/css-scroll-anchoring/#exclusion-api)

  ---------------------------------------------------------------------------------------

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

`overflow-anchor`

56

79

66

No

43

No

56

56

66

43

No

6.0

See also
--------

- [](guide_to_scroll_anchoring.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor>
