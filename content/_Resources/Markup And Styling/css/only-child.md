:only-child
===========

The `:only-child` CSS [pseudo-class](pseudo-classes.md) represents an
element without any siblings. This is the same as
`:first-child:last-child` or `:nth-child(1):nth-last-child(1)`, but with
a lower specificity.

Try it
------

**Note:** As originally defined, the selected element had to have a
parent. Beginning with Selectors Level 4, this is no longer required.

Syntax
------

[css]

```css
:only-child {
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
  <div>I am an only child.</div>
</div>

<div>
  <div>I am the 1st sibling.</div>
  <div>I am the 2nd sibling.</div>
  <div>
    I am the 3rd sibling,
    <div>but this is an only child.</div>
  </div>
</div>
```

#### CSS

[css]

```css
div:only-child {
  color: red;
}

div {
  display: inline-block;
  margin: 6px;
  outline: 1px solid;
}
```

#### Result

### A list example

#### HTML

[html]

```html
<ol>
  <li>
    First
    <ul>
      <li>This list has just one element.</li>
    </ul>
  </li>
  <li>
    Second
    <ul>
      <li>This list has three elements.</li>
      <li>This list has three elements.</li>
      <li>This list has three elements.</li>
    </ul>
  </li>
</ol>
```

#### CSS

[css]

```css
li li {
  list-style-type: disc;
}

li:only-child {
  color: red;
  list-style-type: square;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  only-child-pseudo]](https://drafts.csswg.org/selectors/#only-child-pseudo)

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

`:only-child`

2

12

1.5

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

- [`:only-of-type`](:only-of-type)
- [`:first-child`](:first-child)
- [`:last-child`](:last-child)
- [`:nth-child`](:nth-child)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:only-child>
