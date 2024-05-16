clear
=====

The `clear` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets whether an element must be moved below (cleared)
[floating](float.md) elements that precede it. The `clear` property applies
to floating and non-floating elements.

Try it
------

When applied to non-floating blocks, it moves the [](introduction_to_the_css_box_model.md#border_area) of
the element down until it is below the [](introduction_to_the_css_box_model.md#margin_area) of
all relevant floats. The non-floated block\'s top margin collapses.

Vertical margins between two floated elements on the other hand will not
collapse. When applied to floating elements, the margin edge of the
bottom element is moved below the margin edge of all relevant floats.
This affects the position of later floats, since later floats cannot be
positioned higher than earlier ones.

The floats that are relevant to be cleared are the earlier floats within
the same [block formatting
context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context).

**Note:** If an element contains only floated elements, its height
collapses to nothing. If you want it to always be able to resize, so
that it contains floating elements inside it, set the value of the
element\'s [`display`](display.md) property to
[`flow-root`](display.md#flow-root).

[css]

```css
#container {
  display: flow-root;
}
```

Syntax
------

[css]

```css
/* Keyword values */
clear: none;
clear: left;
clear: right;
clear: both;
clear: inline-start;
clear: inline-end;

/* Global values */
clear: inherit;
clear: initial;
clear: revert;
clear: revert-layer;
clear: unset;
```

### Values

[`none`](#none)

:   Is a keyword indicating that the element is *not* moved down to
    clear past floating elements.

[`left`](#left)

:   Is a keyword indicating that the element is moved down to clear past
    *left* floats.

[`right`](#right)

:   Is a keyword indicating that the element is moved down to clear past
    *right* floats.

[`both`](#both)

:   Is a keyword indicating that the element is moved down to clear past
    *both* left and right floats.

[`inline-start`](#inline-start)

:   Is a keyword indicating that the element is moved down to clear
    floats on *start side of its containing block*, that is the *left*
    floats on ltr scripts and the *right* floats on rtl scripts.

[`inline-end`](#inline-end)

:   Is a keyword indicating that the element is moved down to clear
    floats on *end side of its containing block*, that is the *right*
    floats on ltr scripts and the *left* floats on rtl scripts.

Formal definition
-----------------

  ---------------------------------- ----------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         block-level elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ----------------------

Formal syntax
-------------

```
clear = 
  inline-start  |
  inline-end    |
  block-start   |
  block-end     |
  left          |
  right         |
  top           |
  bottom        |
  none          
```

Examples
--------

### clear: left

#### HTML

[html]

```html
<div class="wrapper">
  <p class="black">
    Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Phasellus sit amet
    diam. Duis mattis varius dui. Suspendisse eget dolor.
  </p>
  <p class="red">Lorem ipsum dolor sit amet, consectetuer adipiscing elit.</p>
  <p class="left">This paragraph clears left.</p>
</div>
```

#### CSS

[css]

```css
.wrapper {
  border: 1px solid black;
  padding: 10px;
}
.left {
  border: 1px solid black;
  clear: left;
}
.black {
  float: left;
  margin: 0;
  background-color: black;
  color: #fff;
  width: 20%;
}
.red {
  float: left;
  margin: 0;
  background-color: pink;
  width: 20%;
}
p {
  width: 50%;
}
```

### clear: right

#### HTML

[html]

```html
<div class="wrapper">
  <p class="black">
    Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Phasellus sit amet
    diam. Duis mattis varius dui. Suspendisse eget dolor.
  </p>
  <p class="red">Lorem ipsum dolor sit amet, consectetuer adipiscing elit.</p>
  <p class="right">This paragraph clears right.</p>
</div>
```

#### CSS

[css]

```css
.wrapper {
  border: 1px solid black;
  padding: 10px;
}
.right {
  border: 1px solid black;
  clear: right;
}
.black {
  float: right;
  margin: 0;
  background-color: black;
  color: #fff;
  width: 20%;
}
.red {
  float: right;
  margin: 0;
  background-color: pink;
  width: 20%;
}
p {
  width: 50%;
}
```

### clear: both

#### HTML

[html]

```html
<div class="wrapper">
  <p class="black">
    Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Phasellus sit amet
    diam. Duis mattis varius dui. Suspendisse eget dolor. Fusce pulvinar lacus
    ac dui.
  </p>
  <p class="red">
    Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Phasellus sit amet
    diam. Duis mattis varius dui. Suspendisse eget dolor.
  </p>
  <p class="both">This paragraph clears both.</p>
</div>
```

#### CSS

[css]

```css
.wrapper {
  border: 1px solid black;
  padding: 10px;
}
.both {
  border: 1px solid black;
  clear: both;
}
.black {
  float: left;
  margin: 0;
  background-color: black;
  color: #fff;
  width: 20%;
}
.red {
  float: right;
  margin: 0;
  background-color: pink;
  width: 20%;
}
p {
  width: 45%;
}
```

Specifications
--------------

  --------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------

  [Cascading Style Sheets Level 2 Revision 2 (CSS 2.2) Specification\
  [\# propdef-clear]](https://drafts.csswg.org/css2/#propdef-clear)

[CSS Logical Properties and Values Level 1\
  [\#
  float-clear]](https://drafts.csswg.org/css-logical/#float-clear)
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

`clear`

1

12

1

4

3.5

1

4.4

18

4

10.1

1

1.0

`flow_relative_values`

118

118

55

No

104

15

118

118

55

No

15

No

See also
--------

- [](introduction_to_the_css_box_model.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/clear>
