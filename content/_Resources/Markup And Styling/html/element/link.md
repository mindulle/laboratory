\<link\>: The External Resource Link element
============================================

The `<link>` [HTML](../index) element specifies relationships between
the current document and an external resource. This element is most
commonly used to link to
[stylesheets](https://developer.mozilla.org/en-US/docs/Glossary/CSS),
but is also used to establish site icons (both \"favicon\" style icons
and icons for the home screen and apps on mobile devices) among other
things.

Try it
------

To link an external stylesheet, you\'d include a `<link>` element inside
your [`<head>`](head) like this:

[html]

```html
<link href="main.css" rel="stylesheet" />
```

This simple example provides the path to the stylesheet inside an `href`
attribute, and a [`rel`](../attributes/rel) attribute with a value of
`stylesheet`. The `rel` stands for \"relationship\", and is one of the
key features of the `<link>` element --- the value denotes how the item
being linked to is related to the containing document.

There are a number of other common types you\'ll come across. For
example, a link to the site\'s favicon:

[html]

```html
<link rel="icon" href="favicon.ico" />
```

There are a number of other icon `rel` values, mainly used to indicate
special icon types for use on various mobile platforms, e.g.:

[html]

```html
<link
  rel="apple-touch-icon"
  sizes="114x114"
  href="apple-icon-114.png"
  type="image/png" />
```

The `sizes` attribute indicates the icon size, while the `type` contains
the MIME type of the resource being linked. These provide useful hints
to allow the browser to choose the most appropriate icon available.

You can also provide a media type or query inside a `media` attribute;
this resource will then only be loaded if the media condition is true.
For example:

[html]

```html
<link href="print.css" rel="stylesheet" media="print" />
<link
  href="mobile.css"
  rel="stylesheet"
  media="screen and (max-width: 600px)" />
```

Some interesting new performance and security features have been added
to the `<link>` element too. Take this example:

[html]

```html
<link
  rel="preload"
  href="myFont.woff2"
  as="font"
  type="font/woff2"
  crossorigin="anonymous" />
```

A `rel` value of `preload` indicates that the browser should preload
this resource (see [`rel="preload"`](../attributes/rel/preload) for more
details), with the `as` attribute indicating the specific class of
content being fetched. The `crossorigin` attribute indicates whether the
resource should be fetched with a
[CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) request.

Other usage notes:

- A `<link>` element can occur either in the [`<head>`](head) or
    [`<body>`](body) element, depending on whether it has a [link
    type](https://html.spec.whatwg.org/multipage/links.html#body-ok)
    that is **body-ok**. For example, the `stylesheet` link type is
    body-ok, and therefore `<link rel="stylesheet">` is permitted in the
    body. However, this isn\'t a good practice to follow; it makes more
    sense to separate your `<link>` elements from your body content,
    putting them in the `<head>`.
- When using `<link>` to establish a favicon for a site, and your site
    uses a Content Security Policy (CSP) to enhance its security, the
    policy applies to the favicon. If you encounter problems with the
    favicon not loading, verify that the
    [`Content-Security-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy)
    header\'s [`img-src`
    directive](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/img-src)
    is not preventing access to it.
- The HTML and XHTML specifications define event handlers for the
    `<link>` element, but it is unclear how they would be used.
- Under XHTML 1.0, [void
    elements](https://developer.mozilla.org/en-US/docs/Glossary/Void_element)
    such as `<link>` require a trailing slash: `<link />`.
- WebTV supports the use of the value `next` for `rel` to preload the
    next page in a document series.

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`as`](#as)

:   This attribute is required when
    [`rel="preload"`](../attributes/rel/preload) has been set on the
    `<link>` element, optional when
    [`rel="modulepreload"`](../attributes/rel/modulepreload) has been
    set, and otherwise should not be used. It specifies the type of
    content being loaded by the `<link>`, which is necessary for request
    matching, application of correct [content security
    policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP), and
    setting of correct
    [`Accept`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept)
    request header.

    Furthermore, `rel="preload"` uses this as a signal for request
    prioritization. The table below lists the valid values for this
    attribute and the elements or resources they apply to.

     
    +-----------------------------------+-----------------------------------+
    | Value                             | Applies To                        |
    +===================================+===================================+
    | audio                             | `<audio>` elements                |
    +-----------------------------------+-----------------------------------+
    | document                          | `<iframe>` and `<frame>` elements |
    +-----------------------------------+-----------------------------------+
    | embed                             | `<embed>` elements                |
    +-----------------------------------+-----------------------------------+
    | fetch                             | fetch, XHR                        |
    |                                   |                                   |
    |                                   |        |
    |                                   | **Note:** This value also         |
    |                                   | requires `<link>` to contain the  |
    |                                   | crossorigin attribute, see        |
    |                                   | [CORS-enabled                     |
    |                                   | fetches](../attributes/r          |
    |                                   | el/preload#cors-enabled_fetches). |
    |                                   |                                |
    +-----------------------------------+-----------------------------------+
    | font                              | CSS \@font-face                   |
    +-----------------------------------+-----------------------------------+
    | image                             | `<img>` and `<picture>` elements  |
    |                                   | with srcset or imageset           |
    |                                   | attributes, SVG `<image>`         |
    |                                   | elements, CSS `*-image` rules     |
    +-----------------------------------+-----------------------------------+
    | object                            | `<object>` elements               |
    +-----------------------------------+-----------------------------------+
    | script                            | `<script>` elements, Worker       |
    |                                   | `importScripts`                   |
    +-----------------------------------+-----------------------------------+
    | style                             | `<link rel=stylesheet>` elements, |
    |                                   | CSS `@import`                     |
    +-----------------------------------+-----------------------------------+
    | track                             | `<track>` elements                |
    +-----------------------------------+-----------------------------------+
    | video                             | `<video>` elements                |
    +-----------------------------------+-----------------------------------+
    | worker                            | Worker, SharedWorker              |
    +-----------------------------------+-----------------------------------+

[`blocking`](#blocking) [Experimental]

:   This attribute explicitly indicates that certain operations should
    be blocked on the fetching of an external resource. The operations
    that are to be blocked must be a space-separated list of blocking
    attributes listed below.

    -   `render`: The rendering of content on the screen is blocked.

[`crossorigin`](#crossorigin)

:   This
    [enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
    attribute indicates whether
    [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) must
    be used when fetching the resource. [CORS-enabled
    images](../cors_enabled_image) can be reused in the
    [`<canvas>`](canvas) element without being *tainted*. The allowed
    values are:

    [`anonymous`](#anonymous)

    :   A cross-origin request (i.e. with an
        [`Origin`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Origin)
        HTTP header) is performed, but no credential is sent (i.e. no
        cookie, X.509 certificate, or HTTP Basic authentication). If the
        server does not give credentials to the origin site (by not
        setting the
        [`Access-Control-Allow-Origin`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Origin)
        HTTP header) the resource will be tainted and its usage
        restricted.

    [`use-credentials`](#use-credentials)

    :   A cross-origin request (i.e. with an `Origin` HTTP header) is
        performed along with a credential sent (i.e. a cookie,
        certificate, and/or HTTP Basic authentication is performed). If
        the server does not give credentials to the origin site (through
        [`Access-Control-Allow-Credentials`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Credentials)
        HTTP header), the resource will be *tainted* and its usage
        restricted.

    If the attribute is not present, the resource is fetched without a
    [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS)
    request (i.e. without sending the `Origin` HTTP header), preventing
    its non-tainted usage. If invalid, it is handled as if the
    enumerated keyword **anonymous** was used. See [CORS settings
    attributes](../attributes/crossorigin) for additional information.

[`disabled`](#disabled) [Non-standard]

:   For `rel="stylesheet"` only, the `disabled` Boolean attribute
    indicates whether the described stylesheet should be loaded and
    applied to the document. If `disabled` is specified in the HTML when
    it is loaded, the stylesheet will not be loaded during page load.
    Instead, the stylesheet will be loaded on-demand, if and when the
    `disabled` attribute is changed to `false` or removed.

    Setting the `disabled` property in the DOM causes the stylesheet to
    be removed from the document\'s
    [`Document.styleSheets`](https://developer.mozilla.org/en-US/docs/Web/API/Document/styleSheets)
    list.

[`fetchpriority`](#fetchpriority) [Experimental]

:   Provides a hint of the relative priority to use when fetching a
    preloaded resource. Allowed values:

    [`high`](#high)

    :   Signals a high-priority fetch relative to other resources of the
        same type.

    [`low`](#low)

    :   Signals a low-priority fetch relative to other resources of the
        same type.

    [`auto`](#auto)

    :   Default: Signals automatic determination of fetch priority
        relative to other resources of the same type.

[`href`](#href)

:   This attribute specifies the
    [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL) of the
    linked resource. A URL can be absolute or relative.

[`hreflang`](#hreflang)

:   This attribute indicates the language of the linked resource. It is
    purely advisory. Allowed values are specified by [RFC 5646: Tags for
    Identifying Languages (also known as
    BCP 47)](https://datatracker.ietf.org/doc/html/rfc5646). Use this
    attribute only if the [`href`](a#href) attribute is present.

[`imagesizes`](#imagesizes)

:   For `rel="preload"` and `as="image"` only, the `imagesizes`
    attribute is [a sizes
    attribute](https://html.spec.whatwg.org/multipage/images.html#sizes-attribute)
    that indicates to preload the appropriate resource used by an `img`
    element with corresponding values for its `srcset` and `sizes`
    attributes.

[`imagesrcset`](#imagesrcset)

:   For `rel="preload"` and `as="image"` only, the `imagesrcset`
    attribute is [a sourceset
    attribute](https://html.spec.whatwg.org/multipage/images.html#srcset-attribute)
    that indicates to preload the appropriate resource used by an `img`
    element with corresponding values for its `srcset` and `sizes`
    attributes.

[`integrity`](#integrity)

:   Contains inline metadata --- a base64-encoded cryptographic hash of
    the resource (file) you\'re telling the browser to fetch. The
    browser can use this to verify that the fetched resource has been
    delivered free of unexpected manipulation. See [Subresource
    Integrity](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity).

[`media`](#media)

:   This attribute specifies the media that the linked resource applies
    to. Its value must be a media type / [media
    query](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries).
    This attribute is mainly useful when linking to external stylesheets
    --- it allows the user agent to pick the best adapted one for the
    device it runs on.

    **Note:**

    -   In HTML 4, this can only be a simple white-space-separated list
        of media description literals, i.e., [media types and
        groups](https://developer.mozilla.org/en-US/docs/Web/CSS/@media),
        where defined and allowed as values for this attribute, such as
        `print`, `screen`, `aural`, `braille`. HTML5 extended this to
        any kind of [media
        queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries),
        which are a superset of the allowed values of HTML 4.
    -   Browsers not supporting [CSS Media
        Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries)
        won\'t necessarily recognize the adequate link; do not forget to
        set fallback links, the restricted set of media queries defined
        in HTML 4.

[`referrerpolicy`](#referrerpolicy)

:   A string indicating which referrer to use when fetching the
    resource:

    -   `no-referrer` means that the
        [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer)
        header will not be sent.
    -   `no-referrer-when-downgrade` means that no
        [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer)
        header will be sent when navigating to an origin without TLS
        (HTTPS). This is a user agent\'s default behavior, if no policy
        is otherwise specified.
    -   `origin` means that the referrer will be the origin of the page,
        which is roughly the scheme, the host, and the port.
    -   `origin-when-cross-origin` means that navigating to other
        origins will be limited to the scheme, the host, and the port,
        while navigating on the same origin will include the referrer\'s
        path.
    -   `unsafe-url` means that the referrer will include the origin and
        the path (but not the fragment, password, or username). This
        case is unsafe because it can leak origins and paths from
        TLS-protected resources to insecure origins.

[`rel`](#rel)

:   This attribute names a relationship of the linked document to the
    current document. The attribute must be a space-separated list of
    [link type values](../attributes/rel).

[`sizes`](#sizes) [Experimental]

:   This attribute defines the sizes of the icons for visual media
    contained in the resource. It must be present only if the
    [`rel`](#rel) contains a value of `icon` or a non-standard type such
    as Apple\'s `apple-touch-icon`. It may have the following values:

    -   `any`, meaning that the icon can be scaled to any size as it is
        in a vector format, like `image/svg+xml`.
    -   a white-space separated list of sizes, each in the format
        `<width in pixels>x<height in pixels>` or
        `<width in pixels>X<height in pixels>`. Each of these sizes must
        be contained in the resource.

     
    **Note:** Most icon formats are only able to store one single icon;
    therefore, most of the time, the [`sizes`](#sizes) attribute
    contains only one entry. MS\'s ICO format does, as well as Apple\'s
    ICNS. ICO is more ubiquitous, so you should use this format if
    cross-browser support is a concern (especially for old IE versions).

[`title`](#title)

:   The `title` attribute has special semantics on the `<link>` element.
    When used on a `<link rel="stylesheet">` it defines a [default or an
    alternate
    stylesheet](https://developer.mozilla.org/en-US/docs/Web/CSS/Alternative_style_sheets).

[`type`](#type)

:   This attribute is used to define the type of the content linked to.
    The value of the attribute should be a MIME type such as
    **text/html**, **text/css**, and so on. The common use of this
    attribute is to define the type of stylesheet being referenced (such
    as **text/css**), but given that CSS is the only stylesheet language
    used on the web, not only is it possible to omit the `type`
    attribute, but is actually now recommended practice. It is also used
    on `rel="preload"` link types, to make sure the browser only
    downloads file types that it supports.

### Non-standard attributes

[`methods`](#methods) [Non-standard]

:   The value of this attribute provides information about the functions
    that might be performed on an object. The values generally are given
    by the HTTP protocol when it is used, but it might (for similar
    reasons as for the **title** attribute) be useful to include
    advisory information in advance in the link. For example, the
    browser might choose a different rendering of a link as a function
    of the methods specified; something that is searchable might get a
    different icon, or an outside link might render with an indication
    of leaving the current site. This attribute is not well understood
    nor supported, even by the defining browser, Internet Explorer 4.

[`target`](#target) [Deprecated]

:   Defines the frame or window name that has the defined linking
    relationship or that will show the rendering of any linked resource.

### Obsolete attributes

[`charset`](#charset) [Deprecated]

:   This attribute defines the character encoding of the linked
    resource. The value is a space- and/or comma-delimited list of
    character sets as defined in [RFC
    2045](https://datatracker.ietf.org/doc/html/rfc2045). The default
    value is `iso-8859-1`.

    **Note:** To produce the same effect as this obsolete attribute, use
    the
    [`Content-Type`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type)
    HTTP header on the linked resource.

[`rev`](#rev) [Deprecated]

:   The value of this attribute shows the relationship of the current
    document to the linked document, as defined by the [`href`](#href)
    attribute. The attribute thus defines the reverse relationship
    compared to the value of the `rel` attribute. [Link type
    values](../attributes/rel) for the attribute are similar to the
    possible values for [`rel`](#rel).

    **Note:** Instead of `rev`, you should use the [`rel`](#rel)
    attribute with the opposite [link type value](../attributes/rel).
    For example, to establish the reverse link for `made`, specify
    `author`. Also, this attribute doesn\'t stand for \"revision\" and
    must not be used with a version number, even though many sites
    misuse it in this way.

Examples
--------

### Including a stylesheet

To include a stylesheet in a page, use the following syntax:

[html]

```html
<link href="style.css" rel="stylesheet" />
```

### Providing alternative stylesheets

You can also specify [alternative style
sheets](https://developer.mozilla.org/en-US/docs/Web/CSS/Alternative_style_sheets).

The user can choose which style sheet to use by choosing it from the
**View \> Page Style** menu. This provides a way for users to see
multiple versions of a page.

[html]

```html
<link href="default.css" rel="stylesheet" title="Default Style" />
<link href="fancy.css" rel="alternate stylesheet" title="Fancy" />
<link href="basic.css" rel="alternate stylesheet" title="Basic" />
```

### Providing icons for different usage contexts

You can include links to several icons on the same page, and the browser
will choose which one works best for its particular context using the
`rel` and `sizes` values as hints.

[html]

```html
<!-- third-generation iPad with high-resolution Retina display: -->
<link rel="apple-touch-icon" sizes="144x144" href="favicon144.png" />
<!-- iPhone with high-resolution Retina display: -->
<link rel="apple-touch-icon" sizes="114x114" href="favicon114.png" />
<!-- first- and second-generation iPad: -->
<link rel="apple-touch-icon" sizes="72x72" href="favicon72.png" />
<!-- non-Retina iPhone, iPod Touch, and Android 2.1+ devices: -->
<link rel="apple-touch-icon" href="favicon57.png" />
<!-- basic favicon -->
<link rel="icon" href="favicon32.png" />
```

### Conditionally loading resources with media queries

You can provide a media type or query inside a `media` attribute; this
resource will then only be loaded if the media condition is true. For
example:

[html]

```html
<link href="print.css" rel="stylesheet" media="print" />
<link href="mobile.css" rel="stylesheet" media="all" />
<link
  href="desktop.css"
  rel="stylesheet"
  media="screen and (min-width: 600px)" />
<link
  href="highres.css"
  rel="stylesheet"
  media="screen and (min-resolution: 300dpi)" />
```

### Stylesheet load events

You can determine when a style sheet has been loaded by watching for a
`load` event to fire on it; similarly, you can detect if an error has
occurred while processing a style sheet by watching for an `error`
event:

[html]

```html
<script>
  const stylesheet = document.querySelector("#my-stylesheet");

  stylesheet.onload = () => {
    // Do something interesting; the sheet has been loaded
  };

  stylesheet.onerror = () => {
    console.log("An error occurred loading the stylesheet!");
  };
</script>

<link rel="stylesheet" href="mystylesheet.css" id="my-stylesheet" />
```

**Note:** The `load` event fires once the stylesheet and all of its
imported content has been loaded and parsed, and immediately before the
styles start being applied to the content.

### Preload examples

You can find a number of `<link rel="preload">` examples in [Preloading
content with `rel="preload"`](../attributes/rel/preload).

### Blocking rendering till a resource is fetched

You can include `render` token inside a `blocking` attribute; the
rendering of the page will be blocked till the resource is fetched. For
example:

[html]

```html
<link blocking="render" href="critical-font.woff2" as="font" />
```

Technical summary
-----------------

  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   Metadata content. If `itemprop` is present: [Flow content](../content_categories#flow_content) and [phrasing content](../content_categories#phrasing_content).
  Permitted content                             None; it is a [void element](https://developer.mozilla.org/en-US/docs/Glossary/Void_element).
  Tag omission                                  As it is a void element, the start tag must be present and the end tag must not be present
  Permitted parents                             Any element that accepts metadata elements. If [itemprop](../global_attributes/itemprop) is present: any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            [`link`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/link_role) with `href` attribute
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLLinkElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement)
  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-link-element]](https://html.spec.whatwg.org/multipage/semantics.html#the-link-element)

  ----------------------------------------------------------------------------------------------------

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

`link`

1

12

1

Yes

≤12.1

≤4

4.4

18

4

≤12.1

≤3.2

1.0

`blocking`

105

105

No

No

91

No

105

105

No

72

No

20.0

`charset`

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

`crossorigin`

34

17

18Before Firefox 83, `crossorigin` is not supported for `rel="icon"`.

No

21

10

37

34

18Before Firefox 83, `crossorigin` is not supported for `rel="icon"`.

21

10

2.0

`disabled`

1In Chrome and other Blink-based browsers, adding the `disabled`
attribute using JavaScript does not remove the stylesheet from
`document.styleSheets`.

12Since Edge 79, adding the `disabled` attribute using JavaScript does
not remove the stylesheet from `document.styleSheets`.

1

≤6

≤12.1In Chrome and other Blink-based browsers, adding the `disabled`
attribute using JavaScript does not remove the stylesheet from
`document.styleSheets`.

≤4

4.4In Chrome and other Blink-based browsers, adding the `disabled`
attribute using JavaScript does not remove the stylesheet from
`document.styleSheets`.

18In Chrome and other Blink-based browsers, adding the `disabled`
attribute using JavaScript does not remove the stylesheet from
`document.styleSheets`.

4

≤12.1In Chrome and other Blink-based browsers, adding the `disabled`
attribute using JavaScript does not remove the stylesheet from
`document.styleSheets`.

≤3.2

1.0In Samsung Internet and other Blink-based browsers, adding the
`disabled` attribute using JavaScript does not remove the stylesheet
from `document.styleSheets`.

`fetchpriority`

101

101

No

No

No

preview

101

101

No

70

No

19.0

`href`

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

`hreflang`

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

`imagesizes`

73

79

78

No

60

No

73

73

79

52

No

11.0

`imagesrcset`

73

79

78

No

60

No

73

73

79

52

No

11.0

`integrity`

45

17

43

No

32

11.1

45

45

43

32

11.3

5.0

`media`

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

`methods`

No

12--79

No

4

No

No

No

No

No

No

No

No

`referrerpolicy`

51

79

50

No

38

14

51

51

50

41

14

7.2

`rel`

1

12

1

Yes

9

1

4.4

18

4

10.1

1

1.0

`rev`

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

`sizes`

≤80

80

≤72

No

67

6

80

80

79

57

6

13.0

`target`

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

`title`

1

12

1

Yes

Yes

≤4

Yes

Yes

4

Yes

≤3.2

Yes

`type`

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

- [`Link`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Link)
    HTTP header
- [The `integrity` attribute](https://150daysofhtml.com/book/day010/)
    on 150daysofhtml.com (2021)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link>>
