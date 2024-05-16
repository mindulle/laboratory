Namespace separator
===================

The **namespace separator** (`|`) separates the selector from the
namespace, identifying the
[namespace](https://developer.mozilla.org/en-US/docs/Glossary/Namespace),
or lack thereof, for a type selector.

[css]

```css
/* Links in the namespace named myNameSpace */
myNameSpace|a {
  font-weight: bold;
}
/* paragraphs in any namespace (including no namespace) */
*|p {
  color: darkblue;
}
/* heading level 2 not in a namespace */
|h2 {
  margin-bottom: 0;
}
```

[Type selectors](type_selectors.md) and the [](universal_selectors.md) allow an optional namespace component.
When a namespace has been previously declared via
[`@namespace`](@namespace.md), these selectors can be namespaced by
prepending the selector with the name of the namespace separated by the
namespace separator (`|`). This is useful when dealing with documents
containing multiple namespaces such as HTML with inline SVG or MathML,
or XML that mixes multiple vocabularies.

- `ns|h1` - matches `<h1>` elements in namespace `ns`
- `*|h1` - matches all `<h1>` elements
- `|h1` - matches all `<h1>` elements outside of any declared or
    implied namespace

Syntax
------

[css]

```css
namespace|element 
```

Examples
--------

By default, all elements in an HTML or SVG element have a namespace as
the `http://www.w3.org/1999/xhtml` and `http://www.w3.org/2000/svg`
namespace are implied. The
[`document.createElementNS`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElementNS)
method, with an empty string for the namespace parameter, can be used to
create elements with no namespace.

### Named namespace example

In this example, all elements are in a namespace.

#### HTML

No namespaces are explicitly declared in the HTML or within the SVG.

[html]

```html
<p>This paragraph <a href="#">has a link</a>.</p>

<svg width="400" viewBox="0 0 400 20">
  <a href="#">
    <text x="0" y="15">Link created in SVG</text>
  </a>
</svg>
```

#### CSS

The CSS declares two namespaces, then assigns styles to links globally
(`a`), to links in no namespace (`|a`), to links in any namespace or no
namespace (`*|a`), and then to two different named namespaces
(`svgNamespace|a` and `htmlNameSpace|a`).

[css]

```css
@namespace svgNamespace url("http://www.w3.org/2000/svg");
@namespace htmlNameSpace url("http://www.w3.org/1999/xhtml");
/* All `<a>`s in the default namespace, in this case, all `<a>`s */
a {
  font-size: 1.4rem;
}
/* no namespace */
|a {
  text-decoration: wavy overline lime;
  font-weight: bold;
}
/* all namespaces (including no namespace) */
*|a {
  color: red;
  fill: red;
  font-style: italic;
}
/* only the svgNamespace namespace, which is <svg> content */
svgNamespace|a {
  color: green;
  fill: green;
}
/* The htmlNameSpace namespace, which is the HTML document */
htmlNameSpace|a {
  text-decoration-line: line-through;
}
```

#### Result

The selector `|a`, a link not in a namespace, doesn\'t match any links.
In HTML, the `http://www.w3.org/1999/xhtml` is implied, meaning all HTML
is in a namespace, even if none is explicitly declared. In SVG, even if
not explicitly set, the `http://www.w3.org/2000/svg` namespace is also
implied. This means all the content is within at least one namespace.

### Default namespace and no namespace

In this example, we use JavaScript to create an element without a
namespace and append it to the document. We set the SVG namespace to be
the default namespace by defining the unnamed namespace with
`@namespace`.

**Note:** If a default, or unnamed, namespace is defined, universal and
type selectors apply only to elements in that namespace.

#### HTML

No namespaces are explicitly declared in the HTML or within the SVG.

[html]

```html
<p><a href="#">A link</a> in the implied HTML namespace.</p>

<svg width="400" viewBox="0 0 400 20">
  <a href="#">
    <text x="0" y="15">Link created in SVG namespace</text>
  </a>
</svg>
```

#### JavaScript

With JavaScript, with
[`document.createElementNS`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElementNS),
we create an anchor link without a namespace, then append the link.

[js]

```js
// create 'no namespace' anchor
const a = document.createElementNS("", "a");
a.href = "#";
a.appendChild(document.createTextNode("Link created without a namespace"));

document.body.appendChild(a);
```

#### CSS

We declare a namespace with [`@namespace`](@namespace.md). By omitting the
name for the namespace, the `@namespace` declaration creates a default
namespace.

[css]

```css
/* By omitting a name, this sets SVG as the default namespace */
@namespace url("http://www.w3.org/2000/svg");

/* `<a>` in the default (set to SVG) namespace */
a {
  font-size: 1.4rem;
}

/* `<svg>` and `<p>` in the default (set to SVG) namespace */
svg,
p {
  border: 5px solid gold;
}

/* links outside of any namespace */
|a {
  text-decoration: wavy underline purple;
  font-weight: bold;
}

/* links with any namespace or no namespace */
*|a {
  font-style: italic;
  color: magenta;
  fill: magenta;
}
```

#### Result

The selector with no namespace separator, the `a`, matched only the SVG
`<a>` elements, as SVG was set as the default namespace.

The selector with no namespace, the `|a`, matched the JavaScript defined
and appended `<a>`, as that node is the only node that doesn\'t have a
default namespace.

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [CSS Namespaces Module Level 3\
  [\#
  declaration]](https://drafts.csswg.org/css-namespaces/#declaration)

  -----------------------------------------------------------------------------

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

`Namespace_separator`

1

12

1

9

8

3

37

18

4

14

1

1.0

See also
--------

- [`@namespace`](@namespace.md)
- [`Document.createElementNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElementNS)
    method
- [`Element.namespaceURI`](https://developer.mozilla.org/en-US/docs/Web/API/Element/namespaceURI)
    property
- [CSS type selector](type_selectors.md)
- [CSS universal selector](universal_selectors.md)
- [CSS selector module](css_selectors.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Namespace_separator>
