:is()
=====

The `:is()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) function takes a selector list as its
argument, and selects any element that can be selected by one of the
selectors in that list. This is useful for writing large selectors in a
more compact form.

**Note:** Originally named `:matches()` (and `:any()`), this selector
was renamed to `:is()` in [CSSWG issue
\#3258](https://github.com/w3c/csswg-drafts/issues/3258).

Try it
------

Pseudo-elements are not valid in the selector list for `:is()`.

### Difference between :is() and :where()

The difference between the two is that `:is()` counts towards the
specificity of the overall selector (it takes the specificity of its
most specific argument), whereas [`:where()`](:where) has a specificity
value of 0. This is demonstrated by the [example on the `:where()`
reference page](:where#examples).

### Forgiving Selector Parsing

The specification defines `:is()` and `:where()` as accepting a
[forgiving selector
list](https://drafts.csswg.org/selectors-4/#typedef-forgiving-selector-list).

In CSS when using a selector list, if any of the selectors are invalid
then the whole list is deemed invalid. When using `:is()` or `:where()`
instead of the whole list of selectors being deemed invalid if one fails
to parse, the incorrect or unsupported selector will be ignored and the
others used.

[css]

```css
:is(:valid, :unsupported) {
  /* … */
}
```

Will still parse correctly and match `:valid` even in browsers which
don\'t support `:unsupported`, whereas:

[css]

```css
:valid,
:unsupported {
  /* … */
}
```

Will be ignored in browsers which don\'t support `:unsupported` even if
they support `:valid`.

Examples
--------

### Simplifying list selectors

The `:is()` pseudo-class can greatly simplify your CSS selectors. For
example, take the following CSS:

[css]

```css
/* 3-deep (or more) unordered lists use a square */
ol ol ul,
ol ul ul,
ol menu ul,
ol dir ul,
ol ol menu,
ol ul menu,
ol menu menu,
ol dir menu,
ol ol dir,
ol ul dir,
ol menu dir,
ol dir dir,
ul ol ul,
ul ul ul,
ul menu ul,
ul dir ul,
ul ol menu,
ul ul menu,
ul menu menu,
ul dir menu,
ul ol dir,
ul ul dir,
ul menu dir,
ul dir dir,
menu ol ul,
menu ul ul,
menu menu ul,
menu dir ul,
menu ol menu,
menu ul menu,
menu menu menu,
menu dir menu,
menu ol dir,
menu ul dir,
menu menu dir,
menu dir dir,
dir ol ul,
dir ul ul,
dir menu ul,
dir dir ul,
dir ol menu,
dir ul menu,
dir menu menu,
dir dir menu,
dir ol dir,
dir ul dir,
dir menu dir,
dir dir dir {
  list-style-type: square;
}
```

You can replace it with:

[css]

```css
/* 3-deep (or more) unordered lists use a square */
:is(ol, ul, menu, dir) :is(ol, ul, menu, dir) :is(ul, menu, dir) {
  list-style-type: square;
}
```

### Simplifying section selectors

The `:is()` pseudo-class is particularly useful when dealing with HTML
[sections and
headings](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements).
Since
[`<section>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section),
[`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article),
[`<aside>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside),
and
[`<nav>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav)
are commonly nested together, without `:is()`, styling them to match one
another can be tricky.

For example, without `:is()`, styling all the
[h1](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)
elements at different depths could be very complicated:

[css]

```css
/* Level 0 */
h1 {
  font-size: 30px;
}

/* Level 1 */
section h1,
article h1,
aside h1,
nav h1 {
  font-size: 25px;
}

/* Level 2 */
section section h1,
section article h1,
section aside h1,
section nav h1,
article section h1,
article article h1,
article aside h1,
article nav h1,
aside section h1,
aside article h1,
aside aside h1,
aside nav h1,
nav section h1,
nav article h1,
nav aside h1,
nav nav h1 {
  font-size: 20px;
}

/* Level 3 */
/* don't even think about it! */
```

Using `:is()`, though, it\'s much easier:

[css]

```css
/* Level 0 */
h1 {
  font-size: 30px;
}
/* Level 1 */
:is(section, article, aside, nav) h1 {
  font-size: 25px;
}
/* Level 2 */
:is(section, article, aside, nav) :is(section, article, aside, nav) h1 {
  font-size: 20px;
}
/* Level 3 */
:is(section, article, aside, nav)
  :is(section, article, aside, nav)
  :is(section, article, aside, nav)
  h1 {
  font-size: 15px;
}
```

### :is() does not select pseudo-elements

The `:is()` pseudo-class does not match pseudo-elements. So rather than
this:

[css]

```css
some-element:is(::before, ::after) {
  display: block;
}
```

or this:

[css]

```css
:is(some-element::before, some-element::after) {
  display: block;
}
```

instead do:

[css]

```css
some-element::before,
some-element::after {
  display: block;
}
```

Syntax
------

[css]

```css
:is(<forgiving-selector-list>) {
  /* ... */
}
```

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  matches-pseudo]](https://drafts.csswg.org/selectors/#matches-pseudo)

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

`:is`

88

12Doesn\'t support combinators.

88

79Doesn\'t support combinators.

78

4\[\"Doesn\'t support combinators.\", \"See [bug
906353](https://bugzil.la/906353).\"\]

No

74

15Doesn\'t support combinators.

149

5Doesn\'t support combinators.

88

≤37Doesn\'t support combinators.

88

18Doesn\'t support combinators.

79

4\[\"Doesn\'t support combinators.\", \"See [bug
906353](https://bugzil.la/906353).\"\]

63

14Doesn\'t support combinators.

149

5Doesn\'t support combinators.

15.09.0--10.01.0

`forgiving_selector_list`

88

88

82

No

74

14

88

88

82

63

14

15.0

See also
--------

- [`:where()`](:where) - Like `:is()`, but with 0
    [specificity](specificity.md).
- [Selector list](selector_list.md)
- [Web
    components](https://developer.mozilla.org/en-US/docs/Web/API/Web_components)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:is>
