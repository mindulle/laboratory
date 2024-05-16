outline
=======

The `outline` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[shorthand property](shorthand_properties.md) sets most of the outline
properties in a single declaration.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`outline-color`](outline-color.md)
- [`outline-style`](outline-style.md)
- [`outline-width`](outline-width.md)

Syntax
------

[css]

```css
/* style */
outline: solid;

/* color | style */
outline: #f66 dashed;

/* style | width */
outline: inset thick;

/* color | style | width */
outline: green solid 3px;

/* Global values */
outline: inherit;
outline: initial;
outline: revert;
outline: revert-layer;
outline: unset;
```

The `outline` property may be specified using one, two, or three of the
values listed below. The order of the values does not matter. As with
all shorthand properties, any omitted sub-values will be set to their
[initial value](initial_value.md).

**Note:** The outline will be invisible for many elements if its style
is not defined. This is because the style defaults to `none`. A notable
exception is `input` elements, which are given default styling by
browsers.

### Values

[`<'outline-color'>`](#outline-color)

:   Sets the color of the outline. Defaults to `invert` for browsers
    supporting it, `currentcolor` for the others. See
    [`outline-color`](outline-color.md).

[`<'outline-style'>`](#outline-style)

:   Sets the style of the outline. Defaults to `none` if absent. See
    [`outline-style`](outline-style.md).

[`<'outline-width'>`](#outline-width)

:   Sets the thickness of the outline. Defaults to `medium` if absent.
    See [`outline-width`](outline-width.md).

Description
-----------

Outline is a line outside of the element\'s [border](border.md). Unlike
other areas of the box, outlines don\'t take up space, so they don\'t
affect the layout of the document in any way.

There are a few properties that affect an outline\'s appearance. It is
possible to change the style, color, and width using the `outline`
property, the distance from the border using the
[`outline-offset`](outline-offset.md) property, and corner angles using the
[`border-radius`](border-radius.md) property.

An outline is not required to be rectangular: While dealing with
multiline text, some browsers will draw an outline for each line box
separately, while others will wrap the whole text with a single outline.

Accessibility concerns
----------------------

Assigning `outline` a value of `0` or `none` will remove the browser\'s
default focus style. If an element can be interacted with it must have a
visible focus indicator. Provide obvious focus styling if the default
focus style is removed.

- [How to Design Useful and Usable Focus
    Indicators](https://www.deque.com/blog/give-site-focus-tips-designing-usable-focus-indicators/)
- WCAG 2.1: [Understanding Success Criterion 2.4.7: Focus
    Visible](https://www.w3.org/WAI/WCAG21/Understanding/focus-visible.html)

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -                                 |
|                                   | [`outline-color`](outline-color.md): |
|                                   |     `invert`, for browsers        |
|                                   |     supporting it, `currentColor` |
|                                   |     for the other                 |
|                                   | -                                 |
|                                   | [`outline-style`](outline-style.md): |
|                                   |     `none`                        |
|                                   | -                                 |
|                                   | [`outline-width`](outline-width.md): |
|                                   |     `medium`                      |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements                      |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -                                 |
|                                   | [`outline-color`](outline-color.md): |
|                                   |     For the keyword `invert`, the |
|                                   |     computed value is `invert`.   |
|                                   |     For the color value, if the   |
|                                   |     value is translucent, the     |
|                                   |     computed value will be the    |
|                                   |     `rgba()` corresponding one.   |
|                                   |     If it isn\'t, it will be the  |
|                                   |     `rgb()` corresponding one.    |
|                                   |     The `transparent` keyword     |
|                                   |     maps to `rgba(0,0,0,0)`.      |
|                                   | -                                 |
|                                   | [`outline-width`](outline-width.md): |
|                                   |     an absolute length; if the    |
|                                   |     keyword `none` is specified,  |
|                                   |     the computed value is `0`     |
|                                   | -                                 |
|                                   | [`outline-style`](outline-style.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -                                 |
|                                   | [`outline-color`](outline-color.md): |
|                                   |     a                             |
|                                   |     [](color_value.md#interpolation) |
|                                   | -                                 |
|                                   | [`outline-width`](outline-width.md): |
|                                   |     a                             |
|                                   |                                   |
|                                   |    [length](length.md#interpolation) |
|                                   | -                                 |
|                                   | [`outline-style`](outline-style.md): |
|                                   |     by computed value type        |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
outline = 
  <'outline-color'>  ||
  <'outline-style'>  ||
  <'outline-width'>  
```

Examples
--------

### Using outline to set a focus style

#### HTML

[html]

```html
<a href="#">This link has a special focus style.</a>
```

#### CSS

[css]

```css
a {
  border: 1px solid;
  border-radius: 3px;
  display: inline-block;
  margin: 10px;
  padding: 5px;
}

a:focus {
  outline: 4px dotted #e73;
  outline-offset: 4px;
  background: #ffa;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Basic User Interface Module Level 4\
  [\# outline]](https://drafts.csswg.org/css-ui/#outline)

  -----------------------------------------------------------------------

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

`outline`

94

1--94Before Chrome 94, `outline` does not follow the shape of
`border-radius`.

94

12--94Before Edge 94, `outline` does not follow the shape of
`border-radius`.

88

1.5--88Before Firefox 88, `outline` does not follow the shape of
`border-radius`.

1--3.6

8

80

7--80Before Opera 80, `outline` does not follow the shape of
`border-radius`.

16.4

1.2--16.4Before Safari 16.4, `outline` does not follow the shape of
`border-radius`. See [bug 20807](https://webkit.org/b/20807).

94

1--94Before Chrome 94, `outline` does not follow the shape of
`border-radius`.

94

18--94Before Chrome 94, `outline` does not follow the shape of
`border-radius`.

88

4--88Before Firefox 88, `outline` does not follow the shape of
`border-radius`.

10.1

16.4

1--16.4Before Safari 16.4, `outline` does not follow the shape of
`border-radius`. See [bug 20807](https://webkit.org/b/20807).

1.0

`invert`

No

12--79

1--3

8

7--15

No

No

No

No

No

No

No

See also
--------

- [`outline-color`](outline-color.md)
- [`outline-style`](outline-style.md)
- [`outline-width`](outline-width.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/outline>
