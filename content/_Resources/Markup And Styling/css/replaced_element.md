Replaced elements
=================

In [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS), a **replaced
element** is an element whose representation is outside the scope of
CSS; they\'re external objects whose representation is independent of
the CSS formatting model.

Put in simpler terms, they\'re elements whose contents are not affected
by the current document\'s styles. The position of the replaced element
can be affected using CSS, but not the contents of the replaced element
itself. Some replaced elements, such as
[`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)
elements, may have stylesheets of their own, but they don\'t inherit the
styles of the parent document.

The only other impact CSS can have on a replaced element is that there
are properties which support controlling the positioning of the
element\'s content within its box. See [Controlling object position
within the content
box](#controlling_object_position_within_the_content_box) for further
information.

Replaced elements
-----------------

Typical replaced elements are:

- [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)
- [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)
- [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed)
- [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)

Some elements are treated as replaced elements only in specific cases:

- [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option)
- [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
- [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas)
- [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object)

HTML spec also says that an
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
element can be replaced, because
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
elements of the `"image"` type are replaced elements similar to
[`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img).
However, other form controls, including other types of
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
elements, are explicitly listed as non-replaced elements (the spec
describes their default platform-specific rendering with the term
\"Widgets\").

Objects inserted using the CSS [`content`](content.md) property are
*anonymous replaced elements*. They are \"anonymous\" because they
don\'t exist in the HTML markup.

Using CSS with replaced elements
--------------------------------

CSS handles replaced elements specifically in some cases, like when
calculating margins and some `auto` values.

Note that some replaced elements, but not all, have intrinsic dimensions
or a defined baseline, which is used by some CSS properties, such as
[`vertical-align`](vertical-align.md). Only replaced elements can ever have
intrinsic dimensions.

### Controlling object position within the content box

Certain CSS properties can be used to specify how the object contained
within the replaced element should be positioned within the element\'s
box area. These are defined by the [CSS
Images](https://drafts.csswg.org/css-images/) specification:

[`object-fit`](object-fit.md)

:   Specifies how the replaced element\'s content object should be
    fitted to the containing element\'s box.

[`object-position`](object-position.md)

:   Specifies the alignment of the replaced element\'s content object
    within the element\'s box.

See also
--------

- [HTML
    Spec](https://html.spec.whatwg.org/multipage/rendering.html#replaced-elements)
- [Void
    elements](https://developer.mozilla.org/en-US/docs/Glossary/Void_element)
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
  - [Shorthand properties](shorthand_properties.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Replaced_element>
