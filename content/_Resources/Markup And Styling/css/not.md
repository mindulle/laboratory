:not()
======

The `:not()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents elements that do not match a
list of selectors. Since it prevents specific items from being selected,
it is known as the *negation pseudo-class*.

Try it
------

The `:not()` pseudo-class has a number of [quirks, tricks, and
unexpected results](#description) that you should be aware of before
using it.

Syntax
------

The `:not()` pseudo-class requires a comma-separated list of one or more
selectors as its argument. The list must not contain another negation
selector or a [pseudo-element](pseudo-elements.md).

[css]

```css
:not(<complex-selector-list>) {
  /* ... */
}
```

Description
-----------

There are several unusual effects and outcomes when using `:not()` that
you should keep in mind when using it:

- Useless selectors can be written using this pseudo-class. For
    example, `:not(*)` matches any element which is not an element,
    which is obviously nonsense, so the accompanying rule will never be
    applied.
- This pseudo-class can increase the [specificity](specificity.md) of a
    rule. For example, `#foo:not(#bar)` will match the same element as
    the simpler `#foo`, but has the higher specificity of two `id`
    selectors.
- The specificity of the `:not()` pseudo-class is replaced by the
    specificity of the most specific selector in its comma-separated
    argument of selectors; providing the same specificity as if it had
    been written [`:not(:is(argument))`](:is).
- `:not(.foo)` will match anything that isn\'t `.foo`, *including
    [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)
    and
    [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body).*
- This selector will match everything that is \"not an X\". This may
    be surprising when used with [](descendant_combinator.md), since there are multiple paths
    to select a target element. For instance, `body :not(table) a` will
    still apply to links inside a
    [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table),
    since
    [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr),
    [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody),
    [`<th>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/th),
    [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td),
    [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption),
    etc. can all match the `:not(table)` part of the selector.
- You can negate several selectors at the same time. Example:
    `:not(.foo, .bar)` is equivalent to `:not(.foo):not(.bar)`.
- If any selector passed to the `:not()` pseudo-class is invalid or
    not supported by the browser, the whole rule will be invalidated.
    The effective way to overcome this behavior is to use [`:is()`](:is)
    pseudo-class, which accepts a forgiving selector list. For example
    `:not(.foo, :invalid-pseudo-class)` will invalidate a whole rule,
    but `:not(:is(.foo, :invalid-pseudo-class))` will match any
    (*including
    [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)
    and
    [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body)*)
    element that isn\'t `.foo`.

Examples
--------

### Using :not() with valid selectors

This example shows some simple cases of using `:not()`.

#### HTML

[html]

```html
<p>I am a paragraph.</p>
<p class="fancy">I am so very fancy!</p>
<div>I am NOT a paragraph.</div>
<h2>
  <span class="foo">foo inside h2</span>
  <span class="bar">bar inside h2</span>
</h2>
```

#### CSS

[css]

```css
.fancy {
  text-shadow: 2px 2px 3px gold;
}

/* <p> elements that don't have a class `.fancy` */
p:not(.fancy) {
  color: green;
}

/* Elements that are not <p> elements */
body :not(p) {
  text-decoration: underline;
}

/* Elements that are not <div>s or `.fancy` */
body :not(div):not(.fancy) {
  font-weight: bold;
}

/* Elements that are not <div>s or `.fancy` */
body :not(div, .fancy) {
  text-decoration: overline underline;
}

/* Elements inside an <h2> that aren't a <span> with a class of `.foo` */
h2 :not(span.foo) {
  color: red;
}
```

#### Result

### Using :not() with invalid selectors

This example shows the use of `:not()` with invalid selectors and how to
prevent invalidation.

#### HTML

[html]

```html
<p class="foo">I am a paragraph with .foo</p>
<p class="bar">I am a paragraph with .bar</p>
<div>I am a div without a class</div>
<div class="foo">I am a div with .foo</div>
<div class="bar">I am a div with .bar</div>
<div class="foo bar">I am a div with .foo and .bar</div>
```

#### CSS

[css]

```css
/* Invalid rule, does nothing */
p:not(.foo, :invalid-pseudo-class) {
  color: red;
  font-style: italic;
}

/* Select all <p> elements without the `foo` class */
p:not(:is(.foo, :invalid-pseudo-class)) {
  color: green;
  border-top: dotted thin currentcolor;
}

/* Select all <div> elements without the `foo` or the `bar` class */
div:not(.foo, .bar) {
  color: red;
  font-style: italic;
}

/* Select all <div> elements without the `foo` or the `bar` class */
div:not(:is(.foo, .bar)) {
  border-bottom: dotted thin currentcolor;
}
```

#### Result

The `p:not(.foo, :invalid-pseudo-class)` rule is invalid because it
contains an invalid selector. The `:is()` pseudo-class accepts a
forgiving selector list, so the `:is(.foo, :invalid-pseudo-class)` rule
is valid and equivalent to `:is(.foo)`. Thus, the
`p:not(:is(.foo, :invalid-pseudo-class))` rule is valid and equivalent
to `p:not(.foo)`.

If `:invalid-pseudo-class` was a valid selector, the first two rules
above would still be equivalent (the last two rules showcase that). The
use of `:is()` makes the rule more robust.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Selectors Level 4\
  [\# negation]](https://drafts.csswg.org/selectors/#negation)

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

`:not`

1

12

1

9

9.5

3.1

2

18

4

10.1

2

1.0

`selector_list`

88

88

84

No

74

9

88

88

84

No

9

15.0

See also
--------

- [Pseudo-classes](pseudo-classes.md)
- [Pseudo-classes and
    pseudo-elements](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements)
- Other functional CSS pseudo-classes:
  - [`:has()`](:has)
  - [`:is()`](:is)
  - [`:where()`](:where)
- [How :not() chains multiple
    selectors](https://developer.mozilla.org/en-US/blog/css-not-pseudo-multiple-selectors/)
    on MDN blog (2023)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:not>
