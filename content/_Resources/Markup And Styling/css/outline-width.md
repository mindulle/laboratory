outline-width
=============

The [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
`outline-width` property sets the thickness of an element\'s outline. An
outline is a line that is drawn around an element, outside the
[`border`](border.md).

Try it
------

It is often more convenient to use the shorthand property
[`outline`](outline.md) when defining the appearance of an outline.

Syntax
------

[css]

```css
/* Keyword values */
outline-width: thin;
outline-width: medium;
outline-width: thick;

/* <length> values */
outline-width: 1px;
outline-width: 0.1em;

/* Global values */
outline-width: inherit;
outline-width: initial;
outline-width: revert;
outline-width: revert-layer;
outline-width: unset;
```

The `outline-width` property is specified as any one of the values
listed below.

### Values

[`<length>`](length.md)

:   The width of the outline specified as a `<length>`.

[`thin`](#thin)

:   Depends on the user agent. Typically equivalent to `1px` in desktop
    browsers (including Firefox).

[`medium`](#medium)

:   Depends on the user agent. Typically equivalent to `3px` in desktop
    browsers (including Firefox).

[`thick`](#thick)

:   Depends on the user agent. Typically equivalent to `5px` in desktop
    browsers (including Firefox).

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `medium`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   an absolute length; if the keyword `none` is specified, the computed value is `0`
  Animation type                     a [length](length.md#interpolation)
  ---------------------------------- -----------------------------------------------------------------------------------

Formal syntax
-------------

```
outline-width = 
  <line-width>  

<line-width> = 
  <length [0,∞]>  |
  thin            |
  medium          |
  thick           
```

Examples
--------

### Setting an element\'s outline width

#### HTML

[html]

```html
<span id="thin">thin</span>
<span id="medium">medium</span>
<span id="thick">thick</span>
<span id="twopixels">2px</span>
<span id="oneex">1ex</span>
<span id="em">1.2em</span>
```

#### CSS

[css]

```css
span {
  outline-style: solid;
  display: inline-block;
  margin: 20px;
}

#thin {
  outline-width: thin;
}

#medium {
  outline-width: medium;
}

#thick {
  outline-width: thick;
}

#twopixels {
  outline-width: 2px;
}

#oneex {
  outline-width: 1ex;
}

#em {
  outline-width: 1.2em;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------

  [CSS Basic User Interface Module Level 4\
  [\#
  outline-width]](https://drafts.csswg.org/css-ui/#outline-width)

  -------------------------------------------------------------------------

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

`outline-width`

1

12

1.5Before Firefox 88, an outline does not follow the shape of
`border-radius`.

1--3.6

8

7

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

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/outline-width>
