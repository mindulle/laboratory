Selector list
=============

The CSS **selector list** (`,`) selects all the matching nodes. A
selector list is a comma-separated list of selectors.

Description
-----------

When multiple selectors share the same declarations, they can be grouped
together into a comma-separated list. Selector lists can also be passed
as parameters to some functional CSS pseudo-classes. White space may
appear before and/or after the comma.

The following three declarations are equivalent:

[css]

```css
span {
  border: red 2px solid;
}
div {
  border: red 2px solid;
}
```

[css]

```css
span,
div {
  border: red 2px solid;
}
```

[css]

```css
:is(span, div) {
  border: red 2px solid;
}
```

Examples
--------

When applying the same styles to elements matching different criteria,
grouping the selectors in a comma-separated list can improve consistency
while reducing the size of style sheets.

### Single line grouping

This example shows grouping selectors in a single line using a
comma-separated list.

[css]

```css
h1, h2, h3, h4, h5, h6 {
  font-family: helvetica;
}
```

### Multi line grouping

This example shows grouping selectors in multiple lines using a
comma-separated list.

[css]

```css
#main,
.content,
article,
h1 + p {
  font-size: 1.1em;
}
```

Valid and invalid selector lists
--------------------------------

An invalid selector represents, and therefore matches, nothing. When a
selector list contains an invalid selector, the entire style block is
ignored, except for the [`:is()`](:is) and [`:where()`](:where)
pseudo-classes that accept [forgiving selector
lists](#forgiving_selector_list).

### Invalid selector list

A downside to using a selector list is that a single unsupported
selector in the selector list invalidates the entire rule.

Consider the following two CSS rule sets:

[css]

```css
h1 {
  font-family: sans-serif;
}
h2:invalid-pseudo {
  font-family: sans-serif;
}
h3 {
  font-family: sans-serif;
}
```

[css]

```css
h1,
h2:invalid-pseudo,
h3 {
  font-family: sans-serif;
}
```

They are not equivalent. In the first rule set, styles will be applied
on the `h1` and `h3` elements, but the `h2:invalid-pseudo` rule will not
be parsed. In the second rule set, because one selector in the list is
invalid, the entire rule will not be parsed. Because of this, no style
will be applied to the `h1` and `h3` elements as when any selector in a
list of selectors in invalid, the entire style block will be ignored.

### Forgiving selector list

A way to remedy the [invalid selector list](#invalid_selector_list)
problem is to use the [`:is()`](:is) or the [`:where()`](:where)
pseudo-class, which accept a forgiving selector list. Each selector in a
forgiving selector list is parsed individually. So any invalid selectors
in the list are ignored and the valid ones are used.

Carrying on from the previous example, the following two CSS rule sets
are now equivalent:

[css]

```css
h1 {
  font-family: sans-serif;
}
h2:maybe-unsupported {
  font-family: sans-serif;
}
h3 {
  font-family: sans-serif;
}
```

[css]

```css
:is(h1, h2:maybe-unsupported, h3) {
  font-family: sans-serif;
}
```

The difference between the two is that the specificity of `:is()` is its
most specific argument, whereas the `:where()` selector and the
forgiving selector list parameter do not add any specificity weight.

### Relative selector list

A relative selector list is a comma-separated selector list parsed as
[](selector_structure.md#relative_selector), which
begin with an explicit or implied combinator.

[css]

```css
h2:has(+ p, + ul.red) {
  font-style: italic;
}
```

In the above example, the italic style will be applied to any `h2`
heading that is immediately followed by `<p>` or `<ul class="red">`.
Note that pseudo-elements and the `:has()` selector are not valid within
the [`:has()`](:has) relative selector list.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Selectors Level 4\
  [\# grouping]](https://drafts.csswg.org/selectors/#grouping)

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

`Selector_list`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

See also
--------

- The [`:is()`](:is) and [`:where()`](:where) pseudo-classes accept
    forgiving selector lists.
- The [`:not()`](:not) pseudo-class accepts a regular selector list
- The [`:has()`](:has) pseudo-class accepts a relative selector list.
- [CSS selectors](css_selectors.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list>
