\<map\>: The Image Map element
==============================

The `<map>` [HTML](../index) element is used with [`<area>`](area)
elements to define an image map (a clickable link area).

Try it
------

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`name`](#name)

:   The `name` attribute gives the map a name so that it can be
    referenced. The attribute must be present and must have a non-empty
    value with no space characters. The value of the `name` attribute
    must not be equal to the value of the `name` attribute of another
    `<map>` element in the same document. If the
    [`id`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#id) attribute is also specified, both
    attributes must have the same value.

Examples
--------

### Image map with two areas

Click the left-hand parrot for JavaScript, or the right-hand parrot for
CSS.

#### HTML

[html]

```html
<!-- Photo by Juliana e Mariana Amorim on Unsplash -->
<map name="primary">
  <area
    shape="circle"
    coords="75,75,75"
    href="https://developer.mozilla.org/docs/Web/JavaScript"
    target="_blank"
    alt="JavaScript" />
  <area
    shape="circle"
    coords="275,75,75"
    href="https://developer.mozilla.org/docs/Web/CSS"
    target="_blank"
    alt="CSS" />
</map>
<img
  usemap="#primary"
  src="parrots.jpg"
  alt="350 x 150 picture of two parrots" />
```

#### Result

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content.
  Permitted content                             Any [transparent](../content_categories#transparent_content_model) element.
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLMapElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMapElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-map-element]](https://html.spec.whatwg.org/multipage/image-maps.html#the-map-element)

  ---------------------------------------------------------------------------------------------------

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

`map`

1

12

1\[\"Before Firefox 5, in Quirks Mode, empty maps were no longer skipped
over in favor of non-empty ones when matching.\", \"Before Firefox 17,
the default styling of the `<map>` HTML element was `display: block;`.
This is now `display: inline;` and matches the behavior of the other
browsers. It was already the case in Quirks Mode.\"\]

Yes

15

1

4.4

18

4

14

1

1.0

`name`

1

12

1

Yes

15

1

4.4

18

4

14

1

1.0

See also
--------

- [`<a>`](a)
- [`<area>`](area)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/map>>
