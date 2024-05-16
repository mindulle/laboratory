CSS selectors and combinators
=============================

CSS selectors are used to define a pattern of the elements that you want
to select for applying a set of CSS rules on the selected elements.
Combinators define the relationship between the selectors. Using various
selectors and combinators, you can precisely select and style the
desired elements based on their type, attributes, state, or relationship
to other elements.

Types of selectors
------------------

There are over 80 selectors and combinators. CSS selectors can be
grouped into the following categories based on the type of elements they
can select.

### Basic selectors

The [type selector](type_selectors.md) selects all elements that have
the given node name. For example, `div` will select all
[`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
elements and `input` will match any
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
element. The [universal selector](universal_selectors.md), denoted with
an asterisk (`*`), is a special type selector that selects all elements.

The [class selector](class_selectors.md) selects all elements that have
the given `class` attribute denoted by the class name prefixed with a
period (`.`). For example, `.index` will match any element that has
`class="index"`. The [ID selector](id_selectors.md) selects an element
based on the value of its `id` attribute. The selector is the `id`
prefixed with a \"number sign\" (U+0023, `#`). For example, `#toc` will
match the element that has `id="toc"`. Both
[`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/class)
and
[`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/id)
are global attributes. There should be only one element with a given
`id` in a document; but if there is more than one, the ID selector will
match all the elements with that `id`.

When combining a type or universal selector with a class or id selector
to create a [compound selector](selector_structure.md#compound_selector),
the type or universal selector must precede the class or id.

#### CSS

In this example, we declare four [](selector_structure.md#simple_selector) and one [](selector_structure.md#compound_selector) using the four basic
selector types, as described above.

[css]

```css
* {
  font-style: italic;
}
p {
  color: red;
}
.myClass {
  text-decoration: underline;
}
#myId {
  font-family: monospace;
}
p.myClass#myId {
  font-size: 1.5rem;
}
```

#### HTML

[html]

```html
<p class="myClass" id="myId">I match everything.</p>
<p>I match the universal and type selectors only.</p>
```

#### Result

Combinators
-----------

Using CSS combinators, we can combine selectors to select DOM nodes
based on their relationship to other elements within the document node
tree. This combining of selectors with combinators creates [](selector_structure.md#complex_selector).

### Descendant combinator

The [descendant combinator](descendant_combinator.md), denoted with one
or more spaces, selects nodes that are descendants of the first element.
For example, `div span` will match all
[`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span)
elements that are inside a
[`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
element.

### Child combinator

The [child combinator](child_combinator.md) is more specific than the
descendant combinator. Denoted with the greater than character (`>`),
the child combinator selects nodes that are direct children of the first
element. Comparing with our previous example, `div > span` will match
only the
[`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span)
elements that are direct children of a
[`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
element.

### Subsequent-sibling combinator

In addition to descendant selectors, CSS also enables selecting elements
based on their siblings. The [](subsequent-sibling_combinator.md), denoted with a tilde
(`~`), selects siblings. Given `A ~ B`, all elements matching `B` will
be selected if they are preceded by `A`, provided both `A` and `B` share
the same parent. For example, `h2 ~ p` will match all
[`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)
elements that follow an
[h2](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements),
immediately or not.

### Next-sibling combinator

The [next-sibling combinator](next-sibling_combinator.md), denoted by
the plus symbol (`+`), is similar to the subsequent-sibling. However,
given `A + B`, it only matches `B` if `B` is immediately preceded by
`A`, with both sharing the same parent. Amending our previous example,
`h2 + p` will match only the single `<p>` element that *immediately*
follows an `<h2>` element.

### Column combinator

There is also a [column combinator](column_combinator.md), denoted by
two pipe characters (`||`), which, when supported, selects nodes that
belong to a column. For example, `col || td` will match all
[`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td)
elements that belong to the scope of the
[`<col>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col).

### Namespace separator

The [namespace separator](namespace_separator.md) is another combinator
that is generally used in conjunction with the
[`@namespace`](@namespace.md) at-rule. This combinator is denoted by a
single pipe character (`|`). It enables limiting [](type_selectors.md) and the [](universal_selectors.md) to a specific namespace. For example,
by defining a namespace such as
`@namespace SVG url('http://www.w3.org/2000/svg');`, you can include
selectors that target elements nested in an SVG namespace only.
Declaring `SVG|a` would match links within SVGs and not those in the
rest of the document. Namespacing can be useful to target MathML, SVG,
or other XML-based content within your HTML.

#### CSS

In this example, we declare five [](selector_structure.md#relative_selector) using [](selector_structure.md#simple_selector) combined with
combinators.

[css]

```css
h2 + p ~ p {
  font-style: italic;
}
h2 + p + p {
  color: red;
}
.myClass + p {
  text-decoration: underline;
}
#myId > .myClass {
  outline: 3px dashed red;
}
> p {
  font-size: 1.1rem;
}
```

#### HTML

[html]

```html
<h2 class="myClass" id="myId">
  No selectors match. <span class="myClass">This span has an outline</span> as
  it is both myClass and a child of #myId.
</h2>
<p>The first paragraph is underlined. All the paragraphs are 1.1rem.</p>
<p>
  The second paragraph is red. This and the following paragraphs are italic.
</p>
<p>The third paragraph is NOT red. It is italic and 1.1rem.</p>
<p class="myClass">
  Does not have an outline; this is a sibling of H2, not a child. It is italic
  and 1.1rem.
</p>
```

#### Result

### Creating complex selectors with CSS nesting

The above complex selectors can also be defined using simple selectors,
combinators, and [CSS nesting](css_nesting.md), with or without the [](nesting_selector.md).

#### CSS

In this example, we replicate the same five relative selectors using
simple selectors combined with combinators, but this time with CSS
nesting.

[css]

```css
h2 {
  & + p {
    & ~ p {
      font-style: italic;
    }
    & + p {
      color: red;
    }
  }
}
.myClass {
  & + p {
    text-decoration: underline;
  }
}
#myId {
  & > .myClass {
    outline: 3px dashed red;
  }
}
> p {
  font-size: 1.1rem;
}
```

#### HTML

[html]

```html
<h2 class="myClass" id="myId">
  No selectors match. <span class="myClass">This span has an outline</span> as
  it is both myClass and a child of #myId.
</h2>
<p>The first paragraph is underlined. All the paragraphs are 1.1rem.</p>
<p>
  The second paragraph is red. This and the following paragraphs are italic.
</p>
<p>The third paragraph is NOT red. It is italic and 1.1rem.</p>
<p class="myClass">
  Does not have an outline; this is a sibling of H2, not a child. It is italic
  and 1.1rem.
</p>
```

#### Result

Attribute selectors
-------------------

[Attribute selectors](attribute_selectors.md) select all elements that,
depending on how the selector is written, either have the given
attribute or have the given attribute with a substring value match. For
example, `[type]` will match all elements that have the `type` attribute
set (to any value), and `[type="submit"]` will match
`<input type="submit">` and `<button type="submit">`, or any element
with `type="submit"` set, even though this attribute-value pair is only
supported on
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
and
[`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)
elements. The match is case-insensitive.

The case sensitivity of the attribute depends on the language.
Generally, in HTML, if an attribute is
[enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated),
the value in the selector is case-insensitive, even if the value is not
one of the enumerated values or if the attribute is not a valid value
for the element on which it is set. For non-enumerated attributes, like
`class`, `id`, or any `data-*` attribute, or for non-HTML attributes,
like `role` or `aria-*` attributes, the value match is case-sensitive;
the match can be made case-insensitive with a case-insensitive modifier
(`i`).

Pseudo-class selectors
----------------------

The [CSS selectors](css_selectors.md) module defines over 60
[pseudo-classes](pseudo-classes.md). Pseudo-classes are [simple
selectors](#simple-selector), prefixed with a colon (`:`), that allow
the selection of elements based on state information that is not
contained in the document tree. [`pseudo-classes`](pseudo-classes.md)
can be used to style an element based on its *state*. For example, the
[`:target`](../:target) simple selector targets element of a URL
containing a fragment identifier, and the [`a:visited`](../:visited)
[compound selector](selector_structure.md#compound_selector) matches all
[`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)
elements that have been visited by a user.

The pseudo-classes can be categorized as [](pseudo-classes.md#element_display_state_pseudo-classes),
[input](pseudo-classes.md#input_pseudo-classes),
[linguistic](pseudo-classes.md#linguistic_pseudo-classes),
[location](pseudo-classes.md#location_pseudo-classes), [](pseudo-classes.md#resource_state_pseudo-classes),
[time-dimensional](pseudo-classes.md#time-dimensional_pseudo-classes),
[tree-structural](pseudo-classes.md#tree-structural_pseudo-classes),
[user action](pseudo-classes.md#user_action_pseudo-classes), and
[functional](pseudo-classes.md#functional_pseudo-classes).

Multiple pseudo-classes can be combined to create [compound
selectors](#compound-selector). When combining a pseudo-class into a
compound selector with a type or universal selector, the pseudo-class
must follow the type selector or universal selector, if present.

Pseudo-element selectors
------------------------

Not all CSS selectors are defined in the [CSS selectors
module](https://developer.mozilla.org/en-US/docs/Web/CSS). CSS
pseudo-element selectors are defined in the [](css_pseudo-elements.md) module.

CSS [pseudo-elements](pseudo-elements.md), prefixed with two colons
(`::`), represent entities that are not included in HTML. For example,
the simple [`::marker`](../::marker) selector selects list item bullets,
and the compound selector [`p::first-line`](../::first-line) matches the
first line of all
[`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)
elements.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Selectors Level 4\
  ](https://drafts.csswg.org/selectors/)

[CSS Pseudo-Elements Module Level 4\
  ](https://drafts.csswg.org/css-pseudo/)
  -----------------------------------------------------------------------

See the [pseudo-classes](pseudo-classes.md#specifications) and
[pseudo-elements](pseudo-elements.md#specifications) specification
tables for details on those.

See also
--------

- [Selector list](selector_list.md)
- [CSS selector structure](selector_structure.md)
- [Specificity](specificity.md)
- [CSS nesting module](css_nesting.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators>
