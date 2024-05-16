text-decoration-skip-ink
========================

The `text-decoration-skip-ink`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies how overlines and underlines are drawn when they pass over
glyph ascenders and descenders.

Try it
------

`text-decoration-skip-ink` is not part of the
[`text-decoration`](text-decoration.md) shorthand.

Syntax
------

[css]

```css
/* Single keyword */
text-decoration-skip-ink: none;
text-decoration-skip-ink: auto;
text-decoration-skip-ink: all;

/* Global keywords */
text-decoration-skip-ink: inherit;
text-decoration-skip-ink: initial;
text-decoration-skip-ink: revert;
text-decoration-skip-ink: revert-layer;
text-decoration-skip-ink: unset;
```

### Values

[`none`](#none)

:   Underlines and overlines are drawn across the full length of the
    text content, including parts that cross over glyph descenders and
    ascenders.

[`auto`](#auto)

:   The default --- the browser *may* interrupt underlines and overlines
    so that they do not touch or closely approach a glyph. That is, they
    are interrupted where they would otherwise cross over a glyph.

[`all`](#all)

:   The browser *must* interrupt underlines and overlines so that they
    do not touch or closely approach a glyph. This can be helpful with
    certain Chinese, Japanese, or Korean (CJK) fonts, where the `auto`
    behavior might not create interruptions.

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
text-decoration-skip-ink = 
  auto  |
  none  |
  all   
```

Examples
--------

### HTML

[html]

```html
<p>You should go on a quest for a cup of coffee.</p>
<p class="no-skip-ink">Or maybe you'd prefer some tea?</p>
<p>この文は、 text-decoration-skip-ink: auto の使用例を示しています。</p>
<p class="skip-ink-all">
  この文は、 text-decoration-skip-ink: all の使用例を示しています。
</p>
```

### CSS

[css]

```css
p {
  font-size: 1.5em;
  text-decoration: underline blue;
  text-decoration-skip-ink: auto; /* this is the default anyway */
}

.no-skip-ink {
  text-decoration-skip-ink: none;
}

.skip-ink-all {
  text-decoration-skip-ink: all;
}
```

### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------------------

  [CSS Text Decoration Module Level 4\
  [\#
  text-decoration-skip-ink-property]](https://drafts.csswg.org/css-text-decor-4/#text-decoration-skip-ink-property)

  ---------------------------------------------------------------------------------------------------------------------------

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

`text-decoration-skip-ink`

64

79

70

No

50

15.4

64

64

79

46

15.4

9.0

`all`

No

No

75

No

No

15.4

No

No

79

No

15.4

No

See also
--------

- [`text-decoration`](text-decoration.md)
- [`text-decoration-skip`](text-decoration-skip.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-skip-ink>
