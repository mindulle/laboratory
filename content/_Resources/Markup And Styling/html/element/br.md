\<br\>: The Line Break element
==============================

The `<br>` [HTML](../index) element produces a line break in text
(carriage-return). It is useful for writing a poem or an address, where
the division of lines is significant.

Try it
------

As you can see from the above example, a `<br>` element is included at
each point where we want the text to break. The text after the `<br>`
begins again at the start of the next line of the text block.

**Note:** Do not use `<br>` to create margins between paragraphs; wrap
them in [`<p>`](p) elements and use the
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)
property to control their size.

Attributes
----------

This element\'s attributes include the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

### Deprecated attributes

[`clear`](#clear) [Deprecated]

:   Indicates where to begin the next line after the break.

Styling with CSS
----------------

The `<br>` element has a single, well-defined purpose --- to create a
line break in a block of text. As such, it has no dimensions or visual
output of its own, and there is very little you can do to style it.

You can set a
[`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) on
`<br>` elements themselves to increase the spacing between the lines of
text in the block, but this is a bad practice --- you should use the
[`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height)
property that was designed for that purpose.

Examples
--------

### Simple br

In the following example we use `<br>` elements to create line breaks
between the different lines of a postal address:

[html]

```html
Mozilla<br />
331 E. Evelyn Avenue<br />
Mountain View, CA<br />
94041<br />
USA<br />
```

#### Result

Accessibility concerns
----------------------

Creating separate paragraphs of text using `<br>` is not only bad
practice, it is problematic for people who navigate with the aid of
screen reading technology. Screen readers may announce the presence of
the element, but not any content contained within `<br>`s. This can be a
confusing and frustrating experience for the person using the screen
reader.

Use `<p>` elements, and use CSS properties like
[`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) to
control their spacing.

Technical summary
-----------------

  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content).
  Permitted content                             None; it is a [void element](https://developer.mozilla.org/en-US/docs/Glossary/Void_element).
  Tag omission                                  Must have a start tag, and must not have an end tag. In XHTML documents, write this element as `<br />`.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          [`none`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/none_role), [`presentation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role)
  DOM interface                                 [`HTMLBRElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBRElement)
  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -----------------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-br-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-br-element)

  -----------------------------------------------------------------------------------------------------------

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

`br`

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

`clear`

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

See also
--------

- [`<address>`](address) element
- [`<p>`](p) element
- [`<wbr>`](wbr) element

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br>>
