text-emphasis-position
======================

The `text-emphasis-position`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
where emphasis marks are drawn. Like ruby text, if there isn\'t enough
room for emphasis marks, the line height is increased.

Try it
------

Syntax
------

[css]

```css
/* Initial value */
text-emphasis-position: over right;

/* Keywords value */
text-emphasis-position: over left;
text-emphasis-position: under right;
text-emphasis-position: under left;

text-emphasis-position: left over;
text-emphasis-position: right under;
text-emphasis-position: left under;

/* Global values */
text-emphasis-position: inherit;
text-emphasis-position: initial;
text-emphasis-position: revert;
text-emphasis-position: revert-layer;
text-emphasis-position: unset;
```

### Values

[`over`](#over)

:   Draws marks over the text in horizontal writing mode.

[`under`](#under)

:   Draws marks under the text in horizontal writing mode.

[`right`](#right)

:   Draws marks to the right of the text in vertical writing mode.

[`left`](#left)

:   Draws marks to the left of the text in vertical writing mode.

Description
-----------

The preferred position of emphasis marks depends on the language. In
Japanese for example, the preferred position is `over right`. In
Chinese, on the other hand, the preferred position is `under right`. The
informative table below summarizes the preferred emphasis mark positions
for Chinese, Mongolian and Japanese:

![](data:image/png;base64,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 "Emphasis (shown in blue for clarity) applied above a fragment of Japanese text")

**Note:** The `text-emphasis-position` cannot be set, and therefore are
not reset either, using the [`text-emphasis`](text-emphasis.md) shorthand
property.

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `over right`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
text-emphasis-position = 
  [ over | under ]   &&
  [ right | left ]?  
```

Examples
--------

### Preferring ruby over emphasis marks

Some editors prefer to hide emphasis marks when they conflict with ruby.
In HTML, this can be done with the following style rule:

[css]

```css
ruby {
  text-emphasis: none;
}
```

### Preferring emphasis marks over ruby

Some other editors prefer to hide ruby when they conflict with emphasis
marks. In HTML, this can be done with the following pattern:

[css]

```css
em {
  text-emphasis: dot; /* Set text-emphasis for <em> elements */
}

em rt {
  display: none; /* Hide ruby inside <em> elements */
}
```

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------------

  [CSS Text Decoration Module Level 3\
  [\#
  text-emphasis-position-property]](https://drafts.csswg.org/css-text-decor/#text-emphasis-position-property)

  ---------------------------------------------------------------------------------------------------------------------

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

`text-emphasis-position`

9925

9979

46

No

8515

77

994.4

9925

46

6814

77

18.01.5

`left_and_right`

62

79

46

No

49

8

62

62

46

46

8

8.0

`over`

99

99

108

No

85

≤13.1

99

99

108

68

≤13.4

18.0

`under`

99

99

108

No

85

≤13.1

99

99

108

68

≤13.4

18.0

See also
--------

- The longhand properties
    [`text-emphasis-style`](text-emphasis-style.md),
    [`text-emphasis-color`](text-emphasis-color.md), and the corresponding
    shorthand property [`text-emphasis`](text-emphasis.md).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-position>
