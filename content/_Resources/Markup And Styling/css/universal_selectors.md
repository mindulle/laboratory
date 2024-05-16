Universal selectors
===================

The CSS **universal selector** (`*`) matches elements of any type.

[css]

```css
/* Selects all elements */
* {
  color: green;
}
```

The universal selector is a special [type selector](type_selectors.md) and
can therefore be namespaced when using [`@namespace`](@namespace.md). This
is useful when dealing with documents containing multiple namespaces
such as HTML with inline SVG or MathML, or XML that mixes multiple
vocabularies.

- `ns|*` - matches all elements in namespace *ns*
- `*|*` - matches all elements
- `|*` - matches all elements without any declared namespace

Syntax
------

[css]

```css
* 
```

The asterisk is optional with simple selectors. For instance,
`*.warning` and `.warning` are equivalent.

Examples
--------

### CSS

[css]

```css
* [lang^="en"] {
  color: green;
}

*.warning {
  color: red;
}

*#maincontent {
  border: 1px solid blue;
}

.floating {
  float: left;
}

/* automatically clear the next sibling after a floating element */
.floating + * {
  clear: left;
}
```

### HTML

[html]

```html
<p class="warning">
  <span lang="en-us">A green span</span> in a red paragraph.
</p>
<p id="maincontent" lang="en-gb">
  <span class="warning">A red span</span> in a green paragraph.
</p>
```

### Result

### Namespaces

In this example the selector will only match elements in the example
namespace.

[css]

```css
@namespace example url(http://www.example.com);
example|* {
  color: blue;
}
```

Specifications
--------------

  ----------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  the-universal-selector]](https://drafts.csswg.org/selectors/#the-universal-selector)

  ----------------------------------------------------------------------------------------------

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

`Universal_selectors`

1

12

1

7

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

- [CSS selectors](css_selectors.md) module
- [Learn CSS:
    Selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors>
