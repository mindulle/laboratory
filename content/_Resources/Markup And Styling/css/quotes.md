quotes
======

The [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) `quotes`
property sets how the browser should render quotation marks that are
automatically added to the HTML
[`<q>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q)
element or added using the `open-quotes` or `close-quotes` (or omitted
using the `no-open-quote` and `no-close-quote`) values of the of the CSS
[`content`](content.md) property.

Try it
------

Browsers insert quotation marks at the opening and closing of `<q>`
elements and for the `open-quote` and `close-quote` values of the
`content` property. Each opening or closing quote is replaced by one of
the strings from the value of `quotes`, based on the depth of nesting,
or, if `quotes` is explicity set to or otherwise resolves to `auto`, the
quotation marks used are language dependent.

Syntax
------

[css]

```css
/* Keyword value */
quotes: none;
quotes: auto;

/* <string> values */
quotes: "«" "»"; /* Set open-quote and close-quote to use French quotation marks */
quotes: "«" "»" "‹" "›"; /* Set two levels of quotation marks */

/* Global values */
quotes: inherit;
quotes: initial;
quotes: revert;
quotes: revert-layer;
quotes: unset;
```

### Values

[`none`](#none)

:   The `open-quote` and `close-quote` values of the
    [`content`](content.md) property produce no quotation marks, as if
    `no-open-quote` and `no-close-quote` were set, respectively.

[`auto`](#auto)

:   Quotation marks that are typographically appropriate for the
    inherited language (i.e. via the
    [`lang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#lang)
    attribute set on the parent or other ancestor).

