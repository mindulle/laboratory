\<overflow\>
============

The `<overflow>`
[enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
value type represents the keyword values for the
[`overflow-block`](_Resources/Markup%20And%20Styling/css/overflow-block.md),
[`overflow-inline`](_Resources/Markup%20And%20Styling/css/overflow-inline.md), [`overflow-x`](overflow-x.md), and
[`overflow-y`](overflow-y.md) longhand properties and the
[`overflow`](overflow.md) shorthand property. These properties apply to
block containers, flex containers, and grid containers.

Syntax
------

```
<overflow> = visible | hidden | clip | scroll | auto
```

Values
------

The `<overflow>` enumerated value type is specified using one of the
values listed below.

[`visible`](#visible)

:   Overflow content is not clipped and may be visible outside the
    element\'s padding box. The element box is not a [scroll
    container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container).
    This is the default value for all the properties that have the
    `<overflow>` enumerated value type.

[`hidden`](#hidden)

:   Overflow content is clipped at the element\'s padding box. There are
    no scroll bars, and the clipped content is not visible (i.e.,
    clipped content is hidden), but the content still exists. User
    agents do not add scrollbars and also do not allow users to view the
    content outside the clipped region by actions such as dragging on a
    touch screen or using the scroll wheel on a mouse. The content *can*
    be scrolled programmatically (for example, by setting the value of
    the
    [`scrollLeft`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollLeft)
    property or the
    [`scrollTo()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTo)
    method). The content can also be scrolled via keyboard interaction;
    arrows enable scrolling through the content and tabbing to a
    focusable element within the hidden content enables scrolling the
    focused element into view. The element box on which this value is
    set is a scroll container.

[`clip`](#clip)

:   Overflow content is clipped at the element\'s *overflow clip edge*
    that is defined using the
    [`overflow-clip-margin`](overflow-clip-margin.md) property. As a
    result, content overflows the element\'s padding box by the
    [`<length>`](length.md) value of `overflow-clip-margin` or by `0px` if
    not set. Overflow content outside the clipped region is not visible,
    user agents do not add a scrollbar, and programmatic scrolling is
    also not supported. No new [formatting
    context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)
    is created.

[`scroll`](#scroll)

:   Overflow content is clipped at the element\'s padding box, and
    overflow content can be scrolled into view using scrollbars. User
    agents display scrollbars in both horizontal and vertical directions
    if only one value is set, whether or not any content is overflowing
    or clipped. The use of this keyword value, therefore, can prevent
    scrollbars from appearing and disappearing as content changes.
    Printers may still print overflowing content. The element box on
    which this value is set is a scroll container.

[`auto`](#auto)

:   Overflow content is clipped at the element\'s padding box, and
    overflow content can be scrolled into view. Unlike `scroll`, user
    agents display scrollbars *only if* the content is overflowing and
    hide scrollbars by default. If content fits inside the element\'s
    padding box, it looks the same as with `visible` but still
    establishes a new formatting context. The element box on which this
    value is set is a scroll container.

**Note:** The keyword value `overlay` is a legacy value alias for
`auto`. With `overlay`, the scroll bars are drawn on top of the content
instead of taking up space.

Examples
--------

This example demos all the `<overflow>` enumerated values for the
[`overflow`](overflow.md) property.

### HTML

The HTML in this example contains some lyrics within the
[`<pre>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/pre)
element. The HTML also contains a link text to enable testing the
effects of keyboard focus on overflow and scroll behaviors. The same
HTML code is repeated multiple times to show the effect of each
`<overflow>` enumerated value.

[html]

```html
<pre>&nbsp;
Oh, Rubber Duckie, you're the one
You make bath time lots of fun
Rubber Duckie, I'm awfully fond of you

Rubber Duckie, joy of joys
When I squeeze you, you make noise
Rubber Duckie, you're my very best friend, it's true

Oh, every day when I make my way to the tubby
I find a little fella who's cute and yellow and chubby
Rub-a-dub-dubby

<a href="#">Rubber Duckie</a>, you're so fine
And I'm lucky that you're mine
Rubber Duckie, I'm awfully fond of you
</pre>
```

### CSS

For the purpose of demonstration, the size of the `<pre>` element box
has been defined to ensure that the content overflows its container in
both the inline and block directions. A different `<overflow>` value is
set for each of the repeating `<pre>` elements. For the `clip` value
demonstration, a [`overflow-clip-margin`](overflow-clip-margin.md) has been
added.

[css]

```css
pre {
  block-size: 100px;
  inline-size: 295px;
}

pre:nth-of-type(1) {
  overflow: hidden;
}
pre:nth-of-type(1)::before {
  content: "hidden: ";
}

pre:nth-of-type(2) {
  overflow: clip;
  overflow-clip-margin: 1em;
}
pre:nth-of-type(2)::before {
  content: "clip: ";
}

pre:nth-of-type(3) {
  overflow: scroll;
}
pre:nth-of-type(3)::before {
  content: "scroll: ";
}

pre:nth-of-type(4) {
  overflow: auto;
}
pre:nth-of-type(4)::before {
  content: "auto: ";
}

pre:nth-of-type(5) {
  overflow: clip;
  overflow: overlay;
  overflow-clip-margin: 3em;
}
pre:nth-of-type(5)::before {
  content: "overlay (or clip if not supported): ";
}

pre:nth-of-type(6) {
  overflow: visible;
}
pre:nth-of-type(6)::before {
  content: "visible: ";
}
```

### Result

To see the effect of keyboard focus on overflow and scroll behaviors,
try tabbing through all the links in the example. Notice that the `clip`
box does not create a scroll container, and the link does not come into
view when the link is focused. The `visible` value, which has the link
always in view, is also not a scroll container.

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

`overflow_value`

1

12

1

4From version 4 to 6, Internet Explorer enlarges an element with
`visible` (default value) to fit the content inside it.

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

No

16

15.0

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

- Properties that use this data type: [`overflow-x`](overflow-x.md),
    [`overflow-y`](overflow-y.md), [`overflow-inline`](_Resources/Markup%20And%20Styling/css/overflow-inline.md),
    [`overflow-block`](_Resources/Markup%20And%20Styling/css/overflow-block.md) and [`overflow`](overflow.md)
- [CSS overflow module](css_overflow.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/overflow_value>
