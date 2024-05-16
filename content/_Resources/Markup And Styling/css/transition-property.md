transition-property
===================

The `transition-property`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the CSS properties to which a [](using_css_transitions.md) should be applied.

Try it
------

If you specify a shorthand property (e.g., [`background`](background.md)),
all of its longhand sub-properties that can be animated will be.

Syntax
------

[css]

```css
/* Keyword values */
transition-property: none;
transition-property: all;

/* <custom-ident> values */
transition-property: test_05;
transition-property: -specific;
transition-property: sliding-vertically;

/* Multiple values */
transition-property: test1, animation4;
transition-property: all, height, color;
transition-property:
  all,
  -moz-specific,
  sliding;

/* Global values */
transition-property: inherit;
transition-property: initial;
transition-property: revert;
transition-property: revert-layer;
transition-property: unset;
```

### Values

[`none`](#none)

:   No properties will transition.

[`all`](#all)

:   All properties that can transition will.

[`<custom-ident>`](custom-ident.md)

:   A string identifying the property to which a transition effect
    should be applied when its value changes.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     all
  Applies to                         all elements, [`::before`](::before) and [`::after`](::after) [pseudo-elements](pseudo-elements.md)
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- --------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
transition-property = 
  none                           |
  <single-transition-property>#  

<single-transition-property> = 
  all             |
  <custom-ident>  
```

Examples
--------

### Simple example

This example performs a four-second font size transition when the user
hovers over the element, the `transition-property` is the `font-size`.

#### HTML

[html]

```html
<a class="target">Hover over me</a>
```

#### CSS

[css]

```css
.target {
  font-size: 14px;
  transition-property: font-size;
  transition-duration: 4s;
}

.target:hover {
  font-size: 36px;
}
```

You will find more examples of `transition-property` included in the
main [CSS transitions](using_css_transitions.md) article.

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------------

  [CSS Transitions\
  [\#
  transition-property-property]](https://drafts.csswg.org/css-transitions/#transition-property-property)

  ----------------------------------------------------------------------------------------------------------------

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

`IDENT_value`

1

12

16

10

15

4

≤37

18

16

14

3

1.0

`transition-property`

261

1212

49164

1010

1512.111.6--15

93.1

≤374.4

2618

49164

1412.112--14

92

1.51.0

See also
--------

- [Using CSS transitions](using_css_transitions.md)
- [`transition`](transition.md)
- [`transition-duration`](transition-duration.md)
- [`transition-timing-function`](transition-timing-function.md)
- [`transition-delay`](transition-delay.md)
- [`TransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property>
