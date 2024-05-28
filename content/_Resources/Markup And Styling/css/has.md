:has()
======

The functional `:has()` CSS [pseudo-class](pseudo-classes.md) represents an
element if any of the [](selector_structure.md#relative_selector) that are
passed as an argument match at least one element when anchored against
this element. This pseudo-class presents a way of selecting a parent
element or a previous sibling element with respect to a reference
element by taking a [](selector_list.md#relative_selector_list) as an argument.

[css]

```css
/* Selects an h1 heading with a
paragraph element that immediately follows
the h1 and applies the style to h1 */
h1:has(+ p) {
  margin-bottom: 0;
}
```

The `:has()` pseudo-class takes on the [specificity](specificity.md) of the
most specific selector in its arguments the same way as [`:is()`](:is)
and [`:not()`](:not) do.

Syntax
------

[css]

```css
:has(<relative-selector-list>) {
  /* ... */
}
```

If the `:has()` pseudo-class itself is not supported in a browser, the
entire selector block will fail unless `:has()` is in a forgiving
selector list, such as in [`:is()`](:is) and [`:where()`](:where)).

The `:has()` pseudo-class cannot be nested within another `:has()`. This
is because many pseudo-elements exist conditionally based on the styling
of their ancestors and allowing these to be queried by `:has()` can
introduce cyclic querying.

Pseudo-elements are also not valid selectors within `:has()` and
pseudo-elements are not valid anchors for `:has()`.

Examples
--------

### With the sibling combinator

The `:has()` style declaration in the following example adjusts the
spacing after `<h1>` headings if they are immediately followed by an
`<h2>` heading.

#### HTML

[html]

```html
<section>
  <article>
    <h1>Morning Times</h1>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
      tempor incididunt ut labore et dolore magna aliqua.
    </p>
  </article>
  <article>
    <h1>Morning Times</h1>
    <h2>Delivering you news every morning</h2>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
      tempor incididunt ut labore et dolore magna aliqua.
    </p>
  </article>
</section>
```

#### CSS

[css]

```css
h1,
h2 {
  margin: 0 0 1rem 0;
}

h1:has(+ h2) {
  margin: 0 0 0.25rem 0;
}
```

#### Result

This example shows two similar texts side-by-side for comparison -- the
left one with an `H1` heading followed by a paragraph and the right one
with an `H1` heading followed by an `H2` heading and then a paragraph.
In the example on the right, `:has()` helps to select the `H1` element
that is immediately followed by an `H2` element (indicated by the
next-sibling combinator[`+`](next-sibling_combinator.md)) and the CSS rule
reduces the spacing after such an `H1` element. Without the `:has()`
pseudo-class, you cannot use CSS selectors to select a preceding sibling
of a different type or a parent element.

### With the :is() pseudo-class

This example builds on the previous example to show how to select
multiple elements with `:has()`.

#### HTML

[html]

```html
<section>
  <article>
    <h1>Morning Times</h1>
    <h2>Delivering you news every morning</h2>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
      tempor incididunt ut labore et dolore magna aliqua.
    </p>
  </article>
  <article>
    <h1>Morning Times</h1>
    <h2>Delivering you news every morning</h2>
    <h3>8:00 am</h3>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
      tempor incididunt ut labore et dolore magna aliqua.
    </p>
  </article>
</section>
```

#### CSS

[css]

```css
h1,
h2,
h3 {
  margin: 0 0 1rem 0;
}

:is(h1, h2, h3):has(+ :is(h2, h3, h4)) {
  margin: 0 0 0.25rem 0;
}
```

#### Result

Here, the first [`:is()`](:is) pseudo-class is used to select any of the
heading elements in the list. The second `:is()` pseudo-class is used to
pass a list of next-sibling selectors as an argument to `:has()`. The
`:has()` pseudo-class helps to select any `H1`, `H2`, or `H3` element
that is immediately followed by (indicated by
[`+`](next-sibling_combinator.md)) an `H2`, `H3`, or `H4` element and the
CSS rule reduces the spacing after such `H1`, `H2`, or `H3` elements.

This selector could have also been written as:

[css]

```css
:is(h1, h2, h3):has(+ h2, + h3, + h4) {
  margin: 0 0 0.25rem 0;
}
```

### Logical operations

The `:has()` relational selector can be used to check if one of the
multiple features is true or if all the features are true.

By using comma-separated values inside the `:has()` relational selector,
you are checking to see if any of the parameters exist. `x:has(a, b)`
will style `x` if descendant `a` OR `b` exists.

By chaining together multiple `:has()` relational selectors together,
you are checking to see if all of the parameters exist.
`x:has(a):has(b)` will style `x` if descendant `a` AND `b` exist.

[css]

```css
body:has(video, audio) {
  /* styles to apply if the content contains audio OR video */
}
body:has(video):has(audio) {
  /* styles to apply if the content contains both audio AND video */
}
```

Analogy between :has() and regular expressions
----------------------------------------------

Interestingly, we can relate some CSS `:has()` constructs with the
[lookahead
assertion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Lookahead_assertion)
in regular expressions because they both allow you to select elements
(or strings in regular expressions) based on a condition without
actually selecting the condition matching the element (or string)
itself.

### Positive lookahead (?=pattern)

In the regular expression `abc(?=xyz)`, the string `abc` is matched only
if it is immediately followed by the string `xyz`. As it is a lookahead
operation, the `xyz` is not included in the match.

The analogous construct in CSS would be `.abc:has(+ .xyz)`: it selects
the element `.abc` only if there is a next sibling `.xyz`. The part
`:has(+ .xyz)` acts as a lookahead operation because the element `.abc`
is selected and not the element `.xyz`.

### Negative lookahead (?!pattern)

Similarly, for the negative lookahead case, in the regular expression
`abc(?!xyz)`, the string `abc` is matched only if it is *not* followed
by `xyz`. The analogous CSS construct `.abc:has(+ :not(.xyz))` doesn\'t
select the element `.abc` if the next element is `.xyz`.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  relational]](https://drafts.csswg.org/selectors/#relational)

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

`:has`

105

105

103

No

91

15.4

105

105

No

72

15.4

20.0

See also
--------

- [`:is()`](:is), [`:where()`](:where), [`:not()`](:not)
- [](selectors_and_combinators.md)
- [CSS selector structure](selector_structure.md)
- [Selector list](selector_list.md)
- [CSS selector module](css_selectors.md)
- [Locating DOM elements using
    selectors](https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model/Locating_DOM_elements_using_selectors)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:has>
