ID selectors
============

The CSS **ID selector** matches an element based on the value of the
element\'s
[`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/id)
attribute. In order for the element to be selected, its `id` attribute
must match exactly the value given in the selector.

[css]

```css
/* The element with id="demo" */
#demo {
  border: red 2px solid;
}
```

Syntax
------

[css]

```css
#id_value 
```

Note that syntactically (but not specificity-wise), this is equivalent
to the following [`attribute selector`](attribute_selectors.md):

[css]

```css
[id=id_value] 
```

Examples
--------

### CSS

[css]

```css
#identified {
  background-color: skyblue;
}
```

### HTML

[html]

```html
<div id="identified">This div has a special ID on it!</div>
<div>This is just a regular div.</div>
```

### Result

Specifications
--------------

  --------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  id-selectors]](https://drafts.csswg.org/selectors/#id-selectors)

  --------------------------------------------------------------------------

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

`ID_selectors`

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

See also
--------

- [CSS Selectors](css_selectors.md)
- [Learn CSS:
    Selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors>
