font-variant-emoji
==================

The `font-variant-emoji`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies the default presentation style for displaying emojis.

Traditionally, this was done by appending a *Variation Selector*,
`U+FE0E` for text and `U+FE0F` for emoji, to the emoji code point. Only
emojis listed as contributing to a [Unicode emoji presentation
sequence](https://www.unicode.org/emoji/charts/emoji-variants.html) are
affected by this property.

Syntax
------

[css]

```css
/* Keyword values */
font-variant-emoji: normal;
font-variant-emoji: text;
font-variant-emoji: emoji;
font-variant-emoji: unicode;

/* Global values */
font-variant-emoji: inherit;
font-variant-emoji: initial;
font-variant-emoji: revert;
font-variant-emoji: revert-layer;
font-variant-emoji: unset;
```

The `font-variant-emoji` property is specified using a single keyword
value from the list below.

### Values

[`normal`](#normal)

:   Allows a browser to choose how to display the emoji. This often
    follows the operating system setting.

[`text`](#text)

:   Renders the emoji as if it were using the unicode text variation
    selector (`U+FE0E`).

[`emoji`](#emoji)

:   Renders the emoji as if it were using the unicode emoji variation
    selector (`U+FE0F`).

[`unicode`](#unicode)

:   Renders the emoji in accordance with the [Emoji presentation
    properties](https://www.unicode.org/reports/tr51/tr51-23.html#Emoji_Presentation).
    If the `U+FE0E` or `U+FE0F` variation selector is present, then it
    will override this value setting.

Formal definition
-----------------

  ---------------------------------- ------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements and text. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
font-variant-emoji = 
  normal   |
  text     |
  emoji    |
  unicode  
```

Examples
--------

### Changing the way an emoji is displayed

This example shows how you can render an emoji in its `text` or `emoji`
presentation.

#### HTML

[html]

```html
<section class="emojis">
  <div class="emoji">
    <h2>text presentation</h2>
    <div class="text-presentation">☎</div>
  </div>
  <div class="emoji">
    <h2>emoji presentation</h2>
    <div class="emoji-presentation">☎</div>
  </div>
</section>
```

#### CSS

[css]

```css
.text-presentation {
  font-variant-emoji: text;
}

.emoji-presentation {
  font-variant-emoji: emoji;
}
```

#### Result

Accessibility concerns
----------------------

While the use of emojis may seem fun, you should consider their impact
on accessibility, specifically for users with visual and cognitive
impairments. Consider the following factors while using emojis:

- Display on screen-readers: Screen-readers will read out the alt text
    of an emoji. Keep this in mind to consider the position of an emoji
    in the content. Repeated and overuse of emojis will have a
    detrimental effect on screen-reader users. It is better to use
    emojis than emoticons; emoticons will be read out as punctuation
    characters.
- Contrast with background: When using emojis, consider their colors
    and how that will work with the background color, especially if you
    have background colors that can change, such as light/dark modes.
- Intent of use: Do not use emojis to replace words because your
    understanding of the emoji meaning may differ from that of the
    users\'. Also consider that emojis might have different meanings in
    different cultures and geographies. Our recommendation is to
    preferably limit usage to commonly known emojis.

Specifications
--------------

  ------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-variant-emoji-prop]](https://drafts.csswg.org/css-fonts/#font-variant-emoji-prop)

  ------------------------------------------------------------------------------------------------

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

`font-variant-emoji`

No

No

108

No

No

No

No

No

No

No

No

No

See also
--------

- [font-variant](font-variant.md)
- [font-variant-alternates](font-variant-alternates.md)
- [font-variant-caps](font-variant-caps.md)
- [font-variant-east-asian](font-variant-east-asian.md)
- [font-variant-ligatures](font-variant-ligatures.md)
- [font-variant-numeric](font-variant-numeric.md)
- [Emojis and accessibility: How to use them
    properly](https://uxdesign.cc/emojis-in-accessibility-how-to-use-them-properly-66b73986b803)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-emoji>
