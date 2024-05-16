text-decoration-skip
====================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `text-decoration-skip`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
what parts of an element\'s content any text decoration affecting the
element must skip over. It controls all text decoration lines drawn by
the element and also any text decoration lines drawn by its ancestors.

**Note:** Most other browsers are converging on supporting the simpler
[`text-decoration-skip-ink`](text-decoration-skip-ink.md) property.

Syntax
------

[css]

```css
/* Keyword values */
text-decoration-skip: none;
text-decoration-skip: objects;
text-decoration-skip: spaces;
text-decoration-skip: edges;
text-decoration-skip: box-decoration;

/* Multiple keywords */
text-decoration-skip: objects spaces;
text-decoration-skip: leading-spaces trailing-spaces;
text-decoration-skip: objects edges box-decoration;

/* Global values */
text-decoration-skip: inherit;
text-decoration-skip: initial;
text-decoration-skip: revert;
text-decoration-skip: revert-layer;
text-decoration-skip: unset;
```

### Values

[`none`](#none)

:   Nothing is skipped. Thus, text decoration is drawn for all text
    content and across atomic inline-level boxes.

[`objects`](#objects)

:   The entire margin box of the element is skipped if it is an atomic
    inline such as an image or inline-block.

[`spaces`](#spaces)

:   All spacing is skipped: all [Unicode white space
    characters](https://www.unicode.org/reports/tr44/#White_Space) and
    all word separators, plus any adjacent
    [`letter-spacing`](letter-spacing.md) or
    [`word-spacing`](word-spacing.md).

[`leading-spaces`](#leading-spaces)

:   The same as `spaces`, except that only leading spaces are skipped.

[`trailing-spaces`](#trailing-spaces)

:   The same as `spaces`, except that only trailing spaces are skipped.

[`edges`](#edges)

:   The start and end of the text decoration is inset slightly (e.g., by
    half of the line thickness) from the content edge of the decorating
    box. Thus, adjacent elements receive separate underlines. (This is
    important in Chinese, where underlining is a form of punctuation.)

    ![An example of \"text-decoration-skip:
    edges;\".](data:image/png;base64,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)

[`box-decoration`](#box-decoration)

:   The text decoration is skipped over the box\'s margin, border, and
    padding areas. This only has an effect on decorations imposed by an
    ancestor; a *decorating box* never draws over its own box
    decoration.

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `objects`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
text-decoration-skip = 
  none  |
  auto  
```

Examples
--------

### Skipping edges

#### HTML

[html]

```html
<p>Hey, grab a cup of <em>coffee!</em></p>
```

#### CSS

[css]

```css
p {
  margin: 0;
  font-size: 3em;
  text-decoration: underline;
  text-decoration-skip: edges;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [CSS Text Decoration Module Level 4\
  [\#
  text-decoration-skipping]](https://drafts.csswg.org/css-text-decor-4/#text-decoration-skipping)

  ---------------------------------------------------------------------------------------------------------

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

`text-decoration-skip`

57--64Only supports the deprecated `ink` value.

No

No

No

44--50Only supports the deprecated `ink` value.

12.1Supports only `none`, `auto`, and `objects` values.

7Supports only `none`, `auto`, and `objects` values.

57--64Only supports the deprecated `ink` value.

57--64Only supports the deprecated `ink` value.

No

43--46Only supports the deprecated `ink` value.

12.2Supports only `none`, `auto`, and `objects` values.

7Supports only `none`, `auto`, and `objects` values.

7.0--9.0Only supports the deprecated `ink` value.

See also
--------

- [`text-decoration-skip-ink`](text-decoration-skip-ink.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-skip>
