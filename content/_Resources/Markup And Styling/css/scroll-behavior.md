scroll-behavior
===============

The `scroll-behavior`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the behavior for a scrolling box when scrolling is triggered by the
navigation or CSSOM scrolling APIs.

Try it
------

Note that any other scrolls, such as those performed by the user, are
not affected by this property. When this property is specified on the
root element, it applies to the viewport instead. This property
specified on the `body` element will *not* propagate to the viewport.

User agents are allowed to ignore this property.

Syntax
------

[css]

```css
/* Keyword values */
scroll-behavior: auto;
scroll-behavior: smooth;

/* Global values */
scroll-behavior: inherit;
scroll-behavior: initial;
scroll-behavior: revert;
scroll-behavior: revert-layer;
scroll-behavior: unset;
```

The `scroll-behavior` property is specified as one of the keyword values
listed below.

### Values

[`auto`](#auto)

:   The scrolling box scrolls instantly.

[`smooth`](#smooth)

:   The scrolling box scrolls in a smooth fashion using a
    user-agent-defined easing function over a user-agent-defined period
    of time. User agents should follow platform conventions, if any.

Formal definition
-----------------

  ---------------------------------- -----------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         scrolling boxes
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- -----------------

Formal syntax
-------------

```
scroll-behavior = 
  auto    |
  smooth  
```

Examples
--------

### Setting smooth scroll behavior

#### HTML

[html]

```html
<nav>
  <a href="#page-1">1</a>
  <a href="#page-2">2</a>
  <a href="#page-3">3</a>
</nav>
<div class="scroll-container">
  <div class="scroll-page" id="page-1">1</div>
  <div class="scroll-page" id="page-2">2</div>
  <div class="scroll-page" id="page-3">3</div>
</div>
```

#### CSS

[css]

```css
a {
  display: inline-block;
  width: 50px;
  text-decoration: none;
}
nav,
.scroll-container {
  display: block;
  margin: 0 auto;
  text-align: center;
}
nav {
  width: 339px;
  padding: 5px;
  border: 1px solid black;
}
.scroll-container {
  width: 350px;
  height: 200px;
  overflow-y: scroll;
  scroll-behavior: smooth;
}
.scroll-page {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  font-size: 5em;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------

  [CSS Overflow Module Level 3\
  [\#
  smooth-scrolling]](https://drafts.csswg.org/css-overflow/#smooth-scrolling)

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

`scroll-behavior`

61

79

36

No

48

15.4

61

61

36

45

15.4

8.0

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior>
