Next-sibling combinator
=======================

The **next-sibling combinator** (`+`) separates two selectors and
matches the second element only if it *immediately* follows the first
element, and both are children of the same parent
[`element`](https://developer.mozilla.org/en-US/docs/Web/API/Element).

[css]

```css
/* Paragraphs that come immediately after any image */
img + p {
  font-weight: bold;
}
```

Syntax
------

[css]

```css
/* The white space around the + combinator is optional but recommended. */
former_element + target_element 
```

Examples
--------

### CSS

[css]

```css
li:first-of-type + li {
  color: red;
}
```

### HTML

[html]

```html
<ul>
  <li>One</li>
  <li>Two!</li>
  <li>Three</li>
</ul>
```

### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  adjacent-sibling-combinators]](https://drafts.csswg.org/selectors/#adjacent-sibling-combinators)

  ----------------------------------------------------------------------------------------------------------

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

`Next-sibling_combinator`

1

12

1

7\[\"Before Internet Explorer 10, the combinator only works in standards
mode.\", \"Internet Explorer 7 doesn\'t update the style correctly when
an element is dynamically placed before an element that matched the
selector.\", \"In Internet Explorer 8, if an element is inserted
dynamically by clicking on a link the first-child style isn\'t applied
until the link loses focus.\"\]

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

- [Subsequent-sibling combinator](subsequent-sibling_combinator.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Next-sibling_combinator>
