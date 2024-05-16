list-style-image
================

The `list-style-image`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets an
image to be used as the list item marker.

It is often more convenient to use the shorthand
[`list-style`](list-style.md).

Try it
------

**Note:** This property is applied to list items, i.e. elements with
`display`: list-item; [by
default](https://html.spec.whatwg.org/multipage/rendering.html#lists)
this includes
[`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li)
elements. Because this property is inherited, it can be set on the
parent element (normally
[`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol)
or
[`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul))
to let it apply to all list items.

Syntax
------

[css]

```css
/* Keyword values */
list-style-image: none;

/* <url> values */
list-style-image: url("starsolid.gif");

/* valid image values */
list-style-image: linear-gradient(to left bottom, red, blue);

/* Global values */
list-style-image: inherit;
list-style-image: initial;
list-style-image: revert;
list-style-image: revert-layer;
list-style-image: unset;
```

### Values

[`<image>`](_Resources/Markup%20And%20Styling/css/image.md)

:   A valid image to use as the marker.

[`none`](#none)

:   Specifies that no image is used as the marker. If this value is set,
    the marker defined in [`list-style-type`](list-style-type.md) will be
    used instead.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         list items
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   The keyword `none` or the computed \<image\>
  Animation type                     discrete
  ---------------------------------- ----------------------------------------------

Formal syntax
-------------

```
list-style-image = 
  <image>  |
  none     

<image> = 
  <url>       |
  <gradient>  

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  
```

Examples
--------

### Using a url value

#### HTML

[html]

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>
```

#### CSS

[css]

```css
ul {
  list-style-image: url("starsolid.gif");
}
```

#### Result

### Using a gradient

#### HTML

[html]

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>
```

#### CSS

[css]

```css
ul {
  font-size: 200%;
  list-style-image: linear-gradient(to left bottom, red, blue);
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------

  [CSS Lists and Counters Module Level 3\
  [\#
  image-markers]](https://drafts.csswg.org/css-lists/#image-markers)

  ----------------------------------------------------------------------------

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

`list-style-image`

1

12

1Before Firefox 86, this property did not accept an `<image>` type, and
required the URL of an image.

4

7

1

4.4

18

4Before Firefox 86, this property did not accept an `<image>` type, and
required the URL of an image.

10.1

1

1.0

See also
--------

- [`list-style`](list-style.md), [`list-style-type`](list-style-type.md),
    [`list-style-position`](list-style-position.md)
- [`url()`](url.md) function

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-image>
