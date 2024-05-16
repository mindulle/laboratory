overflow
========

The `overflow` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[shorthand property](shorthand_properties.md) sets the desired behavior
when content does not fit in the parent element box (overflows) in the
horizontal and/or vertical direction.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`overflow-x`](overflow-x.md)
- [`overflow-y`](overflow-y.md)

Syntax
------

[css]

```css
/* Keyword values */
overflow: visible;
overflow: hidden;
overflow: clip;
overflow: scroll;
overflow: auto;
overflow: hidden visible;

/* Global values */
overflow: inherit;
overflow: initial;
overflow: revert;
overflow: revert-layer;
overflow: unset;
```

The `overflow` property is specified as one or two
[`<overflow>`](overflow_value.md) keyword values. If only one keyword is
specified, both `overflow-x` and `overflow-y` are set to the same value.
If two keywords are specified, the first value applies to `overflow-x`
in the horizontal direction and the second one applies to `overflow-y`
in the vertical direction.

### Values

[`visible`](#visible)

:   Overflow content is not clipped and may be visible outside the
    element\'s padding box. The element box is not a [scroll
    container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container).
    This is the default value of the `overflow` property.

[`hidden`](#hidden)

:   Overflow content is clipped at the element\'s padding box. There are
    no scroll bars, and the clipped content is not visible (i.e.,
    clipped content is hidden), but the content still exists. User
    agents do not add scroll bars and also do not allow users to view
    the content outside the clipped region by actions such as dragging
    on a touch screen or using the scroll wheel on a mouse. The content
    *can* be scrolled programmatically (for example, by setting the
    value of the
    [`scrollLeft`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollLeft)
    property or the
    [`scrollTo()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTo)
    method), in which case the element box is a scroll container.

[`clip`](#clip)

:   Overflow content is clipped at the element\'s *overflow clip edge*
    that is defined using the
    [`overflow-clip-margin`](overflow-clip-margin.md) property. As a
    result, content overflows the element\'s padding box by the
    [`<length>`](length.md) value of `overflow-clip-margin` or by `0px` if
    not set. Overflow content outside the clipped region is not visible,
    user agents do not add a scroll bar, and programmatic scrolling is
    also not supported. No new [formatting
    context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)
    is created. To establish a formatting context, use `overflow: clip`
    along with [`display: flow-root`](display.md#flow-root). The element
    box is not a scroll container.

[`scroll`](#scroll)

:   Overflow content is clipped at the element\'s padding box, and
    overflow content can be scrolled into view using scroll bars. User
    agents display scroll bars in both horizontal and vertical
    directions if only one value is set, whether or not any content is
    overflowing or clipped. The use of this keyword, therefore, can
    prevent scroll bars from appearing and disappearing as content
    changes. Printers may still print overflowing content. The element
    box is a scroll container.

[`auto`](#auto)

:   Overflow content is clipped at the element\'s padding box, and
    overflow content can be scrolled into view. Unlike `scroll`, user
    agents display scroll bars *only if* the content is overflowing and
    hide scroll bars by default. If content fits inside the element\'s
    padding box, it looks the same as with `visible` but still
    establishes a new formatting context. The element box is a scroll
    container.

**Note:** The keyword value `overlay` is a legacy value alias for
`auto`. With `overlay`, the scroll bars are drawn on top of the content
instead of taking up space.

Description
-----------

Overflow options include hiding overflowing content, enabling scroll
bars to view overflow content or displaying the content flowing out of
an element box into the surrounding area, and combinations there of.

The following nuances should be kept in mind while using the various
keywords for `overflow`:

- Specifying a value other than `visible` (the default) or `clip` for
    `overflow` creates a new [block formatting
    context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context).
    This is necessary for technical reasons; if a float intersects with
    a scrolling element, it would forcibly rewrap the content after each
    scroll step, leading to a slow scrolling experience.
- For an `overflow` setting to create the desired effect, the
    block-level element must have either a set height (`height` or
    `max-height`) or `white-space` set to `nowrap`.
- Setting one axis to `visible` (the default) while setting the other
    to a *different* value results in `visible` behaving as `auto`.
- The JavaScript
    [`Element.scrollTop`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTop)
    property may be used to scroll through content in a scroll
    container, including when `overflow` is set to `hidden`.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | `visible`                         |
+-----------------------------------+-----------------------------------+
| Applies to                        | Block-containers, flex            |
|                                   | containers, and grid containers   |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [`overflow-x`](overflow-x.md):   |
|                                   |     as specified, except with     |
|                                   |     `visible`/`clip` computing to |
|                                   |     `auto`/`hidden` respectively  |
|                                   |     if one of                     |
|                                   |     [`overflow-x`](overflow-x.md) or |
|                                   |     [`overflow-y`](overflow-y.md) is |
|                                   |     neither `visible` nor clip    |
|                                   | -   [`overflow-y`](overflow-y.md):   |
|                                   |     as specified, except with     |
|                                   |     `visible`/`clip` computing to |
|                                   |     `auto`/`hidden` respectively  |
|                                   |     if one of                     |
|                                   |     [`overflow-x`](overflow-x.md) or |
|                                   |     [`overflow-y`](overflow-y.md) is |
|                                   |     neither `visible` nor clip    |
+-----------------------------------+-----------------------------------+
| Animation type                    | discrete                          |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
overflow = 
  [ visible | hidden | clip | scroll | auto ]  
```

Examples
--------

### Demonstrating results of various overflow keywords

#### HTML

[html]

```html
<div>
  <code>visible</code>
  <p class="visible">
    Maya Angelou: "I've learned that people will forget what you said, people
    will forget what you did, but people will never forget how you made them
    feel."
  </p>
</div>

<div>
  <code>hidden</code>
  <p class="hidden">
    Maya Angelou: "I've learned that people will forget what you said, people
    will forget what you did, but people will never forget how you made them
    feel."
  </p>
</div>

<div>
  <code>clip</code>
  <p class="clip">
    Maya Angelou: "I've learned that people will forget what you said, people
    will forget what you did, but people will never forget how you made them
    feel."
  </p>
</div>

<div>
  <code>scroll</code>
  <p class="scroll">
    Maya Angelou: "I've learned that people will forget what you said, people
    will forget what you did, but people will never forget how you made them
    feel."
  </p>
</div>

<div>
  <code>auto</code>
  <p class="auto">
    Maya Angelou: "I've learned that people will forget what you said, people
    will forget what you did, but people will never forget how you made them
    feel."
  </p>
</div>

<div>
  <code>overlay</code>
  <p class="overlay">
    Maya Angelou: "I've learned that people will forget what you said, people
    will forget what you did, but people will never forget how you made them
    feel."
  </p>
</div>
```

#### CSS

[css]

```css
p.visible {
  overflow: visible;
}

p.hidden {
  overflow: hidden;
}

p.clip {
  overflow: clip;
  overflow-clip-margin: 1em;
}

p.scroll {
  overflow: scroll;
}

p.auto {
  overflow: auto;
}

p.overlay {
  overflow: overlay;
}
```

#### Result

Accessibility concerns
----------------------

A scrolling content area cannot be scrolled by a keyboard-only user,
with the exception of users on Firefox (which makes the container
keyboard focusable by default).

As a developer, to allow non-Firefox keyboard-only users to scroll the
container, you will need to give it a
[`tabindex`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex)
using `tabindex="0"`. Unfortunately, when a screen reader encounters
this tab-stop, they will have no context for what it is and their screen
reader will likely announce the entirety of its contents. Giving it an
appropriate [WAI-ARIA
role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles)
(`role="region"`, for example) and an accessible name (via
[`aria-label`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label)
or
[`aria-labelledby`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-labelledby))
can mitigate this.

Specifications
--------------

  -------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------

  [CSS Overflow Module Level 3\
  [\#
  propdef-overflow]](https://drafts.csswg.org/css-overflow/#propdef-overflow)

  -------------------------------------------------------------------------------------

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

`overflow`

1

12

1After Firefox 3.6, the `overflow` property is correctly applied to
table group elements (`<thead>`, `<tbody>`, `<tfoot>`).

4From version 4 to 6, Internet Explorer enlarges an element with
`overflow: visible` (default value) to fit the content inside it.
`height` and `width` behave like `min-height` and `min-width`,
respectively.

7

1

37

18

4

14

1

1.0

`clip`

90

90

811.5--81

No

76

16

90

90

814--81

64

16

15.0

`multiple_keywords`

68

79

61

No

55

13.1

68

68

61

48

13.4

10.0

`overlay`

15

79

112

No

15

No

100

100

112

No

No

4.0

See also
--------

- [`overflow-x`](overflow-x.md), [`overflow-y`](overflow-y.md)
- [`overflow-block`](_Resources/Markup%20And%20Styling/css/overflow-block.md),
    [`overflow-clip-margin`](overflow-clip-margin.md),
    [`overflow-inline`](_Resources/Markup%20And%20Styling/css/overflow-inline.md)
- [`clip`](clip.md), [`display`](display.md),
    [`text-overflow`](text-overflow.md), [`white-space`](white-space.md)
- [CSS overflow](css_overflow.md)
- [Keyboard-only scrolling
    areas](https://adrianroselli.com/2022/06/keyboard-only-scrolling-areas.html)
    on adrianroselli.com (2022)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/overflow>
