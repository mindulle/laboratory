\<code\>: The Inline Code element
=================================

The `<code>` [HTML](../index) element displays its contents styled in a
fashion intended to indicate that the text is a short fragment of
computer code. By default, the content text is displayed using the [user
agent\'s](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
default monospace font.

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Examples
--------

A paragraph of text that includes `<code>`:

[html]

```html
<p>
  The function <code>selectAll()</code> highlights all the text in the input
  field so the user can, for example, copy or delete the text.
</p>
```

### Result

Notes
-----

To represent multiple lines of code, wrap the `<code>` element within a
[`<pre>`](pre) element. The `<code>` element by itself only represents a
single phrase of code or line of code.

A CSS rule can be defined for the `code` selector to override the
browser\'s default font face. Preferences set by the user might take
precedence over the specified CSS.

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            `code`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) Up to Gecko 1.9.2 (Firefox 4) inclusive, Firefox implements the [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement) interface for this element.
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-code-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-code-element)

  ---------------------------------------------------------------------------------------------------------------

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

`code`

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

- [`<samp>`](samp)
- [`<kbd>`](kbd)
- [`<var>`](var)
- [`<pre>`](pre)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/code>>
