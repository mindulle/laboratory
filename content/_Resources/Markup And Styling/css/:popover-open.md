:popover-open
=============

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `:popover-open`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents a
[popover](https://developer.mozilla.org/en-US/docs/Web/API/Popover_API)
element (i.e. one with a [`popover`
attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/popover))
that is in the showing state. You can use this to apply style to popover
elements only when they are shown.

Syntax
------

[css]

```css
:popover-open {
  /* ... */
}
```

Examples
--------

By default, popovers appear in the middle of the viewport. The default
styling is achieved like this in the UA stylesheet:

[css]

```css
[popover] {
  position: fixed;
  inset: 0;
  width: fit-content;
  height: fit-content;
  margin: auto;
  border: solid;
  padding: 0.25em;
  overflow: auto;
  color: CanvasText;
  background-color: Canvas;
}
```

To override the default styles and get the popover to appear somewhere
else on your viewport, you could need to override the above styles with
something like this:

[css]

```css
:popover-open {
  width: 200px;
  height: 100px;
  position: absolute;
  inset: unset;
  bottom: 5px;
  right: 5px;
  margin: 0;
}
```

Specifications
--------------

  --------------------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-popover-open]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-popover-open)

  --------------------------------------------------------------------------------------------------------------------

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

`:popover-open`

114

114

114

No

100

17

114

114

No

No

17

No

See also
--------

- [Popover
    API](https://developer.mozilla.org/en-US/docs/Web/API/Popover_API)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:popover-open>
