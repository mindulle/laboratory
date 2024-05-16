fallback
========

The `fallback` descriptor can be used to specify a counter style to fall
back to if the current counter style cannot create a marker
representation for a particular counter value.

Syntax
------

[css]

```css
/* Keyword values */
fallback: lower-alpha;
fallback: custom-gangnam-style;
```

Description
-----------

If the specified fallback style is also unable to construct a
representation, then its fallback style will be used. If a valid
fallback style is not specified, it defaults to `decimal`.

A couple of scenarios where a fallback style will be used are:

- When the [`range`](range.md) descriptor is specified for a counter
    style, the fallback style will be used to represent values that fall
    outside the range.
- When the `fixed` [`system`](system.md) is used and there are not enough
    symbols to cover all the list items, the fallback style will be used
    for the rest of the list items.

Formal definition
-----------------

  ------------------------------------- ---------------------------------------
  Related [at-rule](at-rule.md)         [`@counter-style`](@counter-style.md)
  [Initial value](initial_value.md)     `decimal`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- ---------------------------------------

Formal syntax
-------------

```
fallback = 
  <counter-style-name>  
```

Examples
--------

### Specifying a fallback counter style

#### HTML

[html]

```html
<ul class="list">
  <li>One</li>
  <li>Two</li>
  <li>Three</li>
  <li>Four</li>
  <li>Five</li>
</ul>
```

#### CSS

[css]

```css
@counter-style fallback-example {
  system: fixed;
  symbols: "\24B6" "\24B7" "\24B8";
  fallback: upper-alpha;
}

.list {
  list-style: fallback-example;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [CSS Counter Styles Level 3\
  [\#
  counter-style-fallback]](https://drafts.csswg.org/css-counter-styles/#counter-style-fallback)

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

`fallback`

91

91

33

No

77

17

91

91

33

64

17

16.0

See also
--------

- [`list-style`](list-style.md),
    [`list-style-image`](list-style-image.md),
    [`list-style-position`](list-style-position.md)
- [`symbols()`](symbols.md): the functional notation creating anonymous
    counter styles

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/fallback>
