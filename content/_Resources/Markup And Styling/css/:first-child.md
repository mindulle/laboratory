:first-child
============

The `:first-child`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents the first element among a
group of sibling elements.

Try it
------

Syntax
------

[css]

```css
:first-child {
  /* ... */
}
```

Examples
--------

### Basic example

#### HTML

[html]

```html
<div>
  <p>This text is selected!</p>
  <p>This text isn't selected.</p>
</div>

<div>
  <h2>This text isn't selected: it's not a `p`.</h2>
  <p>This text isn't selected.</p>
</div>
```

#### CSS

[css]

```css
p:first-child {
  color: lime;
  background-color: black;
  padding: 5px;
}
```

#### Result

### Styling a list

#### HTML

[html]

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>
    Item 3
    <ul>
      <li>Item 3.1</li>
      <li>Item 3.2</li>
      <li>Item 3.3</li>
    </ul>
  </li>
</ul>
```

#### CSS

[css]

```css
ul li {
  color: blue;
}

ul li:first-child {
  color: red;
  font-weight: bold;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  first-child-pseudo]](https://drafts.csswg.org/selectors/#first-child-pseudo)

  --------------------------------------------------------------------------------------

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

`:first-child`

4

12

3

7\[\"Internet Explorer 7 doesn\'t update `:first-child` styles when
elements are added dynamically.\", \"In Internet Explorer 8, if an
element is inserted dynamically by clicking on a link, then the
`:first-child` style isn\'t applied until the link loses focus.\"\]

9.5

3.1

≤37

18

4

10.1

4

1.0

`no_parent_required`

57

79

52

No

44

No

57

57

52

43

No

7.0

See also
--------

- [`:-moz-first-node`](:-moz-first-node)
    [Non-standard]
- [`:first-of-type`](:first-of-type)
- [`:last-child`](:last-child)
- [`:nth-child()`](:nth-child)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:first-child>
