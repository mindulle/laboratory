\<var\>: The Variable element
=============================

The `<var>` [HTML](../index) element represents the name of a variable
in a mathematical expression or a programming context. It\'s typically
presented using an italicized version of the current typeface, although
that behavior is browser-dependent.

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

### Related elements

Other elements that are used in contexts in which `<var>` is commonly
used include:

- [`<code>`](code): The HTML Code element
- [`<kbd>`](kbd): The HTML Keyboard input element
- [`<samp>`](samp): The HTML Sample Output element

If you encounter code that is mistakenly using `<var>` for style
purposes rather than semantic purposes, you should either use a
[`<span>`](span) with appropriate CSS or, an appropriate semantic
element among the following:

- [`<em>`](em)
- [`<i>`](i)
- [`<q>`](q)

### Default style

Most browsers apply
[`font-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style)
to `"italic"` when rendering `<var>`. This can be overridden in CSS,
like this:

[css]

```css
var {
  font-style: normal;
}

```

Examples
--------

### Basic example

Here\'s a simple example, using `<var>` to denote variable names in a
mathematical equation.

[html]

```html
<p>A simple equation: <var>x</var> = <var>y</var> + 2</p>
```

#### Result

### Overriding the default style

Using CSS, you can override the default style for the `<var>` element.
In this example, variable names are rendered using bold Courier if it\'s
available, otherwise it falls back to the default monospace font.

#### CSS

[css]

```css
var {
  font:
    bold 15px "Courier",
    "Courier New",
    monospace;
}

```

#### HTML

[html]

```html
<p>
  The variables <var>minSpeed</var> and <var>maxSpeed</var> control the minimum
  and maximum speed of the apparatus in revolutions per minute (RPM).
</p>
```

This HTML uses `<var>` to enclose the names of two variables.

#### Result

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-var-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-var-element)

  -------------------------------------------------------------------------------------------------------------

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

`var`

1

12

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/var>>
