CSS selector structure
======================

The CSS selector represents a particular pattern of element or elements
in a tree structure. The term \"selector\" can refer to a [simple
selector](#simple_selector), a [compound selector](#compound_selector),
or a [complex selector](#complex_selector). When included in the
`:has()` pseudo-class as a parameter, these selectors are referred to as
[relative selectors](#relative_selector), representing elements relative
to one or more anchor elements.

These selectors can be combined into a comma-separated [selector
list](#selector_list). If any selector in a [](selector_list.md#valid_and_invalid_selector_lists) list is
invalid, the entire selector list is invalidated.

### Simple selector

A **simple selector** is a selector with a single component, such as a
single type selector, attribute selector, or pseudo-class, that\'s not
used in combination with or contains any other selector component or
combinator. A given element is said to match a simple selector when that
simple selector accurately describes the element. Any selector that
contains a single [](selectors_and_combinators.md#basic_selectors), [](attribute_selectors.md), [pseudo-class](pseudo-classes.md), or
[pseudo-element](pseudo-elements.md) selector is a simple selector.

[css]

```css
#myId {
}

[pattern*="\d"] {
}
```

### Compound selector

A **compound selector** is a sequence of [simple
selectors](#simple_selector) that are not separated by a
[combinator](selectors_and_combinators.md#combinators). A compound selector
represents a set of simultaneous conditions on a single element. A given
element is said to match a compound selector when the element matches
all the simple selectors in the compound selector.

[css]

```css
a#selected {
}

[type="checkbox"]:checked:focus {
}
```

In a compound selector, the [type selector](type_selectors.md) or
[universal selector](universal_selectors.md) must come first in the
sequence of selectors. Only one type selector or universal selector is
allowed in the sequence. As whitespace represents the [](descendant_combinator.md), no whitespace is allowed between
the simple selectors that make up a compound selector.

### Complex selector

A **complex selector** is a sequence of one or more simple and/or
compound selectors that are separated by combinators, including the
white space [descendant combinator](descendant_combinator.md).

A complex selector represents a set of simultaneous conditions on a set
of elements.

[css]

```css
a#selected > .icon {
}

.box h2 + p {
}
```

Selectors can be read from right to left. For example,
`a#selected > .icon` matches all elements with a class of `icon` that
are the direct children of the `<a>` element with the id `selected`. The
selector `.box h2 + p` matches the first `<p>`s to come immediately
after any `<h2>` elements that are descendants of any element with the
class of `box`.

### Relative selector

A **relative selector** is a selector representing an element relative
to one or more anchor elements preceded by a combinator. Relative
selectors that don\'t begin with an explicit combinator have an implied
[descendant combinator](descendant_combinator.md).

[css]

```css
+ div#topic > #reference {
}

> .icon {
}

dt:has(+ img) ~ dd {
}
```

### Selector list

A [**selector list**](selector_list.md) is a comma-separated list of
simple, compound, and/or complex selectors. A given element is said to
match a selector list when the element matches any (at least one) of the
selectors in that selector list.

[css]

```css
#main,
article.heading {
}
```

If any selector in a [](selector_list.md#valid_and_invalid_selector_lists) list is
invalid, the entire selector list is invalidated.

[css]

```css
#main,
:bad-pseudoclass,
.validClass {
  /* `:bad-pseudoclass` is invalid, invalidating this style block */
}
```

The [`:is()`](../:is) and [`:where()`](../:where) pseudo-classes can be
used to construct [](selector_list.md#forgiving_selector_list).

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Selectors Level 4\
  ](https://drafts.csswg.org/selectors/)

  -----------------------------------------------------------------------

See also
--------

- [CSS selectors and combinators](selectors_and_combinators.md)
- [Forgiving selector list](selector_list.md#forgiving_selector_list)
- [`Document.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)
- [`Document.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)
- [CSS selectors](css_selectors.md) module
- [CSS pseudo-elements](css_pseudo-elements.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure>
