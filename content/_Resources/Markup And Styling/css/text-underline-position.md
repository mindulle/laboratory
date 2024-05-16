text-underline-position
=======================

The `text-underline-position`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies the position of the underline which is set using the
[`text-decoration`](text-decoration.md) property\'s `underline` value.

Try it
------

Syntax
------

[css]

```css
/* Single keyword */
text-underline-position: auto;
text-underline-position: under;
text-underline-position: left;
text-underline-position: right;

/* Multiple keywords */
text-underline-position: under left;
text-underline-position: right under;

/* Global values */
text-underline-position: inherit;
text-underline-position: initial;
text-underline-position: revert;
text-underline-position: revert-layer;
text-underline-position: unset;
```

### Values

[`auto`](#auto)

:   The [user
    agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
    uses its own algorithm to place the line at or under the alphabetic
    baseline.

[`from-font`](#from-font)

:   If the font file includes information about a preferred position,
    use that value. If the font file doesn\'t include this information,
    behave as if `auto` was set, with the browser choosing an
    appropriate position.

[`under`](#under)

:   Forces the line to be set below the alphabetic baseline, at a
    position where it won\'t cross any descenders. This is useful for
    ensuring legibility with chemical and mathematical formulas, which
    make a large use of subscripts.

[`left`](#left)

:   In vertical writing-modes, this keyword forces the line to be placed
    on the *left* side of the text. In horizontal writing-modes, it is a
    synonym of `under`.

[`right`](#right)

:   In vertical writing-modes, this keyword forces the line to be placed
    on the *right* side of the text. In horizontal writing-modes, it is
    a synonym of `under`.

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
text-underline-position = 
  auto                           |
  [ under || [ left | right ] ]  
```

Examples
--------

### A simple example

Let\'s take a couple of simple example paragraphs:

[html]

```html
<p class="horizontal">
  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam consectetur ac
  turpis vel laoreet. Nullam volutpat pharetra lorem, sit amet feugiat tortor
  volutpat quis. Nam eget sodales quam. Aliquam accumsan tellus ac erat posuere.
</p>

<p class="vertical">
  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam consectetur ac
  turpis vel laoreet. Nullam volutpat pharetra lorem, sit amet feugiat tortor
  volutpat quis. Nam eget sodales quam. Aliquam accumsan tellus ac erat posuere.
</p>
```

Our CSS looks like this:

[css]

```css
p {
  font-size: 1.5rem;
  text-transform: capitalize;
  text-decoration: underline;
  text-decoration-thickness: 2px;
}

.horizontal {
  text-underline-position: under;
}

.vertical {
  writing-mode: vertical-rl;
  text-underline-position: left;
}
```

In this example we set both the paragraphs to have a thick underline. In
the horizontal text we use `text-underline-position: under;` to put the
underline below all the descenders.

In the text with a vertical [`writing-mode`](writing-mode.md) set, we can
then use values of `left` or `right` to make the underline appear on the
left or right of the text as required.

The live example looks like this:

### Setting text-underline-position globally

Because the `text-underline-position` property inherits and is not reset
by the [`text-decoration`](text-decoration.md) shorthand property, it may
be appropriate to set its value at a global level. For example, the
`under` value may be appropriate for a document with lots of chemical
and mathematical formulas, which make a large use of subscripts.

[css]

```css
:root {
  text-underline-position: under;
}
```

Specifications
--------------

  -----------------------------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------------------------

  [CSS Text Decoration Module Level 3\
  [\#
  text-underline-position-property]](https://drafts.csswg.org/css-text-decor/#text-underline-position-property)

  -----------------------------------------------------------------------------------------------------------------------

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

`text-underline-position`

33

12

74

6

20

12.19

4.4.3

33

79

20

12.29

2.0

`from-font`

87

87

74

No

73

12.1

87

87

79

62

12.2

14.0

`left_right`

71

79

74

No

58

No

71

71

79

50

No

10.0

`under`

33

79

74

No

20

12.1

4.4.3

33

79

20

12.2

2.0

See also
--------

- The [`text-decoration`](text-decoration.md) property is a shorthand for
    setting most text-decoration properties, including
    [`text-decoration-line`](text-decoration-line.md),
    [`text-decoration-color`](text-decoration-color.md), and
    [`text-decoration-style`](text-decoration-style.md). However, it does
    not set `text-underline-position`.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-underline-position>
