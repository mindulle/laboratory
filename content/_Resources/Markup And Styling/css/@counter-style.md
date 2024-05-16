\@counter-style
===============

The `@counter-style`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[at-rule](at-rule.md) lets you define counter styles that are not part of
the predefined set of styles. A `@counter-style` rule defines how to
convert a counter value into a string representation.

[css]

```css
@counter-style thumbs {
  system: cyclic;
  symbols: "\1F44D";
  suffix: " ";
}

ul {
  list-style: thumbs;
}
```

The initial version of CSS defined a set of useful counter styles.
However, although more styles were added to this set of predefined
styles over the years, this system proved too restrictive to fulfill the
needs of worldwide typography. The `@counter-style` at-rule addresses
this shortcoming in an open-ended manner, by allowing authors to define
their own counter styles when the pre-defined styles aren\'t fitting
their needs.

Syntax
------

### Descriptors

Each `@counter-style` is identified by a name and has a set of
descriptors.

[`system`](system.md)

:   Specifies the algorithm to be used for converting the integer value
    of a counter to a string representation.

[`negative`](negative.md)

:   Lets the author specify symbols to be appended or prepended to the
    counter representation if the value is negative.

[`prefix`](prefix.md)

:   Specifies a symbol that should be prepended to the marker
    representation. Prefixes are added to the representation in the
    final stage, so in the final representation of the counter, it comes
    before the negative sign.

[`suffix`](suffix.md)

:   Specifies, similar to the prefix descriptor, a symbol that is
    appended to the marker representation. Suffixes come after the
    marker representation.

[`range`](range.md)

:   Defines the range of values over which the counter style is
    applicable. If a counter style is used to represent a counter value
    outside of its ranges, the counter style will drop back to its
    fallback style.

[`pad`](pad.md)

:   Is used when you need the marker representations to be of a minimum
    length. For example if you want the counters to start at 01 and go
    through 02, 03, 04, etc., then the pad descriptor is to be used. For
    representations larger than the specified pad value, the marker is
    constructed as normal.

[`fallback`](fallback.md)

:   Specifies a system to fall back into if either the specified system
    is unable to construct the representation of a counter value or if
    the counter value is outside the specified range. If the specified
    fallback also fails to represent the value, then the fallback
    style\'s fallback is used, if one is specified. If there are either
    no fallback systems described or if the chain of fallback systems
    are unable to represent a counter value, then it will ultimately
    fall back to the decimal style.

[`symbols`](symbols.md)

:   Specifies the symbols that are to be used for the marker
    representations. Symbols can contain strings, images, or custom
    identifiers. How the symbols are used to construct the marker
    representation is up to the algorithm specified in the system
    descriptor. For example, if the system specified is fixed, then each
    of the N symbols specified in the descriptor will be used to
    represent the first N counter symbols. Once the specified set of
    symbols have exhausted, the fallback style will be used for the rest
    of the list.

    The below `@counter-style` rule uses images instead of character
    symbols. Image values for symbols is currently an \'at risk\'
    feature, and is not implemented in any browser.

    
    [css]

    ```css
    @counter-style winners-list {
      system: fixed;
      symbols: url(gold-medal.svg) url(silver-medal.svg) url(bronze-medal.svg);
      suffix: " ";
    }
    ```

[`additive-symbols`](additive-symbols.md)

:   While the symbols specified in the symbols descriptor is used for
    constructing marker representation by most algorithms, some systems
    such as \'additive\' rely on *additive tuples* described in this
    descriptor. Each additive tuple consists of a counter symbol and a
    non-negative integer weight. The additive tuples must be specified
    in the descending order of their weights.

[`speak-as`](speak-as.md)

:   Describes how to read out the counter style in speech synthesizers,
    such as screen readers. For example, the value of the marker symbol
    can be read out as numbers or alphabets for ordered lists or as
    audio cues for unordered lists, based on the value of this
    descriptor.

Formal syntax
-------------

```
@counter-style = 
  @counter-style <counter-style-name>   
```

Examples
--------

### Specifying symbols with counter-style

[css]

```css
@counter-style circled-alpha {
  system: fixed;
  symbols: Ⓐ Ⓑ Ⓒ Ⓓ Ⓔ Ⓕ Ⓖ Ⓗ Ⓘ Ⓙ Ⓚ Ⓛ Ⓜ Ⓝ Ⓞ Ⓟ Ⓠ Ⓡ Ⓢ Ⓣ Ⓤ Ⓥ Ⓦ Ⓧ Ⓨ Ⓩ;
  suffix: " ";
}
```

The above counter style rule can be applied to lists like this:

[css]

```css
.items {
  list-style: circled-alpha;
}
```

Which will produce lists like this:

Ⓐ One Ⓑ Two Ⓒ Three Ⓓ Four Ⓔ Five ... Ⓨ Twenty-five Ⓩ Twenty-six 27
Twenty-seven 28 Twenty-eight 29 Twenty-nine 30 Thirty

See more examples on the [demo
page](https://mdn.github.io/css-examples/counter-style-demo/).

### Ready-made counter styles

Find a collection of over 100 `counter-style` code snippets in the
[Ready-made Counter
Styles](https://www.w3.org/TR/predefined-counter-styles/) document. This
document provides counter styles that meet the needs of languages and
cultures around the world.

The [Counter styles converter](https://r12a.github.io/app-counters/)
pulls from this list to test and create copy and paste code for counter
styles.

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [CSS Counter Styles Level 3\
  [\#
  the-counter-style-rule]](https://drafts.csswg.org/css-counter-styles/#the-counter-style-rule)

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

`@counter-style`

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

`additive-symbols`

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

`negative`

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

`pad`

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

`prefix`

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

`range`

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

`speak-as`

No

No

33

No

No

No

No

No

33

No

No

No

`suffix`

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

`symbols`

91Does not support `<image>` as a value for the `symbols` descriptor.

91Does not support `<image>` as a value for the `symbols` descriptor.

33Does not support `<image>` as a value for the `symbols` descriptor.

No

77Does not support `<image>` as a value for the `symbols` descriptor.

17

91Does not support `<image>` as a value for the `symbols` descriptor.

91Does not support `<image>` as a value for the `symbols` descriptor.

33Does not support `<image>` as a value for the `symbols` descriptor.

64Does not support `<image>` as a value for the `symbols` descriptor.

17

16.0Does not support `<image>` as a value for the `symbols` descriptor.

`system`

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

- [`list-style`](list-style.md), [`list-style-image`](list-style-image.md),
    [`list-style-position`](list-style-position.md),
    [`list-style-type`](list-style-type.md)
- [`symbols()`](symbols.md), the functional notation
    creating anonymous counter styles.
- CSS [`counter()`](counter.md) and [`counters()`](counters.md) functions
- [Counter style
    demo](https://mdn.github.io/css-examples/counter-style-demo/)
    ([code](https://github.com/mdn/css-examples/tree/main/counter-style-demo))

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style>
