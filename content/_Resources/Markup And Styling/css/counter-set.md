counter-set
===========

The `counter-set`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets a
[CSS counter](using_css_counters.md) to a given value.
It manipulates the value of existing counters, and will only create new
counters if there isn\'t already a counter of the given name on the
element.

Try it
------

**Note:** The counter\'s value can be incremented or decremented using
the [`counter-increment`](counter-increment.md) CSS property.

Syntax
------

[css]

```css
/* Set "my-counter" to 0 */
counter-set: my-counter;

/* Set "my-counter" to -1 */
counter-set: my-counter -1;

/* Set "counter1" to 1, and "counter2" to 4 */
counter-set: counter1 1 counter2 4;

/* Cancel any counter that could have been set in less specific rules */
counter-set: none;

/* Global values */
counter-set: inherit;
counter-set: initial;
counter-set: revert;
counter-set: revert-layer;
counter-set: unset;
```

The `counter-set` property is specified as either one of the following:

- A `<custom-ident>` naming the counter, followed optionally by an
    `<integer>`. You may specify as many counters to reset as you want,
    with each name or name-number pair separated by a space.
- The keyword value `none`.

### Values

[`<custom-ident>`](custom-ident.md)

:   The name of the counter to set.

[`<integer>`](integer.md)

:   The value to set the counter to on each occurrence of the element.
    Defaults to `0` if not specified. If there isn\'t currently a
    counter of the given name on the element, the element will create a
    new counter of the given name with a starting value of 0 (though it
    may then immediately set or increment that value to something
    different).

[`none`](#none)

:   No counter set is to be performed. This can be used to override a
    `counter-set` defined in a less specific rule.

Formal definition
-----------------

  ---------------------------------- ------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     by computed value type
  ---------------------------------- ------------------------

Formal syntax
-------------

```
counter-set = 
  [ <counter-name> <integer>? ]+  |
  none                            
```

Examples
--------

### Setting named counters

[css]

```css
h1 {
  counter-set: chapter section 1 page;
  /* Sets the chapter and page counters to 0,
     and the section counter to 1 */
}
```

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [CSS Lists and Counters Module Level 3\
  [\#
  propdef-counter-set]](https://drafts.csswg.org/css-lists/#propdef-counter-set)

  ----------------------------------------------------------------------------------------

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

`counter-set`

85

85

68

No

71

No

85

85

68

60

No

14.0

See also
--------

- [Using CSS Counters](using_css_counters.md)
- [`counter-increment`](counter-increment.md)
- [`counter-reset`](counter-reset.md)
- [`@counter-style`](@counter-style.md)
- [`counter()`](counter.md) and [`counters()`](counters.md) functions
- [`content`](content.md) property

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/counter-set>
