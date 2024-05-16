ruby-align
==========

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `ruby-align` CSS property defines the distribution of the different
ruby elements over the base.

Syntax
------

[css]

```css
/* Keyword values */
ruby-align: start;
ruby-align: center;
ruby-align: space-between;
ruby-align: space-around;

/* Global values */
ruby-align: inherit;
ruby-align: initial;
ruby-align: revert;
ruby-align: revert-layer;
ruby-align: unset;
```

### Values

[`start`](#start)

:   Is a keyword indicating that the ruby will be aligned with the start
    of the base text.

[`center`](#center)

:   Is a keyword indicating that the ruby will be aligned at the middle
    of the base text.

[`space-between`](#space-between)

:   Is a keyword indicating that the extra space will be distributed
    between the elements of the ruby.

[`space-around`](#space-around)

:   Is a keyword indicating that the extra space will be distributed
    between the elements of the ruby, and around it.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `space-around`
  Applies to                         ruby bases, ruby annotations, ruby base containers, ruby annotation containers
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     by computed value type
  ---------------------------------- --------------------------------------------------------------------------------

Formal syntax
-------------

```
ruby-align = 
  start          |
  center         |
  space-between  |
  space-around   
```

Examples
--------

### Ruby aligned at the start of the base text

#### HTML

[html]

```html
<ruby>
  <rb>This is a long text to check</rb>
  <rp>（</rp><rt>short ruby</rt><rp>）</rp>
</ruby>
```

#### CSS

[css]

```css
ruby {
  ruby-align: start;
}
```

#### Result

### Ruby aligned at the center of the base text

#### HTML

[html]

```html
<ruby>
  <rb>This is a long text to check</rb>
  <rp>（</rp><rt>short ruby</rt><rp>）</rp>
</ruby>
```

#### CSS

[css]

```css
ruby {
  ruby-align: center;
}
```

#### Result

### Extra space distributed between ruby elements

#### HTML

[html]

```html
<ruby>
  <rb>This is a long text to check</rb>
  <rp>（</rp><rt>short ruby</rt><rp>）</rp>
</ruby>
```

#### CSS

[css]

```css
ruby {
  ruby-align: space-between;
}
```

#### Result

### Extra space distributed between and around ruby elements

#### HTML

[html]

```html
<ruby>
  <rb>This is a long text to check</rb>
  <rp>（</rp><rt>short ruby</rt><rp>）</rp>
</ruby>
```

#### CSS

[css]

```css
ruby {
  ruby-align: space-around;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------

  [CSS Ruby Annotation Layout Module Level 1\
  [\#
  ruby-align-property]](https://drafts.csswg.org/css-ruby/#ruby-align-property)

  ---------------------------------------------------------------------------------------

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

`ruby-align`

No

No

38

NoInternet Explorer 9 and later supports an earlier draft of CSS Ruby
with non-standard values for this property: `auto`, `left`, `center`,
`right`, `distribute-letter`, `distribute-space`, and `line-edge`.

No

No

No

No

38

No

No

No

See also
--------

- HTML Ruby elements:
    [`<ruby>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ruby),
    [`<rt>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rt),
    [`<rp>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rp),
    and
    [`<rtc>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rtc).
- CSS Ruby properties: [`ruby-position`](ruby-position.md),
    [`ruby-merge`].

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/ruby-align>
