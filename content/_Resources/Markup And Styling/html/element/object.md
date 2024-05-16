\<object\>: The External Object element
=======================================

The `<object>` [HTML](../index) element represents an external resource,
which can be treated as an image, a nested browsing context, or a
resource to be handled by a plugin.

Try it
------

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`archive`](#archive) [Deprecated]

:   A space-separated list of URIs for archives of resources for the
    object.

[`border`](#border) [Deprecated]

:   The width of a border around the control, in pixels.

[`classid`](#classid) [Deprecated]

:   The URI of the object\'s implementation. It can be used together
    with, or in place of, the **data** attribute.

[`codebase`](#codebase) [Deprecated]

:   The base path used to resolve relative URIs specified by
    **classid**, **data**, or **archive**. If not specified, the default
    is the base URI of the current document.

[`codetype`](#codetype) [Deprecated]

:   The content type of the data specified by **classid**.

[`data`](#data)

:   The address of the resource as a valid URL. At least one of **data**
    and **type** must be defined.

[`declare`](#declare) [Deprecated]

:   The presence of this Boolean attribute makes this element a
    declaration only. The object must be instantiated by a subsequent
    `<object>` element. Repeat the `<object>` element completely each
    time the resource is reused.

[`form`](#form)

:   The form element, if any, that the object element is associated with
    (its *form owner*). The value of the attribute must be an ID of a
    [`<form>`](form) element in the same document.

[`height`](#height)

:   The height of the displayed resource, in [CSS
    pixels](https://drafts.csswg.org/css-values/#px). --- (Absolute
    values only. [NO
    percentages](https://html.spec.whatwg.org/multipage/embedded-content.html#dimension-attributes))

[`name`](#name)

:   The name of valid browsing context (HTML5), or the name of the
    control (HTML 4).

[`standby`](#standby) [Deprecated]

:   A message that the browser can show while loading the object\'s
    implementation and data.

[`type`](#type)

:   The [content
    type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type)
    of the resource specified by **data**. At least one of **data** and
    **type** must be defined.

[`usemap`](#usemap)

:   A hash-name reference to a [`<map>`](map) element; that is a \'\#\'
    followed by the value of a [`name`](map#name) of a map element.

[`width`](#width)

:   The width of the display resource, in [CSS
    pixels](https://drafts.csswg.org/css-values/#px). --- (Absolute
    values only. [NO
    percentages](https://html.spec.whatwg.org/multipage/embedded-content.html#dimension-attributes))

Examples
--------

### Embed a video

#### HTML

[html]

```html
<object
  type="video/mp4"
  data="https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.webm"
  width="600"
  height="140">
  <img src="path/image.jpg" alt="useful image description" />
</object>
```

#### Result

If the video in the example fails to load, the user will be provided
with an image as fallback content. The [`<img>`](img) tag is used to
display an image. We include the `src` attribute set to the path to the
image we want to embed. We also include the `alt` attribute, which
provides the image with an accessible name. If the image also fails to
load, the content of the `alt` attribute will be displayed.

Technical summary
-----------------

  --------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content); [phrasing content](../content_categories#phrasing_content); [embedded content](../content_categories#embedded_content), palpable content; if the element has a [`usemap`](object#usemap) attribute, [interactive content](../content_categories#interactive_content); [listed](../content_categories#form_listed), [submittable](../content_categories#form_submittable) [form-associated](../content_categories#form-associated_content) element.
  Permitted content                             zero or more [`<param>`](param) elements, then [transparent](../content_categories#transparent_content_model).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [embedded content](../content_categories#embedded_content).
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          [`application`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/application_role), [`document`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/document_role), [`img`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/img_role)
  DOM interface                                 [`HTMLObjectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLObjectElement)
  --------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-object-element]](https://html.spec.whatwg.org/multipage/iframe-embed-object.html#the-object-element)

  ------------------------------------------------------------------------------------------------------------------

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

`object`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`archive`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`border`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`classid`

Yes

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`codebase`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`codetype`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`data`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`declare`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`form`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`height`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`name`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`standby`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`tabindex`

1

12

1

Yes

15

3.1

4.4

18

4

14

2

1.0

`type`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`usemap`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`width`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

See also
--------

- [`<embed>`](embed)
- [`<param>`](param)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object>>
