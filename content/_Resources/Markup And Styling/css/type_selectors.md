Type selectors
==============

The CSS **type selector** matches elements by node name. In other words,
it selects all elements of the given type within a document.

[css]

```css
/* All <a> elements. */
a {
  color: red;
}
```

Type selectors can be namespaced when using [`@namespace`](@namespace.md).
This is useful when dealing with documents containing multiple
namespaces such as HTML with inline SVG or MathML, or XML that mixes
multiple vocabularies.

- `ns|h1` - matches `<h1>` elements in namespace *ns*
- `*|h1` - matches all `<h1>` elements
- `|h1` - matches all `<h1>` elements without any declared namespace

Syntax
------

[css]

```css
element 
```

Examples
--------

### CSS

[css]

```css
span {
  background-color: skyblue;
}
```

### HTML

[html]

```html
<span>Here's a span with some text.</span>
<p>Here's a p with some text.</p>
<span>Here's a span with more text.</span>
```

### Result

### Namespaces

In this example the selector will only match `<h1>` elements in the
example namespace.

[css]

```css
@namespace example url(http://www.example.com);
example|h1 {
  color: blue;
}
```

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  type-selectors]](https://drafts.csswg.org/selectors/#type-selectors)

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

`Type_selectors`

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

`namespaces`

1

12

1

9

8

1.3

≤37

18

4

10.1

1

1.0

See also
--------

- [CSS Selectors](css_selectors.md)
- [Learn CSS:
    Selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors>
