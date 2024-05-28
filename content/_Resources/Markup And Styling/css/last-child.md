:last-child
===========

The `:last-child`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents the last element among a group
of sibling elements.

Try it
------

Syntax
------

[css]

```css
:last-child {
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
  <p>This text isn't selected.</p>
  <p>This text is selected!</p>
</div>

<div>
  <p>This text isn't selected.</p>
  <h2>This text isn't selected: it's not a `p`.</h2>
</div>
```

#### CSS

[css]

```css
p:last-child {
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

ul li:last-child {
  border: 1px solid red;
  color: red;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  the-last-child-pseudo]](https://drafts.csswg.org/selectors/#the-last-child-pseudo)

  --------------------------------------------------------------------------------------------

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

`:last-child`

1

12

1

9

9.5

3.1

≤37

18

4

10.1

2

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

- [`:-moz-last-node`](:-moz-last-node)
    [Non-standard]
- [`:last-of-type`](:last-of-type)
- [`:first-child`](:first-child)
- [`:nth-child`](:nth-child)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:last-child>
