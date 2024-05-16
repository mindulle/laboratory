border-style
============

The `border-style` [shorthand](shorthand_properties.md)
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the line style for all four sides of an element\'s border.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`border-bottom-style`](border-bottom-style.md)
- [`border-left-style`](border-left-style.md)
- [`border-right-style`](border-right-style.md)
- [`border-top-style`](border-top-style.md)

Syntax
------

[css]

```css
/* Keyword values */
border-style: none;
border-style: hidden;
border-style: dotted;
border-style: dashed;
border-style: solid;
border-style: double;
border-style: groove;
border-style: ridge;
border-style: inset;
border-style: outset;

/* top and bottom | left and right */
border-style: dotted solid;

/* top | left and right | bottom */
border-style: hidden double dashed;

/* top | right | bottom | left */
border-style: none solid dotted dashed;

/* Global values */
border-style: inherit;
border-style: initial;
border-style: revert;
border-style: revert-layer;
border-style: unset;
```

The `border-style` property may be specified using one, two, three, or
four values.

- When **one** value is specified, it applies the same style to **all
    four sides**.
- When **two** values are specified, the first style applies to the
    **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first style applies to the
    **top**, the second to the **left and right**, the third to the
    **bottom**.
- When **four** values are specified, the styles apply to the **top**,
    **right**, **bottom**, and **left** in that order (clockwise).

Each value is a keyword chosen from the list below.

### Values

[`<line-style>`](#line-style)

:   Describes the style of the border. It can have the following values:

    [`none`](#none)

    :   Like the `hidden` keyword, displays no border. Unless a
        [`background-image`](background-image) is set, the computed
        value of the same side\'s [`border-width`](border-width) will be
        `0`, even if the specified value is something else. In the case
        of table cell and border collapsing, the `none` value has the
        *lowest* priority: if any other conflicting border is set, it
        will be displayed.

    [`hidden`](#hidden)

    :   Like the `none` keyword, displays no border. Unless a
        [`background-image`](background-image) is set, the computed
        value of the same side\'s [`border-width`](border-width) will be
        `0`, even if the specified value is something else. In the case
        of table cell and border collapsing, the `hidden` value has the
        *highest* priority: if any other conflicting border is set, it
        won\'t be displayed.

    [`dotted`](#dotted)

    :   Displays a series of rounded dots. The spacing of the dots is
        not defined by the specification and is implementation-specific.
        The radius of the dots is half the computed value of the same
        side\'s [`border-width`](border-width).

    [`dashed`](#dashed)

    :   Displays a series of short square-ended dashes or line segments.
        The exact size and length of the segments are not defined by the
        specification and are implementation-specific.

    [`solid`](#solid)

    :   Displays a single, straight, solid line.

    [`double`](#double)

    :   Displays two straight lines that add up to the pixel size
        defined by [`border-width`](border-width).

    [`groove`](#groove)

    :   Displays a border with a carved appearance. It is the opposite
        of `ridge`.

    [`ridge`](#ridge)

    :   Displays a border with an extruded appearance. It is the
        opposite of `groove`.

    [`inset`](#inset)

    :   Displays a border that makes the element appear embedded. It is
        the opposite of `outset`. When applied to a table cell with
        [`border-collapse`](border-collapse) set to `collapsed`, this
        value behaves like `ridge`.

    [`outset`](#outset)

    :   Displays a border that makes the element appear embossed. It is
        the opposite of `inset`. When applied to a table cell with
        [`border-collapse`](border-collapse) set to `collapsed`, this
        value behaves like `groove`.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-top-style.md): |
|                                   |     `none`                        |
|                                   | -   [](border-right-style.md): |
|                                   |     `none`                        |
|                                   | -   [](border-bottom-style.md): |
|                                   |     `none`                        |
|                                   | -   [](border-left-style.md): |
|                                   |     `none`                        |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements. It also applies to  |
|                                   | [`|
|                                   | ::first-letter`](::first-letter). |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-bottom-style.md): |
|                                   |     as specified                  |
|                                   | -   [](border-left-style.md): |
|                                   |     as specified                  |
|                                   | -   [](border-right-style.md): |
|                                   |     as specified                  |
|                                   | -   [](border-top-style.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | discrete                          |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
border-style = 
  <line-style>  

<line-style> = 
  none    |
  hidden  |
  dotted  |
  dashed  |
  solid   |
  double  |
  groove  |
  ridge   |
  inset   |
  outset  
```

Examples
--------

### All property values

Here is an example of all the property values.

#### HTML

[html]

```html
<pre class="b1">none</pre>
<pre class="b2">hidden</pre>
<pre class="b3">dotted</pre>
<pre class="b4">dashed</pre>
<pre class="b5">solid</pre>
<pre class="b6">double</pre>
<pre class="b7">groove</pre>
<pre class="b8">ridge</pre>
<pre class="b9">inset</pre>
<pre class="b10">outset</pre>
```

#### CSS

[css]

```css
pre {
  height: 80px;
  width: 120px;
  margin: 20px;
  padding: 20px;
  display: inline-block;
  background-color: palegreen;
  border-width: 5px;
  box-sizing: border-box;
}

/* border-style example classes */
.b1 {
  border-style: none;
}

.b2 {
  border-style: hidden;
}

.b3 {
  border-style: dotted;
}

.b4 {
  border-style: dashed;
}

.b5 {
  border-style: solid;
}

.b6 {
  border-style: double;
}

.b7 {
  border-style: groove;
}

.b8 {
  border-style: ridge;
}

.b9 {
  border-style: inset;
}

.b10 {
  border-style: outset;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  border-style]](https://drafts.csswg.org/css-backgrounds/#border-style)

  --------------------------------------------------------------------------------

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

`border-style`

1

12

1Before Firefox 50, border styles of rounded corners were always
rendered as if `border-style` was solid. This has been fixed in Firefox
50.

4

3.5

1

3

18

4Before Firefox 50, border styles of rounded corners were always
rendered as if `border-style` was solid. This has been fixed in Firefox
50.

14

3

1.0

See also
--------

- The border-related shorthand CSS properties: [`border`](border.md),
    [`border-width`](border-width.md), [`border-color`](border-color.md),
    [`border-radius`](border-radius.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-style>
