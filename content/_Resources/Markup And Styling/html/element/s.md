\<s\>: The Strikethrough element
================================

The `<s>` [HTML](../index) element renders text with a strikethrough, or
a line through it. Use the `<s>` element to represent things that are no
longer relevant or no longer accurate. However, `<s>` is not appropriate
when indicating document edits; for that, use the [`<del>`](del) and
[`<ins>`](ins) elements, as appropriate.

Try it
------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Phrasing content](../content_categories#phrasing_content), [flow content](../content_categories#flow_content).
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            `deletion`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Examples
--------

[css]

```css
.sold-out {
  text-decoration: line-through;
}

```

[html]

```html
<s>Today's Special: Salmon</s> SOLD OUT<br />
<span class="sold-out">Today's Special: Salmon</span> SOLD OUT
```

### Result

Accessibility concerns
----------------------

The presence of the `s` element is not announced by most screen reading
technology in its default configuration. It can be made to be announced
by using the CSS
[`content`](https://developer.mozilla.org/en-US/docs/Web/CSS/content)
property, along with the
[`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before)
and
[`::after`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after)
pseudo-elements.

[css]

```css
s::before,
s::after {
  clip-path: inset(100%);
  clip: rect(1px, 1px, 1px, 1px);
  height: 1px;
  overflow: hidden;
  position: absolute;
  white-space: nowrap;
  width: 1px;
}

s::before {
  content: " [start of stricken text] ";
}

s::after {
  content: " [end of stricken text] ";
}

```

Some people who use screen readers deliberately disable announcing
content that creates extra verbosity. Because of this, it is important
to not abuse this technique and only apply it in situations where not
knowing content has been struck out would adversely affect
understanding.

- [Short note on making your mark (more accessible) \| The Paciello
    Group](https://www.tpgi.com/short-note-on-making-your-mark-more-accessible/)
- [Tweaking Text Level Styles \| Adrian
    Roselli](https://adrianroselli.com/2017/12/tweaking-text-level-styles.html)

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-s-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-s-element)

  ---------------------------------------------------------------------------------------------------------

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

`s`

1

12

1Before Firefox 4, this element implemented the `HTMLSpanElement`
interface instead of the standard `HTMLElement` interface.

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

See also
--------

- The [`<strike>`](strike) element, alter ego of the [`<s>`](s)
    element, is obsolete and should not be used on websites anymore.
- The [`<del>`](del) element is to be used instead if the data has
    been *deleted*.
- The CSS
    [`text-decoration-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-line)
    property is to be used to achieve the former visual aspect of the
    [`<s>`](s) element.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/s>
