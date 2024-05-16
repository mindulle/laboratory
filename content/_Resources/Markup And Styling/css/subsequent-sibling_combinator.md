Subsequent-sibling combinator
=============================

The **subsequent-sibling combinator** (`~`) separates two selectors and
matches *all instances* of the second element that follow the first
element (not necessarily immediately) and share the same parent element.

In the following example, the subsequent-sibling combinator (`~`) helps
to select and style paragraphs that are both siblings of an image and
appear after any image.

[css]

```css
img ~ p {
  color: red;
}
```

Syntax
------

[css]

```css
/* The white space around the ~ combinator is optional but recommended. */
former_element ~ target_element 
```

Examples
--------

### Using the combinator with simple selectors

This example shows the use of the `~` combinator when both the selectors
are simple selectors (`p` and `span`).

[html]

```html
<article>
  <span>This is not red because it appears before any paragraph.</span>
  <p>Here is a paragraph.</p>
  <code>Here is some code.</code>
  <span>
    This span is red because it appears after the paragraph, even though there
    are other nodes in between.
  </span>
  <p>Whatever it may be, keep smiling.</p>
  <h1>Dream big</h1>
  <span>
    Doesn't matter how many or what kind of nodes are in between, all spans from
    the same parent after a paragraph are red.
  </span>
</article>
<span>
  This span is not red because it doesn't share a parent with a paragraph.
</span>
```

[css]

```css
p ~ span {
  color: red;
}
```

### Using the combinator with complex selectors

This example contains two [](selector_structure.md#complex_selector), both
using the subsequent-sibling combinator: `.foo p ~ span` and
`.foo p ~ .foo span`.

- The first complex selector, `.foo p ~ span`, matches all spans that
    come after a paragraph *if* the span and paragraph share the same
    parent **and** that parent or an ancestor of that parent has the
    class `.foo`.
- The second complex selector, `.foo p ~ .foo span`, matches all spans
    that are a descendant of the element with class `.foo` *if* that
    element is a sibling of the previously mentioned paragraph.

The example below shows that the target element in the complex selector
must share the same parent as the initial element in the complex
selector.

[html]

```html
<h1>Dream big</h1>
<span>And yet again this is a red span!</span>
<div class="foo">
  <p>Here is another paragraph.</p>
  <span>A blue span</span>
  <div class="foo">
    <span>A green span</span>
  </div>
</div>
```

[css]

```css
.foo p ~ span {
  color: blue;
}

.foo p ~ .foo span {
  color: green;
}
```

In the above HTML, the two siblings of `.foo p` are `span` and `.foo`.
The green `span` is a descendant of the `.foo` class, which is a sibling
of `p`.

- When the target selector is `span`, the `span` element that is a
    sibling of `p` is selected. The `p` element is a descendant of
    `.foo`, so are its `span` siblings.
- In `.foo p ~ .foo span`, the target selector is `span` that is a
    descendant of `.foo`. In this case, the `span` element that\'s a
    descendent of `.foo` is selected if that `.foo` is a sibling of `p`;
    essentially, both are nested in an ancestor of `.foo`.

Specifications
--------------

  --------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  general-sibling-combinators]](https://drafts.csswg.org/selectors/#general-sibling-combinators)

  --------------------------------------------------------------------------------------------------------

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

`Subsequent-sibling_combinator`

1

12

1

7Before Internet Explorer 10, the combinator only works in standards
mode.

9

3

≤37

18

4

14

1

1.0

See also
--------

- [Next-sibling combinator](next-sibling_combinator.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Subsequent-sibling_combinator>
