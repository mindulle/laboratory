\<img\>: The Image Embed element
================================

The `<img>` [HTML](../index) element embeds an image into the document.

Try it
------

The above example shows usage of the `<img>` element:

- The `src` attribute is **required**, and contains the path to the
    image you want to embed.
- The `alt` attribute holds a textual replacement for the image, which
    is mandatory and **incredibly useful** for accessibility --- screen
    readers read the attribute value out to their users so they know
    what the image means. Alt text is also displayed on the page if the
    image can\'t be loaded for some reason: for example, network errors,
    content blocking, or linkrot.

There are many other attributes to achieve various purposes:

- [Referrer](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy)/[CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS)
    control for security and privacy: see [`crossorigin`](#crossorigin)
    and [`referrerpolicy`](#referrerpolicy).
- Use both [`width`](#width) and [`height`](#height) to set the
    intrinsic size of the image, allowing it to take up space before it
    loads, to mitigate content layout shifts.
- Responsive image hints with [`sizes`](#sizes) and
    [`srcset`](#srcset) (see also the [`<picture>`](picture) element and
    our [Responsive
    images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)
    tutorial).

Supported image formats
-----------------------

The HTML standard doesn\'t list what image formats to support, so [user
agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
may support different formats.

**Note:** The [Image file type and format
guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types)
provides comprehensive information about image formats and their web
browser support. This section is just a summary!

The image file formats that are most commonly used on the web are:

- [APNG (Animated Portable Network
    Graphics)](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#apng_animated_portable_network_graphics)
    --- Good choice for lossless animation sequences (GIF is less
    performant)
- [AVIF (AV1 Image File
    Format)](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#avif_image)
    --- Good choice for both images and animated images due to high
    performance.
- [GIF (Graphics Interchange
    Format)](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#gif_graphics_interchange_format)
    --- Good choice for *simple* images and animations.
- [JPEG (Joint Photographic Expert Group
    image)](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#jpeg_joint_photographic_experts_group_image)
    --- Good choice for lossy compression of still images (currently the
    most popular).
- [PNG (Portable Network
    Graphics)](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#png_portable_network_graphics)
    --- Good choice for lossless compression of still images (slightly
    better quality than JPEG).
- [SVG (Scalable Vector
    Graphics)](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#svg_scalable_vector_graphics)
    --- Vector image format. Use for images that must be drawn
    accurately at different sizes.
- [WebP (Web Picture
    format)](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#webp_image)
    --- Excellent choice for both images and animated images

Formats like
[WebP](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#webp_image)
and
[AVIF](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#avif_image)
are recommended as they perform much better than PNG, JPEG, GIF for both
still and animated images. WebP is widely supported while AVIF lacks
support in Edge.

SVG remains the recommended format for images that must be drawn
accurately at different sizes.

Image loading errors
--------------------

If an error occurs while loading or rendering an image, and an `onerror`
event handler has been set for the
[`error`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/error_event)
event, that event handler will get called. This can happen in several
situations, including:

- The `src` attribute is empty (`""`) or `null`.
- The `src`
    [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL) is the
    same as the URL of the page the user is currently on.
- The image is corrupted in some way that prevents it from being
    loaded.
- The image\'s metadata is corrupted in such a way that it\'s
    impossible to retrieve its dimensions, and no dimensions were
    specified in the `<img>` element\'s attributes.
- The image is in a format not supported by the [user
    agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`alt`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/alt#usage_notes)

:   Defines text that can replace the image in the page.

    **Note:** Browsers do not always display images. There are a number
    of situations in which a browser might not display images, such as:

    -   Non-visual browsers (such as those used by people with visual
        impairments)
    -   The user chooses not to display images (saving bandwidth,
        privacy reasons)
    -   The image is invalid or an [unsupported
        type](#supported_image_formats)

    In these cases, the browser may replace the image with the text in
    the element\'s `alt` attribute. For these reasons and others,
    provide a useful value for `alt` whenever possible.
    

    Setting this attribute to an empty string (`alt=""`) indicates that
    this image is *not* a key part of the content (it\'s decoration or a
    tracking pixel), and that non-visual browsers may omit it from
    [rendering](https://developer.mozilla.org/en-US/docs/Glossary/Rendering_engine).
    Visual browsers will also hide the broken image icon if the `alt`
    attribute is empty and the image failed to display.

    This attribute is also used when copying and pasting the image to
    text, or saving a linked image to a bookmark.

[`crossorigin`](#crossorigin)

:   Indicates if the fetching of the image must be done using a
    [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS)
    request. Image data from a [CORS-enabled
    image](../cors_enabled_image) returned from a CORS request can be
    reused in the [`<canvas>`](canvas) element without being marked
    \"[tainted](../cors_enabled_image#what_is_a_tainted_canvas)\".

    If the `crossorigin` attribute is *not* specified, then a non-CORS
    request is sent (without the
    [`Origin`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Origin)
    request header), and the browser marks the image as tainted and
    restricts access to its image data, preventing its usage in
    [`<canvas>`](canvas) elements.

    If the `crossorigin` attribute *is* specified, then a CORS request
    is sent (with the
    [`Origin`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Origin)
    request header); but if the server does not opt into allowing
    cross-origin access to the image data by the origin site (by not
    sending any
    [`Access-Control-Allow-Origin`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Origin)
    response header, or by not including the site\'s origin in any
    [`Access-Control-Allow-Origin`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Origin)
    response header it does send), then the browser blocks the image
    from loading, and logs a CORS error to the devtools console.

    Allowed values:

    [`anonymous`](#anonymous)

    :   A CORS request is sent with credentials omitted (that is, no
        [cookies](https://developer.mozilla.org/en-US/docs/Glossary/Cookie),
        [X.509
        certificates](https://datatracker.ietf.org/doc/html/rfc5280), or
        [`Authorization`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization)
        request header).

    [`use-credentials`](#use-credentials)

    :   The CORS request is sent with any credentials included (that is,
        cookies, X.509 certificates, and the `Authorization` request
        header). If the server does not opt into sharing credentials
        with the origin site (by sending back the
        `Access-Control-Allow-Credentials: true` response header), then
        the browser marks the image as tainted and restricts access to
        its image data.

    If the attribute has an invalid value, browsers handle it as if the
    `anonymous` value was used. See [CORS settings
    attributes](../attributes/crossorigin) for additional information.

[`decoding`](#decoding)

:   This attribute provides a hint to the browser as to whether it
    should perform image decoding along with rendering the other DOM
    content in a single presentation step that looks more \"correct\"
    (`sync`), or render and present the other DOM content first and then
    decode the image and present it later (`async`). In practice,
    `async` means that the next paint does not wait for the image to
    decode.

    It is often difficult to perceive any noticeable effect when using
    `decoding` on static `<img>` elements. They\'ll likely be initially
    rendered as empty images while the image files are fetched (either
    from the network or from the cache) and then handled independently
    anyway, so the \"syncing\" of content updates is less apparent.
    However, the blocking of rendering while decoding happens, while
    often quite small, *can* be measured --- even if it is difficult to
    observe with the human eye. See [What does the image decoding
    attribute actually
    do?](https://www.tunetheweb.com/blog/what-does-the-image-decoding-attribute-actually-do/)
    for a more detailed analysis (tunetheweb.com, 2023).

    Using different `decoding` types can result in more noticeable
    differences when dynamically inserting `<img>` elements into the DOM
    via JavaScript --- see
    [`HTMLImageElement.decoding`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/decoding)
    for more details.

    Allowed values:

    [`sync`](#sync)

    :   Decode the image synchronously along with rendering the other
        DOM content, and present everything together.

    [`async`](#async)

    :   Decode the image asynchronously, after rendering and presenting
        the other DOM content.

    [`auto`](#auto)

    :   No preference for the decoding mode; the browser decides what is
        best for the user. This is the default value.

[`elementtiming`](#elementtiming)

:   Marks the image for observation by the
    [`PerformanceElementTiming`](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming)
    API. The value given becomes an identifier for the observed image
    element. See also the [`elementtiming`](../attributes/elementtiming)
    attribute page.

[`fetchpriority`](#fetchpriority) [Experimental]

:   Provides a hint of the relative priority to use when fetching the
    image. Allowed values:

    [`high`](#high)

    :   Signals a high-priority fetch relative to other images.

    [`low`](#low)

    :   Signals a low-priority fetch relative to other images.

    [`auto`](#auto_2)

    :   Default: Signals automatic determination of fetch priority
        relative to other images.

[`height`](#height)

:   The intrinsic height of the image, in pixels. Must be an integer
    without a unit.

    **Note:** Including `height` and [`width`](#width) enables the
    aspect ratio of the image to be calculated by the browser prior to
    the image being loaded. This aspect ratio is used to reserve the
    space needed to display the image, reducing or even preventing a
    layout shift when the image is downloaded and painted to the screen.
    Reducing layout shift is a major component of good user experience
    and web performance.

[`ismap`](#ismap)

:   This Boolean attribute indicates that the image is part of a
    [server-side
    map](https://en.wikipedia.org/wiki/Image_map#Server-side). If so,
    the coordinates where the user clicked on the image are sent to the
    server.

    **Note:** This attribute is allowed only if the `<img>` element is a
    descendant of an [`<a>`](a) element with a valid [`href`](a#href)
    attribute. This gives users without pointing devices a fallback
    destination.

[`loading`](#loading)

:   Indicates how the browser should load the image:

    [`eager`](#eager)

    :   Loads the image immediately, regardless of whether or not the
        image is currently within the visible viewport (this is the
        default value).

    [`lazy`](#lazy)

    :   Defers loading the image until it reaches a calculated distance
        from the viewport, as defined by the browser. The intent is to
        avoid the network and storage bandwidth needed to handle the
        image until it\'s reasonably certain that it will be needed.
        This generally improves the performance of the content in most
        typical use cases.

     
    **Note:** Loading is only deferred when JavaScript is enabled. This
    is an anti-tracking measure, because if a user agent supported lazy
    loading when scripting is disabled, it would still be possible for a
    site to track a user\'s approximate scroll position throughout a
    session, by strategically placing images in a page\'s markup such
    that a server can track how many images are requested and when.

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

[`sizes`](#sizes)

:   One or more strings separated by commas, indicating a set of source
    sizes. Each source size consists of:

    1.  A [media
        condition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries#syntax).
        This must be omitted for the last item in the list.
    2.  A source size value.

    Media Conditions describe properties of the *viewport*, not of the
    *image*. For example, `(max-height: 500px) 1000px` proposes to use a
    source of 1000px width, if the *viewport* is not higher than 500px.

    Source size values specify the intended display size of the image.
    [User
    agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
    use the current source size to select one of the sources supplied by
    the `srcset` attribute, when those sources are described using width
    (`w`) descriptors. The selected source size affects the [intrinsic
    size](https://developer.mozilla.org/en-US/docs/Glossary/Intrinsic_Size)
    of the image (the image\'s display size if no
    [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS) styling
    is applied). If the `srcset` attribute is absent, or contains no
    values with a width descriptor, then the `sizes` attribute has no
    effect.

[`src`](#src)

:   The image
    [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL).
    Mandatory for the `<img>` element. On
    [browsers](https://developer.mozilla.org/en-US/docs/Glossary/Browser)
    supporting `srcset`, `src` is treated like a candidate image with a
    pixel density descriptor `1x`, unless an image with this pixel
    density descriptor is already defined in `srcset`, or unless
    `srcset` contains `w` descriptors.

[`srcset`](#srcset)

:   One or more strings separated by commas, indicating possible image
    sources for the [user
    agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
    to use. Each string is composed of:

    1.  A [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL)
        to an image
    2.  Optionally, whitespace followed by one of:
        -   A width descriptor (a positive integer directly followed by
            `w`). The width descriptor is divided by the source size
            given in the `sizes` attribute to calculate the effective
            pixel density.
        -   A pixel density descriptor (a positive floating point number
            directly followed by `x`).

    If no descriptor is specified, the source is assigned the default
    descriptor of `1x`.

    It is incorrect to mix width descriptors and pixel density
    descriptors in the same `srcset` attribute. Duplicate descriptors
    (for instance, two sources in the same `srcset` which are both
    described with `2x`) are also invalid.

    If the `srcset` attribute uses width descriptors, the `sizes`
    attribute must also be present, or the `srcset` itself will be
    ignored.

    The user agent selects any of the available sources at its
    discretion. This provides them with significant leeway to tailor
    their selection based on things like user preferences or
    [bandwidth](https://developer.mozilla.org/en-US/docs/Glossary/Bandwidth)
    conditions. See our [Responsive
    images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)
    tutorial for an example.

[`width`](#width)

:   The intrinsic width of the image in pixels. Must be an integer
    without a unit.

[`usemap`](#usemap)

:   The partial
    [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL)
    (starting with `#`) of an [image map](map) associated with the
    element.

    **Note:** You cannot use this attribute if the `<img>` element is
    inside an [`<a>`](a) or [`<button>`](button) element.

### Deprecated attributes

[`align`](#align) [Deprecated]

:   Aligns the image with its surrounding context. Use the
    [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float)
    and/or
    [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)
    [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS)
    properties instead of this attribute. Allowed values:

    [`top`](#top)

    :   Equivalent to `vertical-align: top` or
        `vertical-align: text-top`

    [`middle`](#middle)

    :   Equivalent to `vertical-align: -moz-middle-with-baseline`

    [`bottom`](#bottom)

    :   The default, equivalent to `vertical-align: unset` or
        `vertical-align: initial`

    [`left`](#left)

    :   Equivalent to `float: left`

    [`right`](#right)

    :   Equivalent to `float: right`

[`border`](#border) [Deprecated]

:   The width of a border around the image. Use the
    [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border)
    [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS)
    property instead.

[`hspace`](#hspace) [Deprecated]

:   The number of pixels of white space on the left and right of the
    image. Use the
    [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)
    CSS property instead.

[`longdesc`](#longdesc) [Deprecated]

:   A link to a more detailed description of the image. Possible values
    are a [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL)
    or an element [`id`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#id).

    **Note:** This attribute is mentioned in the latest
    [W3C](https://developer.mozilla.org/en-US/docs/Glossary/W3C)
    version, [HTML
    5.2](https://html.spec.whatwg.org/multipage/obsolete.html#element-attrdef-img-longdesc),
    but has been removed from the
    [WHATWG](https://developer.mozilla.org/en-US/docs/Glossary/WHATWG)\'s
    [HTML Living
    Standard](https://html.spec.whatwg.org/multipage/embedded-content.html#the-img-element).
    It has an uncertain future; authors should use a
    [WAI](https://developer.mozilla.org/en-US/docs/Glossary/WAI)-[ARIA](https://developer.mozilla.org/en-US/docs/Glossary/ARIA)
    alternative such as
    [`aria-describedby`](https://www.w3.org/TR/wai-aria-1.1/#aria-describedby)
    or
    [`aria-details`](https://www.w3.org/TR/wai-aria-1.1/#aria-details).

[`name`](#name) [Deprecated]

:   A name for the element. Use the [`id`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#id)
    attribute instead.

[`vspace`](#vspace) [Deprecated]

:   The number of pixels of white space above and below the image. Use
    the
    [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)
    CSS property instead.

Styling with CSS
----------------

`<img>` is a [replaced
element](https://developer.mozilla.org/en-US/docs/Web/CSS/Replaced_element);
it has a
[`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
value of `inline` by default, but its default dimensions are defined by
the embedded image\'s intrinsic values, like it were `inline-block`. You
can set properties like
[`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border)/[`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius),
[`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding)/[`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin),
[`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width),
[`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height),
etc. on an image.

`<img>` has no baseline, so when images are used in an inline formatting
context with
[`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)`: baseline`,
the bottom of the image will be placed on the text baseline.

You can use the
[`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position)
property to position the image within the element\'s box, and the
[`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit)
property to adjust the sizing of the image within the box (for example,
whether the image should fit the box or fill it even if clipping is
required).

Depending on its type, an image may have an intrinsic width and height.
For some image types, however, intrinsic dimensions are unnecessary.
[SVG](https://developer.mozilla.org/en-US/docs/Glossary/SVG) images, for
instance, have no intrinsic dimensions if their root
[`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg)
element doesn\'t have a `width` or `height` set on it.

Examples
--------

### Alternative text

The following example embeds an image into the page and includes
alternative text for accessibility.

[html]

```html
<img src="favicon144.png" alt="MDN" />
```

### Image link

This example builds upon the previous one, showing how to turn the image
into a link. To do so, nest the `<img>` tag inside the [`<a>`](a). You
should make the alternative text describe the resource the link is
pointing to, as if you were using a text link instead.

[html]

```html
<a href="https://developer.mozilla.org">
  <img src="favicon144.png" alt="Visit the MDN site" />
</a>
```

### Using the srcset attribute

In this example we include a `srcset` attribute with a reference to a
high-resolution version of the logo; this will be loaded instead of the
`src` image on high-resolution devices. The image referenced in the
`src` attribute is counted as a `1x` candidate in [user
agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
that support `srcset`.

[html]

```html
<img src="favicon72.png" alt="MDN" srcset="favicon144.png 2x" />
```

### Using the srcset and sizes attributes

The `src` attribute is ignored in [user
agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
that support `srcset` when `w` descriptors are included. When the
`(max-width: 600px)` media condition matches, the 200 pixel-wide image
will load (it is the one that matches `200px` most closely), otherwise
the other image will load.

[html]

```html
<img
  src="clock-demo-200px.png"
  alt="The time is 12:45."
  srcset="clock-demo-200px.png 200w, clock-demo-400px.png 400w"
  sizes="(max-width: 600px) 200px, 50vw" />
```

**Note:** To see the resizing in action, [view the example on a separate
page](https://live.mdnplay.dev/en-US/docs/Web/HTML/Element/img/_sample_.Using_the_srcset_and_sizes_attributes.html?id=Using_the_srcset_and_sizes_attributes&amp;url=%2Fen-US%2Fdocs%2FWeb%2FHTML%2FElement%2Fimg),
so you can actually resize the content area.

Security and privacy concerns
-----------------------------

Although `<img>` elements have innocent uses, they can have undesirable
consequences for user security and privacy. See [Referer header: privacy
and security
concerns](https://developer.mozilla.org/en-US/docs/Web/Security/Referer_header:_privacy_and_security_concerns)
for more information and mitigations.

Accessibility concerns
----------------------

### Authoring meaningful alternate descriptions

An `alt` attribute\'s value should provide a clear and concise text
replacement for the image\'s content. It should not describe the
presence of the image itself or the file name of the image. If the `alt`
attribute is purposefully left off because the image has no textual
equivalent, consider alternate methods to present what the image is
trying to communicate.

#### Don\'t

[html]

```html
<img alt="image" src="penguin.jpg" />
```

#### Do

[html]

```html
<img alt="A Rockhopper Penguin is standing on a beach." src="penguin.jpg" />
```

When an `alt` attribute is not present on an image, some screen readers
may announce the image\'s file name instead. This can be a confusing
experience if the file name isn\'t representative of the image\'s
contents.

- [An alt Decision Tree • Images • WAI Web Accessibility
    Tutorials](https://www.w3.org/WAI/tutorials/images/decision-tree/)
- [Alt-texts: The Ultimate Guide --- Axess
    Lab](https://axesslab.com/alt-texts/)
- [How to Design Great Alt Text: An Introduction \|
    Deque](https://www.deque.com/blog/great-alt-text-introduction/)
- [MDN Understanding WCAG, Guideline 1.1
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.1_%E2%80%94_providing_text_alternatives_for_non-text_content)
- [Understanding Success Criterion 1.1.1 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/text-equiv-all.html)

### Identifying SVG as an image

Due to a [VoiceOver bug](https://webkit.org/b/216364), VoiceOver does
not correctly announce SVG images as images. Include
[`role="img"`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/img_role)
to all `<img>` elements with SVG source files to ensure assistive
technologies correctly announce the SVG as image content.

[html]

```html
<img src="mdn.svg" alt="MDN" role="img" />
```

### The title attribute

The [`title`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#title) attribute is not an acceptable
substitute for the `alt` attribute. Additionally, avoid duplicating the
`alt` attribute\'s value in a `title` attribute declared on the same
image. Doing so may cause some screen readers to announce the same text
twice, creating a confusing experience.

The `title` attribute should also not be used as supplemental captioning
information to accompany an image\'s `alt` description. If an image
needs a caption, use the [`figure`](figure) and
[`figcaption`](figcaption) elements.

The value of the `title` attribute is usually presented to the user as a
tooltip, which appears shortly after the cursor stops moving over the
image. While this *can* provide additional information to the user, you
should not assume that the user will ever see it: the user may only have
keyboard or touchscreen. If you have information that\'s particularly
important or valuable for the user, present it inline using one of the
methods mentioned above instead of using `title`.

- [Using the HTML title attribute -- updated \| The Paciello
    Group](https://www.tpgi.com/using-the-html-title-attribute-updated/)

Technical summary
-----------------

+-----------------------------------+-----------------------------------+
| [Content                          | [Flow                             |
| c                                 | content](../                      |
| ategories](../content_categories) | content_categories#flow_content), |
|                                   | [phrasing                         |
|                                   | content](../cont                  |
|                                   | ent_categories#phrasing_content), |
|                                   | [embedded                         |
|                                   | content](../cont                  |
|                                   | ent_categories#embedded_content), |
|                                   | [palpable                         |
|                                   | content](../cont                  |
|                                   | ent_categories#palpable_content). |
|                                   | If the element has a `usemap`     |
|                                   | attribute, it also is a part of   |
|                                   | the interactive content category. |
+-----------------------------------+-----------------------------------+
| Permitted content                 | None; it is a [void               |
|                                   | element                           |
|                                   | ](https://developer.mozilla.org/e>> |
|                                   | n-US/docs/Glossary/Void_element). |
+-----------------------------------+-----------------------------------+
| Tag omission                      | Must have a start tag and must    |
|                                   | not have an end tag.              |
+-----------------------------------+-----------------------------------+
| Permitted parents                 | Any element that accepts embedded |
|                                   | content.                          |
+-----------------------------------+-----------------------------------+
| Implicit ARIA role                | -   with non-empty `alt`          |
|                                   |     attribute or no `alt`         |
|                                   |     attribute: `img`              |
|                                   | -   with empty `alt` attribute:   |
|                                   |     [`pres                        |
|                                   | entation`](https://developer.mozi>> |
|                                   | lla.org/en-US/docs/Web/Accessibil |
|                                   | ity/ARIA/Roles/presentation_role) |
+-----------------------------------+-----------------------------------+
| Permitted ARIA roles              | -   with non-empty `alt`          |
|                                   |     attribute:                    |
|                                   |     -   `button`                  |
|                                   |     -   `checkbox`                |
|                                   |     -   [`link`](https://develo>>   |
|                                   | per.mozilla.org/en-US/docs/Web/Ac |
|                                   | cessibility/ARIA/Roles/link_role) |
|                                   |     -                             |
|                                   |   [`menuitem`](https://developer>>. |
|                                   | mozilla.org/en-US/docs/Web/Access |
|                                   | ibility/ARIA/Roles/menuitem_role) |
|                                   |     -   [`menuitemchec            |
|                                   | kbox`](https://developer.mozilla>>. |
|                                   | org/en-US/docs/Web/Accessibility/ |
|                                   | ARIA/Roles/menuitemcheckbox_role) |
|                                   |     -   [`menuit                  |
|                                   | emradio`](https://developer.mozil>> |
|                                   | la.org/en-US/docs/Web/Accessibili |
|                                   | ty/ARIA/Roles/menuitemradio_role) |
|                                   |                                   |
|                                   |   -   [`option`](https://develope>> |
|                                   | r.mozilla.org/en-US/docs/Web/Acce |
|                                   | ssibility/ARIA/Roles/option_role) |
|                                   |     -   [`pr                      |
|                                   | ogressbar`](https://developer.moz>> |
|                                   | illa.org/en-US/docs/Web/Accessibi |
|                                   | lity/ARIA/Roles/progressbar_role) |
|                                   |     -                             |
|                                   | [`scrollbar`](https://developer.m>> |
|                                   | ozilla.org/en-US/docs/Web/Accessi |
|                                   | bility/ARIA/Roles/scrollbar_role) |
|                                   |     -                             |
|                                   | [`separator`](https://developer.m>> |
|                                   | ozilla.org/en-US/docs/Web/Accessi |
|                                   | bility/ARIA/Roles/separator_role) |
|                                   |                                   |
|                                   |   -   [`slider`](https://develope>> |
|                                   | r.mozilla.org/en-US/docs/Web/Acce |
|                                   | ssibility/ARIA/Roles/slider_role) |
|                                   |     -   `switch`                  |
|                                   |     -   `tab`                     |
|                                   |     -                             |
|                                   |   [`treeitem`](https://developer>>. |
|                                   | mozilla.org/en-US/docs/Web/Access |
|                                   | ibility/ARIA/Roles/treeitem_role) |
|                                   | -   with empty `alt` attribute,   |
|                                   |     [`none`](https://develo>>       |
|                                   | per.mozilla.org/en-US/docs/Web/Ac |
|                                   | cessibility/ARIA/Roles/none_role) |
|                                   |     or                            |
|                                   |     [`pres                        |
|                                   | entation`](https://developer.mozi>> |
|                                   | lla.org/en-US/docs/Web/Accessibil |
|                                   | ity/ARIA/Roles/presentation_role) |
|                                   | -   with no `alt` attribute, no   |
|                                   |     `role` permitted              |
+-----------------------------------+-----------------------------------+
| DOM interface                     | [`HTMLImageElement`](             |
|                                   | https://developer.mozilla.org/en->> |
|                                   | US/docs/Web/API/HTMLImageElement) |
+-----------------------------------+-----------------------------------+

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-img-element]](https://html.spec.whatwg.org/multipage/embedded-content.html#the-img-element)

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

`img`

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

`align`

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

`alt`

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

`aspect_ratio_computed_from_attributes`

79

79

71

No

66

15

14--15Safari doesn\'t preserve space for images without a valid `src`,
which may disrupt layouts that rely on lazy loading (see [bug
224197](https://webkit.org/b/224197)).

79

79

79

57

15

14--15Safari doesn\'t preserve space for images without a valid `src`,
which may disrupt layouts that rely on lazy loading (see [bug
224197](https://webkit.org/b/224197)).

12.0

`attributionsrc`

117

117

No

No

103

No

117

117

No

No

No

No

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

`crossorigin`

13

12

8

Yes

15

6

4.4

18

8

14

6

1.0

`decoding`

65

≤79

63

No

52

11.1

65

65

63

47

11.3

9.0

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

`hspace`

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

`ismap`

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

`loading`

77

79

75

No

64

15.4

77

77

79

55

15.4

12.0

`longdesc`

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

`onerror`

Yes

≤79

51

No

Yes

Yes

Yes

Yes

51

Yes

Yes

Yes

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

`sizes`

38

12

38

Yes

25

9.1

38

38

38

25

9.3

3.0

`src`

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

`srcset`

34

≤18

38

No

21

8

37

34

38

21

8

2.0

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

`vspace`

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

- [`<picture>`](picture), [`<object>`](object), and [`<embed>`](embed)
    elements
- [`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit),
    [`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position),
    [`image-orientation`](https://developer.mozilla.org/en-US/docs/Web/CSS/image-orientation),
    [`image-rendering`](https://developer.mozilla.org/en-US/docs/Web/CSS/image-rendering),
    and
    [`image-resolution`](https://developer.mozilla.org/en-US/docs/Web/CSS/image-resolution):
    Image-related CSS properties.
- [`HTMLImageElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement)
    interface for this element
- [Images in
    HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML)
- [Image file type and format
    guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types)
- [Responsive
    images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img>>
