\<iframe\>: The Inline Frame element
====================================

The `<iframe>` [HTML](../index) element represents a nested [browsing
context](https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context),
embedding another HTML page into the current one.

Try it
------

Each embedded browsing context has its own
[document](https://developer.mozilla.org/en-US/docs/Web/API/Document)
and allows URL navigations. The navigations of each embedded browsing
context are linearized into the [session
history](https://developer.mozilla.org/en-US/docs/Web/API/History) of
the *topmost* browsing context. The browsing context that embeds the
others is called the *parent browsing context*. The *topmost* browsing
context --- the one with no parent --- is usually the browser window,
represented by the
[`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window)
object.

**Warning:** Because each browsing context is a complete document
environment, every `<iframe>` in a page requires increased memory and
other computing resources. While theoretically you can use as many
`<iframe>`s as you like, check for performance problems.

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`allow`](#allow)

:   Specifies a [Permissions
    Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Permissions_Policy)
    for the `<iframe>`. The policy defines what features are available
    to the `<iframe>` (for example, access to the microphone, camera,
    battery, web-share, etc.) based on the origin of the request.

    **Note:** A Permissions Policy specified by the `allow` attribute
    implements a further restriction on top of the policy specified in
    the
    [`Permissions-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Permissions-Policy)
    header. It doesn\'t replace it.

[`allowfullscreen`](#allowfullscreen)

:   Set to `true` if the `<iframe>` can activate fullscreen mode by
    calling the
    [`requestFullscreen()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/requestFullscreen)
    method.

    **Note:** This attribute is considered a legacy attribute and
    redefined as `allow="fullscreen"`.

[`allowpaymentrequest`](#allowpaymentrequest) [Experimental]

:   Set to `true` if a cross-origin `<iframe>` should be allowed to
    invoke the [Payment Request
    API](https://developer.mozilla.org/en-US/docs/Web/API/Payment_Request_API).

    **Note:** This attribute is considered a legacy attribute and
    redefined as `allow="payment"`.

[`credentialless`](#credentialless) [Experimental]

:   Set to `true` to make the `<iframe>` credentialless, meaning that
    its content will be loaded in a new, ephemeral context. It doesn\'t
    have access to the network, cookies, and storage data associated
    with its origin. It uses a new context local to the top-level
    document lifetime. In return, the
    [`Cross-Origin-Embedder-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Embedder-Policy)
    (COEP) embedding rules can be lifted, so documents with COEP set can
    embed third-party documents that do not. See [IFrame
    credentialless](https://developer.mozilla.org/en-US/docs/Web/Security/IFrame_credentialless)
    for more details.

[`csp`](#csp) [Experimental]

:   A [Content Security
    Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP)
    enforced for the embedded resource. See
    [`HTMLIFrameElement.csp`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement/csp)
    for details.

[`height`](#height)

:   The height of the frame in CSS pixels. Default is `150`.

[`loading`](#loading)

:   Indicates how the browser should load the iframe:

    -   `eager`: Load the iframe immediately, regardless if it is
        outside the visible viewport (this is the default value).
    -   `lazy`: Defer loading of the iframe until it reaches a
        calculated distance from the viewport, as defined by the
        browser.

[`name`](#name)

:   A targetable name for the embedded browsing context. This can be
    used in the `target` attribute of the [`<a>`](a), [`<form>`](form),
    or [`<base>`](base) elements; the `formtarget` attribute of the
    [`<input>`](input) or [`<button>`](button) elements; or the
    `windowName` parameter in the
    [`window.open()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/open)
    method.

[`referrerpolicy`](#referrerpolicy)

:   Indicates which
    [referrer](https://developer.mozilla.org/en-US/docs/Web/API/Document/referrer)
    to send when fetching the frame\'s resource:

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

[`sandbox`](#sandbox)

:   Controls the restrictions applied to the content embedded in the
    `<iframe>`. The value of the attribute can either be empty to apply
    all restrictions, or space-separated tokens to lift particular
    restrictions:

    -   `allow-downloads`: Allows downloading files through an
        [`<a>`](a) or [`<area>`](area) element with the
        [download](a#download) attribute, as well as through the
        navigation that leads to a download of a file. This works
        regardless of whether the user clicked on the link, or JS code
        initiated it without user interaction.
    -   `allow-downloads-without-user-activation`
        [Experimental] : Allows for downloads to occur
        without a gesture from the user.
    -   `allow-forms`: Allows the page to submit forms. If this keyword
        is not used, form will be displayed as normal, but submitting it
        will not trigger input validation, sending data to a web server
        or closing a dialog.
    -   `allow-modals`: Allows the page to open modal windows by
        [`Window.alert()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/alert),
        [`Window.confirm()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/confirm),
        [`Window.print()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/print)
        and
        [`Window.prompt()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/prompt),
        while opening a [`<dialog>`](dialog) is allowed regardless of
        this keyword. It also allows the page to receive
        [`BeforeUnloadEvent`](https://developer.mozilla.org/en-US/docs/Web/API/BeforeUnloadEvent)
        event.
    -   `allow-orientation-lock`: Lets the resource [lock the screen
        orientation](https://developer.mozilla.org/en-US/docs/Web/API/Screen/lockOrientation).
    -   `allow-pointer-lock`: Allows the page to use the [Pointer Lock
        API](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_Lock_API).
    -   `allow-popups`: Allows popups (like from
        [`Window.open()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/open),
        `target="_blank"`,
        [`Window.showModalDialog()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/showModalDialog)).
        If this keyword is not used, that functionality will silently
        fail.
    -   `allow-popups-to-escape-sandbox`: Allows a sandboxed document to
        open new windows without forcing the sandboxing flags upon them.
        This will allow, for example, a third-party advertisement to be
        safely sandboxed without forcing the same restrictions upon the
        page the ad links to.
    -   `allow-presentation`: Allows embedders to have control over
        whether an iframe can start a [presentation
        session](https://developer.mozilla.org/en-US/docs/Web/API/PresentationRequest).
    -   `allow-same-origin`: If this token is not used, the resource is
        treated as being from a special origin that always fails the
        [same-origin
        policy](https://developer.mozilla.org/en-US/docs/Glossary/Same-origin_policy)
        (potentially preventing access to [data
        storage/cookies](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy#cross-origin_data_storage_access)
        and some JavaScript APIs).
    -   `allow-scripts`: Allows the page to run scripts (but not create
        pop-up windows). If this keyword is not used, this operation is
        not allowed.
    -   `allow-storage-access-by-user-activation`
        [Experimental] : Allows a document loaded in
        the `<iframe>` to use the [Storage Access
        API](https://developer.mozilla.org/en-US/docs/Web/API/Storage_Access_API)
        to request access to unpartitioned cookies.
    -   `allow-top-navigation`: Lets the resource navigate the top-level
        browsing context (the one named `_top`).
    -   `allow-top-navigation-by-user-activation`: Lets the resource
        navigate the top-level browsing context, but only if initiated
        by a user gesture.
    -   `allow-top-navigation-to-custom-protocols`: Allows navigations
        to non-`http` protocols built into browser or [registered by a
        website](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/registerProtocolHandler/Web-based_protocol_handlers).
        This feature is also activated by `allow-popups` or
        `allow-top-navigation` keyword.

     
    **Note:**

    -   When the embedded document has the same origin as the embedding
        page, it is **strongly discouraged** to use both `allow-scripts`
        and `allow-same-origin`, as that lets the embedded document
        remove the `sandbox` attribute --- making it no more secure than
        not using the `sandbox` attribute at all.
    -   Sandboxing is useless if the attacker can display content
        outside a sandboxed `iframe` --- such as if the viewer opens the
        frame in a new tab. Such content should be also served from a
        *separate origin* to limit potential damage.

[`src`](#src)

:   The URL of the page to embed. Use a value of `about:blank` to embed
    an empty page that conforms to the [same-origin
    policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy#inherited_origins).
    Also note that programmatically removing an `<iframe>`\'s src
    attribute (e.g. via
    [`Element.removeAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttribute))
    causes `about:blank` to be loaded in the frame in Firefox (from
    version 65), Chromium-based browsers, and Safari/iOS.

[`srcdoc`](#srcdoc)

:   Inline HTML to embed, overriding the `src` attribute. If a browser
    does not support the `srcdoc` attribute, it will fall back to the
    URL in the `src` attribute.

[`width`](#width)

:   The width of the frame in CSS pixels. Default is `300`.

### Deprecated attributes

These attributes are deprecated and may no longer be supported by all
user agents. You should not use them in new content, and try to remove
them from existing content.

[`align`](#align) [Deprecated]

:   The alignment of this element with respect to the surrounding
    context.

[`frameborder`](#frameborder) [Deprecated]

:   The value `1` (the default) draws a border around this frame. The
    value `0` removes the border around this frame, but you should
    instead use the CSS property
    [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border)
    to control `<iframe>` borders.

[`longdesc`](#longdesc) [Deprecated]

:   A URL of a long description of the frame\'s content. Due to
    widespread misuse, this is not helpful for non-visual browsers.

[`marginheight`](#marginheight) [Deprecated]

:   The amount of space in pixels between the frame\'s content and its
    top and bottom borders.

[`marginwidth`](#marginwidth) [Deprecated]

:   The amount of space in pixels between the frame\'s content and its
    left and right borders.

[`scrolling`](#scrolling) [Deprecated]

:   Indicates when the browser should provide a scrollbar for the frame:

    -   `auto`: Only when the frame\'s content is larger than its
        dimensions.
    -   `yes`: Always show a scrollbar.
    -   `no`: Never show a scrollbar.

Scripting
---------

Inline frames, like [`<frame>`](frame) elements, are included in the
[`window.frames`](https://developer.mozilla.org/en-US/docs/Web/API/Window/frames)
pseudo-array.

With the DOM
[`HTMLIFrameElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement)
object, scripts can access the
[`window`](https://developer.mozilla.org/en-US/docs/Web/API/Window)
object of the framed resource via the
[`contentWindow`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement/contentWindow)
property. The
[`contentDocument`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement/contentDocument)
property refers to the `document` inside the `<iframe>`, same as
`contentWindow.document`.

From the inside of a frame, a script can get a reference to its parent
window with
[`window.parent`](https://developer.mozilla.org/en-US/docs/Web/API/Window/parent).

Script access to a frame\'s content is subject to the [same-origin
policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy).
Scripts cannot access most properties in other `window` objects if the
script was loaded from a different origin, including scripts inside a
frame accessing the frame\'s parent. Cross-origin communication can be
achieved using
[`Window.postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage).

Positioning and scaling
-----------------------

As a [replaced
element](https://developer.mozilla.org/en-US/docs/Web/CSS/Replaced_element),
the position, alignment, and scaling of the embedded document within the
`<iframe>` element\'s box, can be adjusted with the
[`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position)
and
[`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit)
properties.

Examples
--------

### A simple \<iframe\>

This example embeds the page at https://example.org>> in an iframe.

#### HTML

[html]

```html
<iframe
  src="https://example.org"
  title="iframe Example 1"
  width="400"
  height="300">
</iframe>
```

#### Result

Accessibility concerns
----------------------

People navigating with assistive technology such as a screen reader can
use the [`title` attribute](../global_attributes/title) on an `<iframe>`
to label its content. The title\'s value should concisely describe the
embedded content:

[html]

```html
<iframe
  title="Wikipedia page for Avocados"
  src="https://en.wikipedia.org/wiki/Avocado"></iframe>
```

Without this title, they have to navigate into the `<iframe>` to
determine what its embedded content is. This context shift can be
confusing and time-consuming, especially for pages with multiple
`<iframe>`s and/or if embeds contain interactive content like video or
audio.

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), embedded content, interactive content, palpable content.
  Permitted content                             None.
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts embedded content.
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          [`application`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/application_role), [`document`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/document_role), [`img`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/img_role), [`none`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/none_role), [`presentation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role)
  DOM interface                                 [`HTMLIFrameElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-iframe-element]](https://html.spec.whatwg.org/multipage/iframe-embed-object.html#the-iframe-element)

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

`iframe`

1

12

1The `resize` CSS property doesn\'t have any effect on this element due
to [bug 680823](https://bugzil.la/680823).

Yes

≤15

≤4Safari has a
[bug](https://www.quirksmode.org/bugreports/archives/2005/02/hidden_iframes.html)
that prevents iframes from loading if the `iframe` element was hidden
when added to the page. `iframeElement.src = iframeElement.src` should
cause it to load the iframe.

4.4

18

4The `resize` CSS property doesn\'t have any effect on this element due
to [bug 680823](https://bugzil.la/680823).

≤14

≤3.2Safari has a
[bug](https://www.quirksmode.org/bugreports/archives/2005/02/hidden_iframes.html)
that prevents iframes from loading if the `iframe` element was hidden
when added to the page. `iframeElement.src = iframeElement.src` should
cause it to load the iframe.

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

`allow`

60

79

74

No

47

11.1

60

60

No

44

11.3

8.0

`allowfullscreen`

3817--38

12

189--18

11

2515--25

10.15.1

384.4--38

3818--38

189--18

2514--25

12Only available on iPad, not on iPhone.

3.01.0--3.0

`allowpaymentrequest`

60

79

56--83

No

47

No

60

60

56--83

44

No

8.0

`credentialless`

110

110

No

No

96

No

110

110

No

74

No

21.0

`external_protocol_urls_blocked`

No

No

67

No

No

No

No

No

67

No

No

No

`frameborder`

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

`loading`

77

79

No

No

64

16.4

77

77

No

55

16.4

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

`marginheight`

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

`marginwidth`

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

`sandbox`

4

12

17

10

15

5

4.4

18

17

14

4.2

1.0

`scrolling`

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

`src`

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

`srcdoc`

20

79

25

No

15

6

37

25

25

No

No

1.5

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

- [CSP:
    frame-ancestors](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/frame-ancestors)
- [Privacy, permissions, and information
    security](https://developer.mozilla.org/en-US/docs/Web/Privacy)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe>>
