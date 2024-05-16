draggable
=========

The `draggable` [global attribute](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) is an
[enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
attribute that indicates whether the element can be dragged, either with
native browser behavior or the [HTML Drag and Drop
API](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API).

The `draggable` attribute may be applied to elements that strictly fall
under the [HTML
namespace](https://developer.mozilla.org/en-US/docs/Glossary/Namespace),
which means that it cannot be applied to
[SVGs](https://developer.mozilla.org/en-US/docs/Web/SVG). For more
information about what namespace declarations look like, and what they
do, see [Namespace crash
course](https://developer.mozilla.org/en-US/docs/Web/SVG/Namespaces_Crash_Course).

`draggable` can have the following values:

- `true`: the element can be dragged.
- `false`: the element cannot be dragged.

**Warning:** This attribute is
*[enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)*
and not *Boolean*. A value of `true` or `false` is mandatory, and
shorthand like `<img draggable>` is forbidden. The correct usage is
`<img draggable="false">`.

If this attribute is not set, its default value is `auto`, which means
drag behavior is the default browser behavior: only text selections,
images, and links can be dragged. For other elements, the event
[`ondragstart`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/dragstart_event)
must be set for drag and drop to work, as shown in this [comprehensive
example](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API/Drag_operations).

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-draggable-attribute]](https://html.spec.whatwg.org/multipage/dnd.html#the-draggable-attribute)

  ------------------------------------------------------------------------------------------------------------

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

`draggable`

4

12

2

Yes

12

5

4.4

18

4

14

4.2

1.0

See also
--------

- All [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/draggable>>
