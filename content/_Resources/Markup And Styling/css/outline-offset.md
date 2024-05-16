outline-offset
==============

The `outline-offset` CSS property sets the amount of space between an
[outline](outline.md) and the edge or border of an element.

Try it
------

Syntax
------

[css]

```css
/* <length> values */
outline-offset: 3px;
outline-offset: 0.2em;

/* Global values */
outline-offset: inherit;
outline-offset: initial;
outline-offset: revert;
outline-offset: revert-layer;
outline-offset: unset;
```

### Values

`<length>`

:   The width of the space between the element and its outline. A
    negative value places the outline inside the element. A value of `0`
    places the outline so that there is no space between it and the
    element.

Description
-----------

An outline is a line that is drawn around an element, outside the border
edge. The space between an element and its outline is transparent. In
other words, it is the same as the parent element\'s background.

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified, but with relative lengths converted into absolute lengths
  Animation type                     a [length](length.md#interpolation)
  ---------------------------------- -------------------------------------------------------------------------

Formal syntax
-------------

```
outline-offset = 
  <length>  
```

Examples
--------

### Setting outline offset in pixels

#### HTML

[html]

```html
<p>Gallia est omnis divisa in partes tres.</p>
```

#### CSS

[css]

```css
p {
  outline: 1px dashed red;
  outline-offset: 10px;
  background: yellow;
  border: 1px solid blue;
  margin: 15px;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------

  [CSS Basic User Interface Module Level 4\
  [\#
  outline-offset]](https://drafts.csswg.org/css-ui/#outline-offset)

  ---------------------------------------------------------------------------

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

`outline-offset`

1

15

1.5Before Firefox 88, an outline does not follow the shape of
`border-radius`.

No

9.5

1.2

37

18

4Before Firefox 88, an outline does not follow the shape of
`border-radius`.

14

1

1.0

See also
--------

- [`outline`](outline.md)
- [`outline-color`](outline-color.md)
- [`outline-style`](outline-style.md)
- [`outline-width`](outline-width.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset>
