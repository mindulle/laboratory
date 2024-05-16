counter-increment
=================

The `counter-increment`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
increases or decreases the value of a [](using_css_counters.md) by a given value.

Try it
------

**Note:** The counter\'s value can be reset to an arbitrary number using
the [`counter-reset`](counter-reset.md) CSS property.

Syntax
------

[css]

```css
/* Increment "my-counter" by 1 */
counter-increment: my-counter;

/* Decrement "my-counter" by 1 */
counter-increment: my-counter -1;

/* Increment "counter1" by 1, and decrement "counter2" by 4 */
counter-increment: counter1 counter2 -4;

/* Do not increment/decrement anything: used to override less specific rules */
counter-increment: none;

/* Global values */
counter-increment: inherit;
counter-increment: initial;
counter-increment: revert;
counter-increment: revert-layer;
counter-increment: unset;
```

The `counter-increment` property is specified as either one of the
following:

- A `<custom-ident>` naming the counter, followed optionally by an
    `<integer>`. You may specify as many counters to increment as you
    want, with each name or name-number pair separated by a space.
- The keyword value `none`.

### Values

[`<custom-ident>`](custom-ident.md)

:   The name of the counter to increment.

[`<integer>`](integer.md)

:   The value to add to the counter. Defaults to `1` if not specified.

[`none`](#none)

:   No counter must be incremented. This is used as the default value,
    or to cancel an increment in more specific rules.

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
counter-increment = 
  [ <counter-name> <integer>? ]+  |
  none                            
```

Examples
--------

### Incrementing named counters

[css]

```css
h1 {
  counter-increment: chapter section 2 page;
  /* Increases the value of the chapter and page counters by 1,
     and the section counter by 2 */
}
```

Specifications
--------------

  ----------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------

  [CSS Lists and Counters Module Level 3\
  [\#
  increment-set]](https://drafts.csswg.org/css-lists/#increment-set)

  ----------------------------------------------------------------------------

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

`counter-increment`

2

12

1

8

9.2

3

4.4

18

25

10.1

1

1.0

See also
--------

- [Using CSS Counters](using_css_counters.md)
- [`counter-reset`](counter-reset.md)
- [`counter-set`](counter-set.md)
- [`@counter-style`](@counter-style.md)
- The [`counter()`](counter.md) and [`counters()`](counters.md) functions

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/counter-increment>
