Shorthand properties
====================

***Shorthand properties*** are CSS properties that let you set the
values of multiple other CSS properties simultaneously. Using a
shorthand property, you can write more concise (and often more readable)
style sheets, saving time and energy.

The CSS specification defines shorthand properties to group the
definition of common properties acting on the same theme. For instance,
the CSS [`background`](background.md) property is a shorthand property
that\'s able to define the values of
[`background-color`](background-color.md),
[`background-image`](background-image.md),
[`background-repeat`](background-repeat.md), and
[`background-position`](background-position.md). Similarly, the most common
font-related properties can be defined using the shorthand
[`font`](font.md), and the different margins around a box can be defined
using the [`margin`](margin.md) shorthand.

Tricky edge cases
-----------------

There are a few edge cases to keep in mind when using shorthand
properties.

### Omitting properties

A value which is not specified is set to its initial value. That means
that it **overrides** previously set values. For example:

[css]

```css
p {
  background-color: red;
  background: url(images/bg.gif) no-repeat left top;
}
```

This will not set the color of the background to `red` but to the
default value for [`background-color`](background-color.md), which is
`transparent`.

Only the individual properties values can inherit. As missing values are
replaced by their initial value, it is impossible to allow inheritance
of individual properties by omitting them. The keyword `inherit` can be
applied to a property, but only as a whole, not as a keyword for one
value or another. That means that the only way to make some specific
value to be inherited is to use the longhand property with the keyword
`inherit`.

### Ordering properties

Shorthand properties try not to force a specific order for the values of
the properties they replace. This works well when these properties use
values of different types, as the order has no importance, but this does
not work as easily when several properties can have identical values.

Two important cases here are:

- properties related to the edges of a box, like
    [`border-style`](border-style.md), [`margin`](margin.md) or
    [`padding`](padding.md)
- properties related to the corners of a box, like
    [`border-radius`](border-radius.md)

#### Edges of a box

Shorthands handling properties related to edges of a box, like
[`border-style`](border-style.md), [`margin`](margin.md) or
[`padding`](padding.md), always use a consistent 1-to-4-value syntax
representing those edges:

- **1-value syntax:** `border-width: 1em` --- The single value
    represents all edges:
- **2-value syntax:** `border-width: 1em 2em` --- The first value
    represents the vertical, that is top and bottom, edges, the second
    the horizontal ones, that is the left and right ones:
- **3-value syntax:** `border-width: 1em 2em 3em` --- The first value
    represents the top edge, the second, the horizontal, that is left
    and right, ones, and the third value the bottom edge:
- **4-value syntax:** `border-width: 1em 2em 3em 4em` --- The four
    values represent the top, right, bottom and left edges respectively,
    always in that order, that is clock-wise starting at the top:  The initial letter of Top-Right-Bottom-Left matches the
    order of the consonant of the word *trouble*: TRBL. You can also
    remember it as the order that the hands would rotate on a clock:
    `1em` starts in the 12 o\'clock position, then `2em` in the 3
    o\'clock position, then `3em` in the 6 o\'clock position, and `4em`
    in the 9 o\'clock position.

#### Corners of a box

Similarly, shorthands handling properties related to corners of a box,
like [`border-radius`](border-radius.md), always use a consistent
1-to-4-value syntax representing those corners:

- **1-value syntax:** `border-radius: 1em` --- The single value
    represents all corners:
- **2-value syntax:** `border-radius: 1em 2em` --- The first value
    represents the top left and bottom right corner, the second the top
    right and bottom left ones:
- **3-value syntax:** `border-radius: 1em 2em 3em` --- The first value
    represents the top left corner, the second the top right and bottom
    left ones, and the third value the bottom right corner:
- **4-value syntax:** `border-radius: 1em 2em 3em 4em` --- The four
    values represent the top left, top right, bottom right and bottom
    left corners respectively, always in that order, that is clock-wise
    starting at the top left:

Background properties
---------------------

Consider a background with the following properties

[css]

```css
background-color: #000;
background-image: url(images/bg.gif);
background-repeat: no-repeat;
background-position: left top;
```

These four declarations can be shortened to just one:

[css]

```css
background: #000 url(images/bg.gif) no-repeat left top;
```

(The shorthand form is actually the equivalent of the longhand
properties above plus `background-attachment: scroll` and, in CSS3, some
additional properties.)

See [`background`](background.md) for more detailed information, including
CSS3 properties.

Font properties
---------------

Consider the following declarations:

[css]

```css
font-style: italic;
font-weight: bold;
font-size: 0.8em;
line-height: 1.2;
font-family: Arial, sans-serif;
```

These 5 statements can be shortened to the following:

[css]

```css
font:
  italic bold 0.8em/1.2 Arial,
  sans-serif;
```

This shorthand declaration is actually equivalent to the longhand
declarations above plus `font-variant: normal`,
`font-size-adjust: none`, and `font-stretch: normal`.

Border properties
-----------------

