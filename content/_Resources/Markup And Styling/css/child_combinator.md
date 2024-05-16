Child combinator
================

The **child combinator** (`>`) is placed between two CSS selectors. It
matches only those elements matched by the second selector that are the
direct children of elements matched by the first.

[css]

```css
/* List items that are children of the "my-things" list */
ul.my-things > li {
  margin: 2em;
}
```

Elements matched by the second selector must be the immediate children
of the elements matched by the first selector. This is stricter than the
[descendant combinator](descendant_combinator.md), which matches all
elements matched by the second selector for which there exists an
ancestor element matched by the first selector, regardless of the number
of \"hops\" up the DOM.

Syntax
------

[css]

```css
/* The white space around the > combinator is optional but recommended. */
selector1 > selector2 
```

Examples
--------

### CSS

[css]

```css
span {
  background-color: aqua;
}

div > span {
  background-color: yellow;
}
```

### HTML

[html]

```html
<div>
  <span>
    Span #1, in the div.
    <span>Span #2, in the span that's in the div.</span>
  </span>
</div>
<span>Span #3, not in the div at all.</span>
```

### Result

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  child-combinators]](https://drafts.csswg.org/selectors/#child-combinators)

  ------------------------------------------------------------------------------------

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

`Child_combinator`

1

12

1

7Before Internet Explorer 10, the combinator only works in standards
mode.

4

1

≤37

18

4

10.1

1

1.0

See also
--------

- [Descendant combinator](descendant_combinator.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Child_combinator>
