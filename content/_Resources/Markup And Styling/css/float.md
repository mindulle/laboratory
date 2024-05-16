float
=====

The `float` CSS property places an element on the left or right side of
its container, allowing text and inline elements to wrap around it. The
element is removed from the normal flow of the page, though still
remaining a part of the flow (in contrast to [](position.md#absolute_positioning)).

Try it
------

A *floating element* is one where the computed value of `float` is not
`none`.

As `float` implies the use of the block layout, it modifies the computed
value of the [`display`](display.md) values, in some cases:

  Specified value        Computed value
  ---------------------- ----------------
  `inline`               `block`
  `inline-block`         `block`
  `inline-table`         `table`
  `table-row`            `block`
  `table-row-group`      `block`
  `table-column`         `block`
  `table-column-group`   `block`
  `table-cell`           `block`
  `table-caption`        `block`
  `table-header-group`   `block`
  `table-footer-group`   `block`
  `inline-flex`          `flex`
  `inline-grid`          `grid`
  *other*                *unchanged*

**Note:** If you\'re referring to this property from JavaScript as a
member of the
[`HTMLElement.style`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style)
object, modern browsers support `float`, but in older browsers you have
to spell it as `cssFloat`. This was an exception to the rule, that the
name of the DOM member is the
[camel-case](https://developer.mozilla.org/en-US/docs/Glossary/Camel_case)
name of the hyphenated CSS name (because \"float\" is a reserved word in
JavaScript, as seen in the need to escape \"class\" as \"className\" and
escape \<label\>\'s \"for\" as \"htmlFor\").

Syntax
------

[css]

```css
/* Keyword values */
float: left;
float: right;
float: none;
float: inline-start;
float: inline-end;

/* Global values */
float: inherit;
float: initial;
float: revert;
float: revert-layer;
float: unset;
```

The `float` property is specified as a single keyword, chosen from the
list of values below.

### Values

[`left`](#left)

:   The element must float on the left side of its containing block.

[`right`](#right)

:   The element must float on the right side of its containing block.

[`none`](#none)

:   The element must not float.

[`inline-start`](#inline-start)

:   The element must float on the start side of its containing block.
    That is the left side with `ltr` scripts, and the right side with
    `rtl` scripts.

[`inline-end`](#inline-end)

:   The element must float on the end side of its containing block. That
    is the right side with `ltr` scripts, and the left side with `rtl`
    scripts.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements, but has no effect if the value of [`display`](display.md) is `none`.
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------

Formal syntax
-------------

```
float = 
  block-start      |
  block-end        |
  inline-start     |
  inline-end       |
  snap-block       |
  <snap-block()>   |
  snap-inline      |
  <snap-inline()>  |
  left             |
  right            |
  top              |
  bottom           |
  none             |
  footnote         
```

Examples
--------

### How floated elements are positioned

As mentioned above, when an element is floated, it is taken out of the
normal flow of the document (though still remaining part of it). It is
shifted to the left, or right, until it touches the edge of its
containing box, *or another floated element*.

In this example, there are three colored squares. Two are floated left,
and one is floated right. Note that the second \"left\" square is placed
to the right of the first. Additional squares would continue to stack to
the right, until they filled the containing box, after which they would
wrap to the next line.

A floated element is at least as tall as its tallest nested floated
children. We gave the parent `width: 100%` and floated it to ensure it
is tall enough to encompass its floated children, and to make sure it
takes up the width of the parent so we don\'t have to clear its adjacent
sibling.

#### HTML

[html]

```html
<section>
  <div class="left">1</div>
  <div class="left">2</div>
  <div class="right">3</div>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi tristique
    sapien ac erat tincidunt, sit amet dignissim lectus vulputate. Donec id
    iaculis velit. Aliquam vel malesuada erat. Praesent non magna ac massa
    aliquet tincidunt vel in massa. Phasellus feugiat est vel leo finibus
    congue.
  </p>
</section>
```

#### CSS

[css]

```css
section {
  box-sizing: border-box;
  border: 1px solid blue;
  width: 100%;
  float: left;
}

div {
  margin: 5px;
  width: 50px;
  height: 150px;
}

.left {
  float: left;
  background: pink;
}

.right {
  float: right;
  background: cyan;
}
```

#### Result

### Clearing floats

Sometimes you may want to force an item to move below any floated
elements. For instance, you may want paragraphs to remain adjacent to
floats, but force headings to be on their own line. See [`clear`](clear.md)
for examples.

Specifications
--------------

  --------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------

  [Cascading Style Sheets Level 2 Revision 2 (CSS 2.2) Specification\
  [\# propdef-float]](https://drafts.csswg.org/css2/#propdef-float)

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

`float`

1

12

1

4

7

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

- [Block formatting
    context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)
- Use [`clear`](clear.md) to force an item to move below a floated
    element.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/float>