[`[`](#sect1)`<string>` \<string\>\]+

:   Defines one or more pairs of quotation mark values for opening and
    closing quotes. In each pair, the first of each pair of quotes are
    used as the values for the `open-quote` and the second of each pair
    is the `close-quote`.

    The first pair represents the quotation\'s outer level. The second
    pair, if present, represents the first nested level. The next pair
    is used for doubly nested levels, and so on. If the depth of quote
    nesting is greater than the number of pairs, the last pair in the
    `quotes` value is repeated.

    Which pair of quotes is used depends on the depth, or nesting level,
    of quotes: the number of occurrences of `<q>` quotes or `open-quote`
    (or `no-open-quote`) in all generated text before the current
    occurrence, minus the number of occurrences of closing quotes,
    either as `</q>`, `close-quote`, or `no-close-quote`. If the depth
    is 0, the first pair is used, if the depth is 1, the second pair is
    used, etc.

**Note:** The CSS `content` property value `open-quote` increments and
`no-close-quote` decrements the quoting level, but does not insert a
quotation marks.

Formal definition
-----------------

  ---------------------------------- -----------------------
  [Initial value](initial_value.md)     depends on user agent
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -----------------------

Formal syntax
-------------

```text
quotes = 
  auto                    |
  none                    |
  [ <string> <string> ]+  
```

Examples
--------

### Default quotes and overrides

This examples compares the default quotes provided by the semantic HTML
`<q>` element to those we define using the CSS `quotes` property.

The default value of `quotes` is [`auto`](#auto). In this example, the
first list item has `quotes: auto` set, so gets the default quotes for
the language specified; the same as if no `quotes` property was set. The
second list item defines which quotation marks to use for quotes and
nested quotes; these quotation marks will be used for descendants of an
element with `specialQuotes` class regardless of the language (like any
[`lang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/lang)
attribute values set).

#### HTML

[html]

```html
<ul>
  <li>
    Default quotes:
    <p lang="ru">
      <q
        >Митч Макконнелл - это человек, который знает о России и ее влиянии
        меньше, чем даже Дональд Трамп, и <q>я ничего не знаю</q>, сказал
        Трамп</q
      >, - писал Раджу.
    </p>
  </li>
  <li class="specialQuotes">
    Defined by <code>quotes</code> property :
    <p lang="ru">
      <q
        >Митч Макконнелл - это человек, который знает о России и ее влиянии
        меньше, чем даже Дональд Трамп, и <q>я ничего не знаю</q>, сказал
        Трамп</q
      >, - писал Раджу.
    </p>
  </li>
  <ul></ul>
</ul>
```

#### CSS

[css]

```css
li {
  quotes: auto;
}

.specialQuotes {
  quotes: "“" "”" "‘" "’";
}
```

#### Result

By default, browser provide language specific quotation marks when the
`<q>` element is used. If the `quotes` property is defined, the values
provided override the browser defaults. Note the `quotes` property is
inherited. The `quotes` property is set on the `<li>` with the
`specialQuotes` class, but the quotes are applied the `<q>` elements.

Note that each open-quote and close-quote is replaced by one of the
strings from the value of quotes, based on the depth of nesting.

### Auto quotes

The default value of `quotes` is `auto`. This example works without it
being explicitly being set.

#### HTML

[html]

```html
<ul>
  <li lang="fr">
    <q>Ceci est une citation française.</q>
  </li>
  <li lang="ru">
    <q>Это русская цитата</q>
  </li>
  <li lang="de">
    <q>Dies ist ein deutsches Zitat</q>
  </li>
  <li lang="en">
    <q>This is an English quote.</q>
  </li>
</ul>
```

#### CSS

[css]

```css
q {
  quotes: auto;
}
li:not(:last-of-type) {
  border-bottom: 1px solid;
}
```

#### Result

Note that the
[`lang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#lang)
attribute was placed on an ancestor of the `<q>`, not the `<q>` itself.
If a quotation is in a different language than the surrounding text, it
is customary to quote the text with the quote marks of the language of
the surrounding text, not the language of the quotation itself.

### With generated content

In this example, instead of using the `<q>` element, we are adding
quotation marks to the [`::before`](::before) and [`::after`](::after)
pseudo-elements before and after the content of each element with a
specific class name.

#### HTML

[html]

```html
<p>
  <span class="quote">I should be using quotes</span>, I thought,
  <span class="quote"
    >But why use semantic HTML elements when I can add classes to
    <span class="quote">ALL THE THINGS!</span>?
  </span>
</p>
```

#### CSS

[css]

```css
.quote {
  quotes: '"' '"' "'" "'";
}
.quote::before {
  content: open-quote;
}
.quote::after {
  content: close-quote;
}
```

#### Result

### Text as quotes and empty quotes

This example demonstrates using something other than quotation marks as
the `<string>` values. The open-quote indicates the speaker and, as
there is not opening quotation mark, the close-quote is the empty.
(Mixing a `<string>` with an enumerated keyword to create a pair is not
supported). We set `auto` for the nested quotes. These nested quotes
will be book-ended by whatever the language dictates is normal for
nested quotes.

#### HTML

[html]

```html
<ul>
  <li><q data-speaker="karen">Hello</q></li>
  <li><q data-speaker="chad">Hi</q></li>
  <li><q data-speaker="karen">this conversation is not interesting</q></li>
  <li>
    <q data-speaker="pat"
      >OMG! <q>Hi</q>? Seriously? at least <q>hello</q> is five letters long.</q
    >
  </li>
</ul>
```

#### CSS

[css]

```css
[data-speaker="karen" i] {
  quotes: "She said: " "";
}
[data-speaker="chad" i] {
  quotes: "He said: " "";
}
[data-speaker="pat" i] {
  quotes: "They said: " "";
}
[data-speaker] q {
  quotes: auto;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Generated Content Module Level 3\
  [\# quotes]](https://drafts.csswg.org/css-content/#quotes)

  -----------------------------------------------------------------------

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

`quotes`

11

12

1.5

8

4

9

37

18

4

14

9

1.0

`quotes_auto`

87

87

70

NoThis value is not supported, but the default browser behavior is to
choose appropriate quotes for the user\'s language setting

73

14.1

87

87

79

62

14.5

14.0

See also
--------

- [CSS generated content](css_generated_content.md) module
- [`contain`](contain.md)
- [`content`](content.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/quotes>
