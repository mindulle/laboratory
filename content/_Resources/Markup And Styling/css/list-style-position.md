list-style-position
===================

The `list-style-position`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the position of the [`::marker`](::marker) relative to a list item.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
list-style-position: inside;
list-style-position: outside;

/* Global values */
list-style-position: inherit;
list-style-position: initial;
list-style-position: revert;
list-style-position: revert-layer;
list-style-position: unset;
```

The `list-style-position` property is specified as one of the keyword
values listed below.

### Values

[`inside`](#inside)

:   The [`::marker`](::marker) is the first element among the list
    item\'s contents.

[`outside`](#outside)

:   The [`::marker`](::marker) is outside the principal block box.

Description
-----------

This property is applied to list items, i.e., elements with `display`:
list-item;. [By
default](https://html.spec.whatwg.org/multipage/rendering.html#lists)
this includes
[`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li)
elements. Because this property is inherited, it can be set on the
parent element (normally
[`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol)
or
[`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul))
to let it apply to all list items.

If a block element is the first child of a list element declared as
`list-style-position: inside`, then the block element is placed on the
line after the marker-box.

It is often more convenient to use the shorthand
[`list-style`](list-style.md).

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `outside`
  Applies to                         list items
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
list-style-position = 
  inside   |
  outside  
```

Examples
--------

### Setting list item position

#### HTML

[html]

```html
<ul class="inside">
  List 1
  <li>List Item 1-1</li>
  <li>List Item 1-2</li>
  <li>List Item 1-3</li>
  <li>List Item 1-4</li>
</ul>
<ul class="outside">
  List 2
  <li>List Item 2-1</li>
  <li>List Item 2-2</li>
  <li>List Item 2-3</li>
  <li>List Item 2-4</li>
</ul>
<ul class="inside-img">
  List 3
  <li>List Item 3-1</li>
  <li>List Item 3-2</li>
  <li>List Item 3-3</li>
  <li>List Item 3-4</li>
</ul>
```

#### CSS

[css]

```css
.inside {
  list-style-position: inside;
  list-style-type: square;
}

.outside {
  list-style-position: outside;
  list-style-type: circle;
}

.inside-img {
  list-style-position: inside;
  list-style-image: url("starsolid.gif");
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------

  [CSS Lists and Counters Module Level 3\
  [\#
  list-style-position-property]](https://drafts.csswg.org/css-lists/#list-style-position-property)

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

`list-style-position`

1

12

1

4

3.5

1

≤37

18

4

14

1

1.0

See also
--------

- [`list-style`](list-style.md), [`list-style-type`](list-style-type.md),
    [`list-style-image`](list-style-image.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-position>