With borders, the width, color, and style can be simplified into one
declaration. For example, consider the following CSS:

[css]

```css
border-width: 1px;
border-style: solid;
border-color: #000;
```

It can be simplified as:

[css]

```css
border: 1px solid #000;
```

Margin and padding properties
-----------------------------

Shorthand versions of margin and padding values work similarly; the
margin property allows for shorthand values to be specified using one,
two, three, or four values. Consider the following CSS declarations:

[css]

```css
margin-top: 10px;
margin-right: 5px;
margin-bottom: 10px;
margin-left: 5px;
```

They are the same as the following declaration using the four value
shorthand. Note that the values are in clockwise order, beginning at the
top: top, right, bottom, then left (TRBL, the consonants in
\"trouble\").

[css]

```css
margin: 10px 5px 10px 5px;
```

Margin shorthand rules for one, two, three and four value declarations
are:

- When **one** value is specified, it applies the same margin to **all
    four sides**.
- When **two** values are specified, the first margin applies to the
    **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first margin applies to the
    **top**, the second to the **left and right**, the third to the
    **bottom**.
- When **four** values are specified, the margins apply to the
    **top**, **right**, **bottom**, and **left** in that order
    (clockwise).

Position properties
-------------------

With position, the shorthand versions of top, right, bottom and left can
be simplified into one declaration. For example, consider the following
CSS:

[css]

```css
top: 0;
right: 20px;
bottom: 0;
left: 20px;
```

It can be simplified as:

[css]

```css
inset: 0 20px 0 20px;
```

Just like margins and paddings, the inset values are ordered clockwise -
top, right, bottom, then left (TRBL).

The universal shorthand property
--------------------------------

CSS provides a universal shorthand property, [`all`](all.md), which applies
its value to every property in the document. Its purpose is to change
the properties\' inheritance model.

See [Cascade and
inheritance](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance)
or [Introducing the CSS Cascade](cascade.md) for more information about how
inheritance works in CSS.

See also
--------

- CSS key concepts:
  - [CSS syntax](_Resources/Markup%20And%20Styling/css/syntax.md)
  - [At-rules](at-rule.md)
  - [Comments](comments.md)
  - [Specificity](specificity.md)
  - [Inheritance](inheritance.md)
  - [Box model](introduction_to_the_css_box_model.md)
  - [Layout modes](layout_mode.md)
  - [Visual formatting models](visual_formatting_model.md)
  - [Margin collapsing](mastering_margin_collapsing.md)
  - Values
    - [Initial values](initial_value.md)
    - [Computed values](computed_value.md)
    - [Used values](used_value.md)
    - [Actual values](actual_value.md)
  - [Value definition syntax](value_definition_syntax.md)
  - [Replaced elements](replaced_element.md)
- Shorthand properties:
  - [`all`](all.md)
  - [`animation`](animation.md)
  - [`background`](background.md)
  - [`border`](border.md)
  - [`border-block-end`](border-block-end.md)
  - [`border-block-start`](border-block-start.md)
  - [`border-bottom`](border-bottom.md)
  - [`border-color`](border-color.md)
  - [`border-image`](border-image.md)
  - [`border-inline-end`](border-inline-end.md)
  - [`border-inline-start`](border-inline-start.md)
  - [`border-left`](border-left.md)
  - [`border-radius`](border-radius.md)
  - [`border-right`](border-right.md)
  - [`border-style`](border-style.md)
  - [`border-top`](border-top.md)
  - [`border-width`](border-width.md)
  - [`column-rule`](column-rule.md)
  - [`columns`](columns.md)
  - [`container`](container.md)
  - [`contain-intrinsic-size`](contain-intrinsic-size.md)
  - [`flex`](flex.md)
  - [`flex-flow`](flex-flow.md)
  - [`font`](font.md)
  - [`font-synthesis`](font-synthesis.md)
  - [`font-variant`](font-variant.md)
  - [`gap`](gap.md)
  - [`grid`](_Resources/Markup%20And%20Styling/css/grid.md)
  - [`grid-area`](grid-area.md)
  - [`grid-column`](grid-column.md)
  - [`grid-row`](grid-row.md)
  - [`grid-template`](grid-template.md)
  - [`inset`](_Resources/Markup%20And%20Styling/css/inset.md)
  - [`list-style`](list-style.md)
  - [`margin`](margin.md)
  - [`mask`](mask.md)
  - [`offset`](offset.md)
  - [`outline`](outline.md)
  - [`overflow`](overflow.md)
  - [`padding`](padding.md)
  - [`place-content`](place-content.md)
  - [`place-items`](place-items.md)
  - [`place-self`](place-self.md)
  - [`scroll-margin`](scroll-margin.md)
  - [`scroll-padding`](scroll-padding.md)
  - [`scroll-timeline`](scroll-timeline.md)
  - [`text-decoration`](text-decoration.md)
  - [`text-emphasis`](text-emphasis.md)
  - [`transition`](transition.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Shorthand_properties>
