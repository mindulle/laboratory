:first-of-type
==============

The `:first-of-type`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents the first element of its type
among a group of sibling elements.

Try it
------

Syntax
------

[css]

```css
:first-of-type {
  /* ... */
}
```

Examples
--------

### Styling the first paragraph

#### HTML

[html]

```html
<h2>Heading</h2>
<p>Paragraph 1</p>
<p>Paragraph 2</p>
```

#### CSS

[css]

```css
p:first-of-type {
  color: red;
  font-style: italic;
}
```

#### Result

### Nested elements

This example shows how nested elements can also be targeted. Note that
the [universal selector](universal_selectors.md) (`*`) is implied when no
type selector is written.

#### HTML

[html]

```html
<article>
  <div>This `div` is first!</div>
  <div>This <span>nested `span` is first</span>!</div>
  <div>
    This <em>nested `em` is first</em>, but this <em>nested `em` is last</em>!
  </div>
  <div>This <span>nested `span` gets styled</span>!</div>
  <p>This `p` qualifies!</p>
  <div>This is the final `div`.</div>
</article>
```

#### CSS

[css]

```css
article :first-of-type {
  background-color: pink;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  first-of-type-pseudo]](https://drafts.csswg.org/selectors/#first-of-type-pseudo)

  ------------------------------------------------------------------------------------------

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

`:first-of-type`

1

12Before Edge 16, Microsoft Edge treats all unknown elements (such as
custom elements) as the same element type.

3.5

9Internet Explorer treats all unknown elements (such as custom elements)
as the same element type.

9.5

3.1

2

18

4

10.1

2

1.0

See also
--------

- [`:first-child`](:first-child), [`:last-of-type`](:last-of-type),
    [`:nth-of-type`](:nth-of-type)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:first-of-type>
