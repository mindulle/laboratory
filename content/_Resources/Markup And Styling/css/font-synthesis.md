font-synthesis
==============

The `font-synthesis` [shorthand](shorthand_properties.md)
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property lets
you specify whether or not the browser may synthesize the bold, italic,
small-caps, and/or subscript and superscript typefaces when they are
missing in the specified font-family.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [font-synthesis-weight](font-synthesis-weight.md)
- [font-synthesis-style](font-synthesis-style.md)
- [font-synthesis-small-caps](font-synthesis-small-caps.md)
- [font-synthesis-position](font-synthesis-position.md)

Syntax
------

[css]

```css
/* none or one or more of the other keyword values */
font-synthesis: none;
font-synthesis: weight;
font-synthesis: style;
font-synthesis: position;
font-synthesis: small-caps style; /* property values can be in any order */
font-synthesis: style small-caps weight position; /* property values can be in any order */

/* Global values */
font-synthesis: inherit;
font-synthesis: initial;
font-synthesis: revert;
font-synthesis: revert-layer;
font-synthesis: unset;
```

### Values

[`none`](#none)

:   Indicates that no bold, italic, or small-caps typeface may be
    synthesized by the browser.

[`weight`](#weight)

:   Indicates that the missing bold typeface may be synthesized by the
    browser if needed.

[`style`](#style)

:   Indicates that the italic typeface may be synthesized by the browser
    if needed.

[`small-caps`](#small-caps)

:   Indicates that the small-caps typeface may be synthesized by the
    browser if needed.

[`position`](#position)

:   Indicates that the subscript and superscript typeface may be
    synthesized by the browser, if needed, when using
    [`font-variant-position`](font-variant-position.md).

Description
-----------

Most standard Western fonts include italic and bold variants, and some
fonts include a small-caps and subscript/superscript variants. However,
many fonts do not. Fonts used for Chinese, Japanese, Korean and other
logographic scripts tend not to include these variants and synthesizing
them might impede the legibility or change the meaning of the text. In
these cases, it may be desirable to switch off the browser\'s default
font-synthesis.

For example, using the [:lang()](:lang) pseudo-class, you can disable
the browser from synthesizing bold and oblique characters for a
language, in this case Arabic:

[css]

```css
*:lang(ar) {
  font-synthesis: none;
}
```

The table below shows how a value of the shorthand `font-synthesis`
property maps to the constituent longhand properties.

  font-synthesis value                 [font-synthesis-weight](font-synthesis-weight.md) value   [font-synthesis-style](font-synthesis-style.md) value   [font-synthesis-small-caps](font-synthesis-small-caps.md) value   [font-synthesis-position](font-synthesis-position.md) value
  ------------------------------------ ------------------------------------------------------ ---------------------------------------------------- -------------------------------------------------------------- ----------------------------------------------------------
  `none`                               `none`                                                 `none`                                               `none`                                                         `none`
  `weight`                             `auto`                                                 `none`                                               `none`                                                         `none`
  `style`                              `none`                                                 `auto`                                               `none`                                                         `none`
  `small-caps`                         `none`                                                 `none`                                               `auto`                                                         `none`
  `position`                           `none`                                                 `none`                                               `none`                                                         `auto`
  `weight style`                       `auto`                                                 `auto`                                               `none`                                                         `none`
  `weight small-caps`                  `auto`                                                 `none`                                               `auto`                                                         `none`
  `weight position`                    `auto`                                                 `none`                                               `none`                                                         `auto`
  `style small-caps`                   `none`                                                 `auto`                                               `auto`                                                         `none`
  `style position`                     `none`                                                 `auto`                                               `none`                                                         `auto`
  `weight style small-caps`            `auto`                                                 `auto`                                               `auto`                                                         `none`
  `weight style position`              `auto`                                                 `auto`                                               `none`                                                         `auto`
  `weight small-caps position`         `auto`                                                 `none`                                               `auto`                                                         `auto`
  `style small-caps position`          `none`                                                 `auto`                                               `auto`                                                         `auto`
  `weight style small-caps position`   `auto`                                                 `auto`                                               `auto`                                                         `auto`

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `weight style small-caps`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
font-synthesis = 
  none                               |
  [ weight || style || small-caps ]  
```

Examples
--------

### Disabling font synthesis

This example shows the browser\'s default font-synthesis behavior and
compares it with when the synthesis behavior is turned off. Notice that
the example uses two imported fonts to demonstrate this behavior. You
might not be able to replicate turning off of font-synthesis on fonts
available on your operating system by default.

#### HTML

[html]

```html
<pre> DEFAULT </pre>
<p class="english">
  This font supports <strong>bold</strong> and <em>italic</em>.
</p>
<p class="chinese">这个字体支持<strong>加粗</strong>和<em>斜体</em></p>
<br />

<pre> SYNTHESIS IS DISABLED </pre>
<p class="english no-syn">
  This font supports <strong>bold</strong> and <em>italic.</em>
</p>
<p class="chinese no-syn">这个字体支持<strong>加粗</strong>和<em>斜体</em></p>
<br />

<pre> SYNTHESIS IS ENABLED </pre>
<p class="english">
  This font supports <strong>bold</strong> and <em>italic</em>.
</p>
<p class="chinese syn">这个字体支持<strong>加粗</strong>和<em>斜体</em></p>
```

#### CSS

[css]

```css
@import url("https://fonts.googleapis.com/css2?family=Montserrat&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Ma+Shan+Zheng&display=swap");

.english {
  font-family: "Montserrat", sans-serif;
}
.chinese {
  font-family: "Ma Shan Zheng";
}
.no-syn {
  font-synthesis: none;
}
.syn {
  font-synthesis: style weight;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-synthesis]](https://drafts.csswg.org/css-fonts/#font-synthesis)

  ------------------------------------------------------------------------------

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

`font-synthesis`

97

97

34

No

83

9

97

97

34

68

9

18.0

`position`

No

No

118

No

No

No

No

No

118

No

No

No

`small-caps`

97

97

93

No

83

10.1

97

97

93

68

10.3

18.0

`style`

97

97

111

No

83

10.1

97

97

111

68

10.3

18.0

`weight`

97

97

111

No

83

10.1

97

97

111

68

10.3

18.0

See also
--------

- [`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md)
- [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md)
- [`font-variant-caps`](font-variant-caps.md)
- [`font-variant-position`](font-variant-position.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis>
