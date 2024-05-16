\<area\>: The Image Map Area element
====================================

The `<area>` [HTML](../index) element defines an area inside an image
map that has predefined clickable areas. An *image map* allows geometric
areas on an image to be associated with [hypertext
links](https://developer.mozilla.org/en-US/docs/Glossary/Hyperlink).

This element is used only within a [`<map>`](map) element.

Try it
------

Attributes
----------

This element\'s attributes include the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`alt`](#alt)

:   A text string alternative to display on browsers that do not display
    images. The text should be phrased so that it presents the user with
    the same kind of choice as the image would offer when displayed
    without the alternative text. This attribute is required only if the
    [`href`](#href) attribute is used.

[`coords`](#coords)

:   The `coords` attribute details the coordinates of the
    [`shape`](#shape) attribute in size, shape, and placement of an
    `<area>`. This attribute must not be used if `shape` is set to
    `default`.

    -   `rect`: the value is `x1,y1,x2,y2`. The value specifies the
        coordinates of the top-left and bottom-right corner of the
        rectangle. For example, in
        `<area shape="rect" coords="0,0,253,27" href="#" target="_blank" alt="Mozilla">`
        the coordinates are `0,0` and `253,27`, indicating the top-left
        and bottom-right corners of the rectangle, respectively.
    -   `circle`: the value is `x,y,radius`. Value specifies the
        coordinates of the circle center and the radius. For example:
        `<area shape="circle" coords="130,136,60" href="#" target="_blank" alt="MDN">`
    -   `poly`: the value is `x1,y1,x2,y2,..,xn,yn`. Value specifies the
        coordinates of the edges of the polygon. If the first and last
        coordinate pairs are not the same, the browser will add the last
        coordinate pair to close the polygon

    The values are numbers of CSS pixels.

[`download`](#download)

:   This attribute, if present, indicates that the author intends the
    hyperlink to be used for downloading a resource. See [`<a>`](a) for
    a full description of the [`download`](a#download) attribute.

[`href`](#href)

:   The hyperlink target for the area. Its value is a valid URL. This
    attribute may be omitted; if so, the `<area>` element does not
    represent a hyperlink.

[`ping`](#ping)

:   Contains a space-separated list of URLs to which, when the hyperlink
    is followed,
    [`POST`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST)
    requests with the body `PING` will be sent by the browser (in the
    background). Typically used for tracking.

[`referrerpolicy`](#referrerpolicy)

:   A string indicating which referrer to use when fetching the
    resource:

    -   `no-referrer`: The
        [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer)
        header will not be sent.
    -   `no-referrer-when-downgrade`: The
        [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer)
        header will not be sent to
        [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin)s
        without
        [TLS](https://developer.mozilla.org/en-US/docs/Glossary/TLS)
        ([HTTPS](https://developer.mozilla.org/en-US/docs/Glossary/HTTPS)).
    -   `origin`: The sent referrer will be limited to the origin of the
        referring page: its
        [scheme](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Web_mechanics/What_is_a_URL),
        [host](https://developer.mozilla.org/en-US/docs/Glossary/Host),
        and
        [port](https://developer.mozilla.org/en-US/docs/Glossary/Port).
    -   `origin-when-cross-origin`: The referrer sent to other origins
        will be limited to the scheme, the host, and the port.
        Navigations on the same origin will still include the path.
    -   `same-origin`: A referrer will be sent for [same
        origin](https://developer.mozilla.org/en-US/docs/Glossary/Same-origin_policy),
        but cross-origin requests will contain no referrer information.
    -   `strict-origin`: Only send the origin of the document as the
        referrer when the protocol security level stays the same
        (HTTPS→HTTPS), but don\'t send it to a less secure destination
        (HTTPS→HTTP).
    -   `strict-origin-when-cross-origin` (default): Send a full URL
        when performing a same-origin request, only send the origin when
        the protocol security level stays the same (HTTPS→HTTPS), and
        send no header to a less secure destination (HTTPS→HTTP).
    -   `unsafe-url`: The referrer will include the origin *and* the
        path (but not the
        [fragment](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/hash),
        [password](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/password),
        or
        [username](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/username)).
        **This value is unsafe**, because it leaks origins and paths
        from TLS-protected resources to insecure origins.

[`rel`](#rel)

:   For anchors containing the [`href`](#href) attribute, this attribute
    specifies the relationship of the target object to the link object.
    The value is a space-separated list of link types. The values and
    their semantics will be registered by some authority that might have
    meaning to the document author. The default relationship, if no
    other is given, is void. Use this attribute only if the
    [`href`](#href) attribute is present.

[`shape`](#shape)

:   The shape of the associated hot spot. The specifications for HTML
    defines the values `rect`, which defines a rectangular region;
    `circle`, which defines a circular region; `poly`, which defines a
    polygon; and `default`, which indicates the entire region beyond any
    defined shapes.

[`target`](#target)

:   A keyword or author-defined name of the [browsing
    context](https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context)
    to display the linked resource. The following keywords have special
    meanings:

    -   `_self` (default): Show the resource in the current browsing
        context.
    -   `_blank`: Show the resource in a new, unnamed browsing context.
    -   `_parent`: Show the resource in the parent browsing context of
        the current one, if the current page is inside a frame. If there
        is no parent, acts the same as `_self`.
    -   `_top`: Show the resource in the topmost browsing context (the
        browsing context that is an ancestor of the current one and has
        no parent). If there is no parent, acts the same as `_self`.

    Use this attribute only if the [`href`](#href) attribute is present.

     
    **Note:** Setting `target="_blank"` on `<area>` elements implicitly
    provides the same `rel` behavior as setting
    [`rel="noopener"`](../attributes/rel/noopener) which does not set
    `window.opener`. See [browser compatibility](#browser_compatibility)
    for support status.

Examples
--------

[html]

```html
<map name="primary">
  <area
    shape="circle"
    coords="75,75,75"
    href="left.html"
    alt="Click to go Left" />
  <area
    shape="circle"
    coords="275,75,75"
    href="right.html"
    alt="Click to go Right" />
</map>
<img
  usemap="#primary"
  src="https://via.placeholder.com/350x150"
  alt="350 x 150 pic" />
```

### Result

Technical summary
-----------------

  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content).
  Permitted content                             None; it is a [void element](https://developer.mozilla.org/en-US/docs/Glossary/Void_element).
  Tag omission                                  Must have a start tag and must not have an end tag.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content). The `<area>` element must have an ancestor [`<map>`](map), but it need not be a direct parent.
  Implicit ARIA role                            [`link`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/link_role) when [`href`](area#href) attribute is present, otherwise [`generic`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/generic_role)
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLAreaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement)
  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -----------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-area-element]](https://html.spec.whatwg.org/multipage/image-maps.html#the-area-element)

  -----------------------------------------------------------------------------------------------------

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

`area`

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

`accesskey`

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

`alt`

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

`coords`

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

`download`

54

12

20

Yes

41

10.1

54

54

20

41

10.3

6.0

`href`

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

`implicit_noopener`

88

88

79

No

No

12.1

No

88

79

Yes

12.2

15.0

`nohref`

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

`ping`

12

17

1

No

15

6

≤37

18

No

14

6

1.0

`referrerpolicy`

51

79

50

No

38

11.1

51

51

50

41

No

7.2

`rel`

16

12

30

Yes

15

5

4.4

18

30

14

4.2

1.0

`shape`

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

`target`

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

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area>>
