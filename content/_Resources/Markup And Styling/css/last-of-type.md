:last-of-type
=============

The `:last-of-type`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents the last element of its type
among a group of sibling elements.

Try it
------

Syntax
------

[css]

```css
:last-of-type {
  /* ... */
}
```

Examples
--------

### Styling the last paragraph

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
p:last-of-type {
  color: red;
  font-style: italic;
}
```

#### Result

### Nested elements

This example shows how nested elements can also be targeted. Note that
the [universal selector](universal_selectors.md) (`*`) is implied when no
simple selector is written.

#### HTML

[html]

```html
<article>
  <div>This `div` is first.</div>
  <div>This <span>nested `span` is last</span>!</div>
  <div>
    This <em>nested `em` is first</em>, but this <em>nested `em` is last</em>!
  </div>
  <p>This `p` qualifies!</p>
  <div>This is the final `div`!</div>
</article>
```

#### CSS

[css]

```css
article :last-of-type {
  background-color: pink;
}
```

#### Result

### Multiple selectors elements

This HTML example contains nested elements of different types. The CSS
contains both type selectors and class selectors.

#### HTML

[html]

```html
<p>This `p` is not selected.</p>
<p>This `p` is not selected either.</p>
<p>
  This `p` is last `p` element of its parent e.g. `body` selected by `p` type
  selector.
</p>
<div class="container">
  <div class="item">This `div` is not selected.</div>
  <div class="item">This `div` is not selected either.</div>
  <div class="item">
    This `div` is last `div` element of its parent `div` selected by `.container
    .item` class selector.
  </div>
  <p class="item">
    This `p` is last `p` element of its parent `div` selected by `.container
    .item` class selector.
  </p>
</div>
```

#### CSS

[css]

```css
p:last-of-type {
  background: skyblue;
}

.container .item:last-of-type {
  color: red;
  font-weight: bold;
}
```

#### Result

The last `<div>` and the last `<p>` are both red and bold as the
`.item:last-of-type` selects the last of every type if that last element
also has the `item` class.

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  last-of-type-pseudo]](https://drafts.csswg.org/selectors/#last-of-type-pseudo)

  ----------------------------------------------------------------------------------------

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

`:last-of-type`

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

- [`:last-child`](:last-child),
    [`:nth-last-of-type`](:nth-last-of-type)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:last-of-type>
