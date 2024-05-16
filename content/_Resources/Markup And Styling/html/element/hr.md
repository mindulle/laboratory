\<hr\>: The Thematic Break (Horizontal Rule) element
====================================================

The `<hr>` [HTML](../index) element represents a thematic break between
paragraph-level elements: for example, a change of scene in a story, or
a shift of topic within a section.

Try it
------

Historically, this has been presented as a horizontal rule or line.
While it may still be displayed as a horizontal rule in visual browsers,
this element is now defined in semantic terms, rather than
presentational terms, so if you wish to draw a horizontal line, you
should do so using appropriate CSS.

Attributes
----------

This element\'s attributes include the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`align`](#align) [Deprecated]

:   Sets the alignment of the rule on the page. If no value is
    specified, the default value is `left`.

[`color`](#color) [Deprecated]

:   Sets the color of the rule through color name or hexadecimal value.

[`noshade`](#noshade) [Deprecated]

:   Sets the rule to have no shading.

[`size`](#size) [Deprecated]

:   Sets the height, in pixels, of the rule.

[`width`](#width) [Deprecated]

:   Sets the length of the rule on the page through a pixel or
    percentage value.

Example
-------

### HTML

[html]

```html
<p>
  This is the first paragraph of text. This is the first paragraph of text. This
  is the first paragraph of text. This is the first paragraph of text.
</p>

<hr />

<p>
  This is the second paragraph of text. This is the second paragraph of text.
  This is the second paragraph of text. This is the second paragraph of text.
</p>
```

### Result

Technical summary
-----------------

  --------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content).
  Permitted content                             None; it is a [void element](https://developer.mozilla.org/en-US/docs/Glossary/Void_element).
  Tag omission                                  It must have start tag, but must not have an end tag.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content).
  Implicit ARIA role                            [`separator`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/separator_role)
  Permitted ARIA roles                          [`presentation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role) or [`none`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/none_role)
  DOM interface                                 [`HTMLHRElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHRElement)
  --------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-hr-element]](https://html.spec.whatwg.org/multipage/grouping-content.html#the-hr-element)

  -------------------------------------------------------------------------------------------------------

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

`hr`

1

12

1

5.5

≤12.1

3

4.4

18

4

≤12.1

1

1.0

`align`

1

12

1

≤6

≤12.1

≤4

4.4

18

4

≤12.1

≤3.2

1.0

`color`

33

12

1

≤6

20

10.1

4.4.3

33

4

20

10.3

2.0

`noshade`

1

12

1

≤6

≤12.1

≤4

4.4

18

4

≤12.1

≤3.2

1.0

`size`

1

12

1

≤6

≤12.1

≤4

4.4

18

4

≤12.1

≤3.2

1.0

`width`

1

12

1

≤6

≤12.1

≤4

4.4

18

4

≤12.1

≤3.2

1.0

See also
--------

- [`<p>`](p)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/hr>>
