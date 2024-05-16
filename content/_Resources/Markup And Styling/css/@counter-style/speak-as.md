speak-as
========

The `speak-as` descriptor specifies how a counter symbol constructed
with a given [`@counter-style`](@counter-style.md) will be represented
in the spoken form. For example, an author can specify a counter symbol
to be either spoken as its numerical value or just represented with an
audio cue.

Syntax
------

[css]

```css
/* Keyword values */
speak-as: auto;
speak-as: bullets;
speak-as: numbers;
speak-as: words;
speak-as: spell-out;

/* @counter-style name value */
speak-as: <counter-style-name>;
```

### Values

[`auto`](#auto)

:   If the value of `speak-as` is specified as `auto`, then the
    effective value of `speak-as` will be determined based on the value
    of the [`system`](system.md) descriptor:

    -   If the value of `system` is `alphabetic`, the effective value of
        `speak-as` will be `spell-out`.
    -   If `system` is `cyclic`, the effective value of `speak-as` will
        be `bullets`.
    -   If `system` is `extends`, the value of `speak-as` will be the
        same as if `speak-as: auto` is specified on the extended style.
    -   For all other cases, specifying `auto` has the same effect as
        specifying `speak-as: numbers`.

[`bullets`](#bullets)

:   A phrase or an audio cue defined by the [user
    agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
    for representing an unordered list item will be read out.

[`numbers`](#numbers)

:   The numerical value of the counter will be read out in the document
    language.

[`words`](#words)

:   The user agent will generate a counter value as normal and read it
    out as a word in the document language.

[`spell-out`](#spell-out)

:   The user agent will generate a counter representation as normal and
    would read it out letter by letter. If the user agent doesn\'t know
    how to read out a particular counter symbol, the user agent might
    read it out as if the value of `speak-as` was `numbers`.

[`<counter-style-name>`](#counter-style-name)

:   The name of another counter style, specified as a
    [`<custom-ident>`](custom-ident.md). If included, the counter will
    be spoken out in the form specified in that counter style, kind of
    like specifying the [`fallback`](fallback.md) descriptor. If the
    specified style does not exist, `speak-as` defaults to `auto`.

Accessibility concerns
----------------------

Assistive technology support is very limited for the `speak-as`
property. Do not rely on it to convey information critical to
understanding the page\'s purpose.

[Let\'s Talk About Speech CSS \| CSS
Tricks](https://css-tricks.com/lets-talk-speech-css/)

Formal definition
-----------------

  ------------------------------------- ---------------------------------------
  Related [at-rule](at-rule.md)         [`@counter-style`](@counter-style.md)
  [Initial value](initial_value.md)     `auto`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- ---------------------------------------

Formal syntax
-------------

```
speak-as = 
  auto                  |
  bullets               |
  numbers               |
  words                 |
  spell-out             |
  <counter-style-name>  
```

Examples
--------

### Setting the spoken form for a counter

#### HTML

[html]

```html
<ul class="list">
  <li>One</li>
  <li>Two</li>
  <li>Three</li>
  <li>Four</li>
  <li>Five</li>
</ul>
```

#### CSS

[css]

```css
@counter-style speak-as-example {
  system: fixed;
  symbols:     ;
  suffix: " ";
  speak-as: numbers;
}

.list {
  list-style: speak-as-example;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [CSS Counter Styles Level 3\
  [\#
  counter-style-speak-as]](https://drafts.csswg.org/css-counter-styles/#counter-style-speak-as)

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

See also
--------

- [`list-style`](list-style.md),
    [`list-style-image`](list-style-image.md),
    [`list-style-position`](list-style-position.md)
- [`symbols()`](symbols.md), the functional notation creating anonymous
    counter styles.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/speak-as>
