CSS basic user interface
========================

The **CSS basic user interface** module lets you define the rendering
and functionality of features related to the user interface including
outline properties, visual feedback to pointing device and keyboard, and
altering the default appearance of UI widgets.

Basic user interface properties can be used to improve user experience
and accessibility by providing visual cues to elements that are being
interacted with, including styling mouse cursors and keyboard
directional focus navigation, and styling caret cursors when an editable
element has focus. The module provides for providing outlines to focused
(or not) elements without impacting an element\'s [box
model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model#what_is_the_css_box_model)
dimensions and styling. This UI module also enables the styling of user
interface controls.

### Basic user interface in action

To view how basic user interface properties can alter the appearance of
UI features, interact with the elements in this sample. Note that some
features in this sample improve usability while others harm user
experience.

The CSS [`outline`](outline.md) and [`outline-offset`](outline-offset.md)
properties were used to provide feedback to users which element
currently has focus. An [`accent-color`](accent-color.md) provides a theme
color to all the form controls. The caret that appears when the text is
edit has the same color thanks to the [`caret-color`](caret-color.md)
property. These can all be considered UI improvements.

Some features harm usability. The [`cursor`](cursor.md) property was used
to change cursors from the browser default which is confusing. The
[`resize`](resize.md) property prevents the second
[`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)
from being resizable while the [`pointer-events`](pointer-events.md)
property prevents the third `<textarea>` from receiving click events. It
is still focusable using the keyboard.

To see the code for this basic user interface sample, [view the source
on
GitHub](https://github.com/mdn/css-examples/blob/main/modules/basicUI.html).

Reference
---------

### Properties

- [`accent-color`](accent-color.md)
- [`appearance`](appearance.md)
- [`caret`], shorthand for:
  - [`caret-color`](caret-color.md)
  - [`caret-shape`]
- [`cursor`](cursor.md)
- [`nav-down`]
- [`nav-left`]
- [`nav-right`]
- [`nav-up`]
- [`outline`](outline.md), shorthand for:
  - [`outline-color`](outline-color.md)
  - [`outline-style`](outline-style.md)
  - [`outline-width`](outline-width.md)
- [`outline-offset`](outline-offset.md)
- [`pointer-events`](pointer-events.md)
- [`resize`](resize.md)
- [`user-select`](user-select.md)

Guides
------

[Learn forms: advanced form styling](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling)

:   Explains how [`appearance`](appearance.md) can be used to style form
    controls.

Related concepts
----------------

- CSS [`cursor`](cursor.md) property
- SVG
    [`cursor`](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/cursor)
    attribute
- CSS [`:focus`](:focus), [`:focus-within`](:focus-within), and
    [`:focus-visible`](:focus-visible) pseudoclasses
- [`CaretPosition`](https://developer.mozilla.org/en-US/docs/Web/API/CaretPosition)
    Interface

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Basic User Interface Module Level 4\
  ](https://drafts.csswg.org/css-ui/)

  -----------------------------------------------------------------------

See also
--------

- [Tips for Designing Useful and Usable Focus
    Indicators](https://www.deque.com/blog/give-site-focus-tips-designing-usable-focus-indicators/) (2016)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_basic_user_interface>
