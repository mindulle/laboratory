font-kerning
============

The `font-kerning` CSS property sets the use of the kerning information
stored in a font.

Try it
------

*Kerning* defines how letters are spaced. In *well-kerned* fonts, this
feature makes character spacing more uniform and pleasant to read than
it would otherwise be.

In the image below, for instance, the examples on the left do not use
kerning, while the ones on the right do:

Syntax
------

[css]

```css
font-kerning: auto;
font-kerning: normal;
font-kerning: none;

/* Global values */
font-kerning: inherit;
font-kerning: initial;
font-kerning: revert;
font-kerning: revert-layer;
font-kerning: unset;
```

### Values

[`auto`](#auto)

:   The browser determines whether font kerning should be used or not.
    For example, some browsers will disable kerning on small fonts,
    since applying it could harm the readability of text.

[`normal`](#normal)

:   Font kerning information stored in the font must be applied.

[`none`](#none)

:   Font kerning information stored in the font is disabled.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
font-kerning = 
  auto    |
  normal  |
  none    
```

Examples
--------

### Enabling and disabling kerning

#### HTML

[html]

```html
<div id="kern"></div>
<div id="nokern"></div>
<textarea id="input">AV T. ij</textarea>
```

#### CSS

[css]

```css
div {
  font-size: 2rem;
  font-family: serif;
}

#nokern {
  font-kerning: none;
}

#kern {
  font-kerning: normal;
}
```

#### JavaScript

[js]

```js
const input = document.getElementById("input");
const kern = document.getElementById("kern");
const nokern = document.getElementById("nokern");

input.addEventListener("keyup", () => {
  kern.textContent = input.value; /* Update content */
  nokern.textContent = input.value;
});

kern.textContent = input.value; /* Initialize content */
nokern.textContent = input.value;
```

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-kerning-prop]](https://drafts.csswg.org/css-fonts/#font-kerning-prop)

  ------------------------------------------------------------------------------------

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

`font-kerning`

3329--33

79

32

No

2016--20

96

4.4.34.4--4.4.3

3329--33

32

2016--20

96

2.01.0--2.0

See also
--------

- [`font-variant`](font-variant.md),
    [`font-variant-position`](font-variant-position.md),
    [`font-variant-east-asian`](font-variant-east-asian.md),
    [`font-variant-caps`](font-variant-caps.md),
    [`font-variant-ligatures`](font-variant-ligatures.md),
    [`font-variant-numeric`](font-variant-numeric.md),
    [`font-variant-alternates`](font-variant-alternates.md),
    [`font-synthesis`](font-synthesis.md),
    [`letter-spacing`](letter-spacing.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-kerning>
