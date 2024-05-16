user-select
===========

The `user-select`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
controls whether the user can select text. This doesn\'t have any effect
on content loaded as part of a browser\'s user interface (its
[chrome](https://developer.mozilla.org/en-US/docs/Glossary/Chrome)),
except in textboxes.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
user-select: none;
user-select: auto;
user-select: text;
user-select: contain;
user-select: all;

/* Global values */
user-select: inherit;
user-select: initial;
user-select: revert;
user-select: revert-layer;
user-select: unset;
```

**Note:** `user-select` is not an inherited property, though the initial
`auto` value makes it behave like it is inherited most of the time.
WebKit/Chromium-based browsers *do* implement the property as inherited,
which violates the behavior described in the spec, and this will bring
some issues. Until now, Chromium has chosen to [fix the
issues](https://chromium.googlesource.com/chromium/src/+/b01af0b296ecb855aac95c4ed335d188e6eac2de)
to make the final behavior meet the specifications.

### Values

[`none`](#none)

:   The text of the element and its sub-elements is not selectable. Note
    that the
    [`Selection`](https://developer.mozilla.org/en-US/docs/Web/API/Selection)
    object can contain these elements.

[`auto`](#auto)

:   The used value of `auto` is determined as follows:

    -   On the `::before` and `::after` pseudo elements, the used value
        is `none`
    -   If the element is an editable element, the used value is
        `contain`
    -   Otherwise, if the used value of `user-select` on the parent of
        this element is `all`, the used value is `all`
    -   Otherwise, if the used value of `user-select` on the parent of
        this element is `none`, the used value is `none`
    -   Otherwise, the used value is `text`

[`text`](#text)

:   The text can be selected by the user.

[`all`](#all)

:   The content of the element shall be selected atomically: If a
    selection would contain part of the element, then the selection must
    contain the entire element including all its descendants. If a
    double-click or context-click occurred in sub-elements, the highest
    ancestor with this value will be selected.

[`contain`](#contain)

:   Enables selection to start within the element; however, the
    selection will be contained by the bounds of that element.

    **Note:** CSS UI 4
    [renamed](https://github.com/w3c/csswg-drafts/commit/3f1d9db96fad8d9fc787d3ed66e2d5ad8cfadd05)
    the `element` value to `contain`.

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
user-select = 
  auto     |
  text     |
  none     |
  contain  |
  all      
```

Examples
--------

### HTML

[html]

```html
<p>You should be able to select this text.</p>
<p class="unselectable">Hey, you can't select this text!</p>
<p class="all">Clicking once will select all of this text.</p>
```

### CSS

[css]

```css
.unselectable {
  -webkit-user-select: none; /* Safari */
  user-select: none;
}

.all {
  -webkit-user-select: all;
  user-select: all;
}
```

### Result

Specifications
--------------

  ---------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------

  [CSS Basic User Interface Module Level 4\
  [\#
  content-selection]](https://drafts.csswg.org/css-ui/#content-selection)

  ---------------------------------------------------------------------------------

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

`user-select`

541

791212--79

69491

10

4115

32--3

54≤37

5418

79494

4114

3

6.01.0

`all`

53

79

1

No

40

16

53

53

4

41

16

6.0

`auto`

1

12

1

10

15

2

≤37

18

4

14

3

1.0

`contain`

No

12--79

No

10

No

No

No

No

No

No

No

No

`none`

1

12

211--65

10

15

2

≤37

18

214--65

14

3

1.0

`text`

1

12

1

10

15

2Allows typing in the `<html>` container.

≤37

18

4

14

3Allows typing in the `<html>` container.

1.0

See also
--------

- [Polyfill for
    `user-select: contain`](https://github.com/github/user-select-contain-polyfill)
- [`::selection`](::selection) pseudo-element
- The JavaScript
    [`Selection`](https://developer.mozilla.org/en-US/docs/Web/API/Selection)
    object

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/user-select>
