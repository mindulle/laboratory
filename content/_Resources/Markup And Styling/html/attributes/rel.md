HTML attribute: rel
===================

The `rel` attribute defines the relationship between a linked resource
and the current document. Valid on [`<link>`](../element/link),
[`<a>`](../element/a), [`<area>`](../element/area), and
[`<form>`](../element/form), the supported values depend on the element
on which the attribute is found.

The type of relationships is given by the value of the `rel` attribute,
which, if present, must have a value that is an unordered set of unique
space-separated keywords. Differently from a `class` name, which does
not express semantics, the `rel` attribute must express tokens that are
semantically valid for both machines and humans. The current registries
for the possible values of the `rel` attribute are the [IANA link
relation
registry](https://www.iana.org/assignments/link-relations/link-relations.xhtml),
the [HTML Living
Standard](https://html.spec.whatwg.org/multipage/links.html#linkTypes),
and the freely-editable [existing-rel-values
page](https://microformats.org/wiki/existing-rel-values) in the
microformats wiki, [as
suggested](https://html.spec.whatwg.org/multipage/links.html#other-link-types)
by the Living Standard. If a `rel` attribute not present in one of the
three sources above is used some HTML validators (such as the [W3C
Markup Validation Service](https://validator.w3.org/)) will generate a
warning.

The following table lists some of the most important existing keywords.
Every keyword within a space-separated value should be unique within
that value.

  `rel` value                            Description                                                                                                                                                                                                                                                             [`<link>`](../element/link)   [`<a>`](../element/a) and [`<area>`](../element/area)   [`<form>`](../element/form)
  -------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------- ------------------------------------------------------- -----------------------------
  [`alternate`](#alternate)              Alternate representations of the current document.                                                                                                                                                                                                                      Link                          Link                                                    Not allowed
  [`author`](#author)                    Author of the current document or article.                                                                                                                                                                                                                              Link                          Link                                                    Not allowed
  [`bookmark`](#bookmark)                Permalink for the nearest ancestor section.                                                                                                                                                                                                                             Not allowed                   Link                                                    Not allowed
  [`canonical`](#canonical)              Preferred URL for the current document.                                                                                                                                                                                                                                 Link                          Not allowed                                             Not allowed
  [`dns-prefetch`](rel/dns-prefetch)     Tells the browser to preemptively perform DNS resolution for the target resource\'s origin.                                                                                                                                                                             External Resource             Not allowed                                             Not allowed
  [`external`](#external)                The referenced document is not part of the same site as the current document.                                                                                                                                                                                           Not allowed                   Annotation                                              Annotation
  [`help`](#help)                        Link to context-sensitive help.                                                                                                                                                                                                                                         Link                          Link                                                    Link
  [`icon`](#icon)                        An icon representing the current document.                                                                                                                                                                                                                              External Resource             Not allowed                                             Not allowed
  [`license`](#license)                  Indicates that the main content of the current document is covered by the copyright license. described by the referenced document.                                                                                                                                      Link                          Link                                                    Link
  [`manifest`](rel/manifest)             Web app manifest.                                                                                                                                                                                                                                                       Link                          Not allowed                                             Not allowed
  [`me`](rel/me)                         Indicates that the current document represents the person who owns the linked content.                                                                                                                                                                                  Link                          Link                                                    Not allowed
  [`modulepreload`](rel/modulepreload)   Tells to browser to preemptively fetch the script and store it in the document\'s module map for later evaluation. Optionally, the module\'s dependencies can be fetched as well.                                                                                       External Resource             Not allowed                                             Not allowed
  [`next`](#next)                        Indicates that the current document is a part of a series and that the next document in the series is the referenced document.                                                                                                                                          Link                          Link                                                    Link
  [`nofollow`](#nofollow)                Indicates that the current document\'s original author or publisher does not endorse the referenced document.                                                                                                                                                           Not allowed                   Annotation                                              Annotation
  [`noopener`](rel/noopener)             Creates a top-level browsing context that is not an auxiliary browsing context if the hyperlink would create either of those, to begin with (i.e., has an appropriate `target` attribute value).                                                                        Not allowed                   Annotation                                              Annotation
  [`noreferrer`](#noreferrer)            No `Referer` header will be included. Additionally, has the same effect as `noopener`.                                                                                                                                                                                  Not allowed                   Annotation                                              Annotation
  [`opener`](#opener)                    Creates an auxiliary browsing context if the hyperlink would otherwise create a top-level browsing context that is not an auxiliary browsing context (i.e., has \"`_blank`\" as `target` attribute value).                                                              Not allowed                   Annotation                                              Annotation
  [`pingback`](#pingback)                Gives the address of the pingback server that handles pingbacks to the current document.                                                                                                                                                                                External Resource             Not allowed                                             Not allowed
  [`preconnect`](rel/preconnect)         Specifies that the user agent should preemptively connect to the target resource\'s origin.                                                                                                                                                                             External Resource             Not allowed                                             Not allowed
  [`prefetch`](rel/prefetch)             Specifies that the user agent should preemptively fetch and cache the target resource as it is likely to be required for a followup navigation.                                                                                                                         External Resource             Not allowed                                             Not allowed
  [`preload`](rel/preload)               Specifies that the user agent must preemptively fetch and cache the target resource for current navigation according to the potential destination given by the [`as`](../element/link#as) attribute (and the priority associated with the corresponding destination).   External Resource             Not allowed                                             Not allowed
  [`prerender`](rel/prerender)           Specifies that the user agent should preemptively fetch the target resource and process it in a way that helps deliver a faster response in the future.                                                                                                                 External Resource             Not allowed                                             Not allowed
  [`prev`](#prev)                        Indicates that the current document is a part of a series and that the previous document in the series is the referenced document.                                                                                                                                      Link                          Link                                                    Link
  [`search`](#search)                    Gives a link to a resource that can be used to search through the current document and its related pages.                                                                                                                                                               Link                          Link                                                    Link
  [`stylesheet`](#stylesheet)            Imports a style sheet.                                                                                                                                                                                                                                                  External Resource             Not allowed                                             Not allowed
  [`tag`](#tag)                          Gives a tag (identified by the given address) that applies to the current document.                                                                                                                                                                                     Not allowed                   Link                                                    Not allowed

The `rel` attribute is relevant to the [`<link>`](../element/link),
[`<a>`](../element/a), [`<area>`](../element/area), and
[`<form>`](../element/form) elements, but some values only relevant to a
subset of those elements. Like all HTML keyword attribute values, these
values are case-insensitive.

The `rel` attribute has no default value. If the attribute is omitted or
if none of the values in the attribute are supported, then the document
has no particular relationship with the destination resource other than
there being a hyperlink between the two. In this case, on
[`<link>`](../element/link) and [`<form>`](../element/form), if the
`rel` attribute is absent, has no keywords, or if not one or more of the
space-separated keywords above, then the element does not create any
links. [`<a>`](../element/a) and [`<area>`](../element/area) will still
created links, but without a defined relationship.

Values
------

[`alternate`](#alternate)

:   Indicates an alternate representation of the current document. Valid
    for [`<link>`](../element/link), [`<a>`](../element/a), and
    [`<area>`](../element/area), the meaning depends on the values of
    the other attributes.

    -   With the [`stylesheet`](#stylesheet) keyword on a `<link>`, it
        creates an [alternate
        stylesheet](https://developer.mozilla.org/en-US/docs/Web/CSS/Alternative_style_sheets).
         
        [html]

        ```html
        <!-- a persistent style sheet -->
        <link rel="stylesheet" href="default.css" />
        <!-- alternate style sheets -->
        <link
          rel="alternate stylesheet"
          href="highcontrast.css"
          title="High contrast" />
        ```
        
    -   With an [`hreflang`](../element/link#hreflang) attribute that
        differs from the document language, it indicates a translation.
    -   With the [`type`](../element/link#type) attribute value of
        `"application/rss+xml"`or `"application/atom+xml"`, it creates a
        hyperlink referencing a syndication feed.
         
        [html]

        ```html
        <link
          rel="alternate"
          type="application/atom+xml"
          href="posts.xml"
          title="Blog" />
        ```
        
    -   Otherwise, it creates a hyperlink referencing an alternate
        representation of the current document, whose nature is given by
        the [`hreflang`](../element/link#hreflang) and
        [`type`](../element/link#type) attributes.
        -   If `hreflang` is given alongside `alternate`, and the value
            of `hreflang` is different from the current document\'s
            language, it indicates that the referenced document is a
            translation.
        -   If `type` is given alongside `alternate`, it indicates that
            the referenced document is an alternative format (such as a
            PDF).
        -   The `hreflang` and `type` attributes may both be given
            alongside `alternate`.

         
        [html]

        ```html
        <link
          rel="alternate"
          href="/fr/html/print"
          hreflang="fr"
          type="text/html"
          media="print"
          title="French HTML (for printing)" />
        <link
          rel="alternate"
          href="/fr/pdf"
          hreflang="fr"
          type="application/pdf"
          title="French PDF" />
        ```

[`author`](#author)

:   Indicates the referenced document provides further information about
    the author of the current document or article. Relevant for
    [`<link>`](../element/link), [`<a>`](../element/a), and
    [`<area>`](../element/area) elements.

    With [`<a>`](../element/a) and [`<area>`](../element/area), it
    indicates the linked document (or `mailto:`) provides information
    about the author of the nearest [`<article>`](../element/article)
    ancestor if there is one, otherwise the entire document.

    With [`<link>`](../element/link), it represents the author of the
    entire document.

     
    **Note:** For historical reasons, the obsolete attribute value
    `rev="made"` is treated as `rel="author"`.

[`bookmark`](#bookmark)

:   Relevant as the `rel` attribute value for the [`<a>`](../element/a)
    and [`<area>`](../element/area) elements. Gives a permalink for the
    nearest ancestor [`<article>`](../element/article) element, if there
    is one. If there is no ancestor `<article>` element, gives a
    permalink for the section the linking element is most closely
    associated with.

[`canonical`](#canonical)

:   Valid for [`<link>`](../element/link), it defines the preferred URL
    for the current document, which helps search engines reduce
    duplicate content.

[`dns-prefetch`](#dns-prefetch)

:   Relevant for the [`<link>`](../element/link) element both in the
    [`<body>`](../element/body) and [`<head>`](../element/head), it
    tells the browser to preemptively perform DNS resolution for the
    target resource\'s origin. Useful for resources the user will likely
    need, it helps reduce latency and thereby improves performance when
    the user does access the resources as the browser preemptively
    performed DNS resolution for the origin of the specified resource.
    See
    [dns-prefetch](https://developer.mozilla.org/en-US/docs/Web/Performance/dns-prefetch)
    described in [resource
    hints](https://w3c.github.io/resource-hints/).

[`external`](#external)

:   Relevant to [`<form>`](../element/form), [`<a>`](../element/a), and
    [`<area>`](../element/area), it indicates the referenced document is
    not part of the current site. This can be used with attribute
    selectors to style external links in a way that indicates to the
    user that they will be leaving the current site.

[`help`](#help)

:   Relevant to [`<form>`](../element/form),
    [`<link>`](../element/link), [`<a>`](../element/a), and
    [`<area>`](../element/area), the `help` keyword indicates that the
    linked to content provides context-sensitive help, providing
    information for the parent of the element defining the hyperlink,
    and its children. When used within `<link>`, the help is for the
    whole document. When included with [`<a>`](../element/a) and
    [`<area>`](../element/area) and supported, the default
    [`cursor`](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor)
    will be `help` instead of `pointer`.

[`icon`](#icon)

:   Valid with [`<link>`](../element/link), the linked resource
    represents the icon, a resource for representing the page in the
    user interface, for the current document.

    The most common use for the `icon` value is the favicon:

     
    [html]

    ```html
    <link rel="icon" href="favicon.ico" />
    ```
    

    If there are multiple `<link rel="icon">`s, the browser uses their
    [`media`](../element/link#media), [`type`](../element/link#type),
    and [`sizes`](../element/link#sizes) attributes to select the most
    appropriate icon. If several icons are equally appropriate, the last
    one is used. If the most appropriate icon is later found to be
    inappropriate, for example because it uses an unsupported format,
    the browser proceeds to the next-most appropriate, and so on.

     
    **Note:** The [`crossorigin`](crossorigin) attribute is not
    supported for `rel="icon"` in Chromium-based browsers. See the [open
    Chromium issue](https://crbug.com/1121645).
    

     
    **Note:** Apple\'s iOS does not use this link type, nor the
    [`sizes`](../element/link#sizes) attribute, like others mobile
    browsers do, to select a webpage icon for Web Clip or a start-up
    placeholder. Instead it uses the non-standard
    [`apple-touch-icon`](https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html#//apple_ref/doc/uid/TP40002051-CH3-SW4)
    and
    [`apple-touch-startup-image`](https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html#//apple_ref/doc/uid/TP40002051-CH3-SW6)
    respectively.
    

     
    **Note:** The `shortcut` link type is often seen before `icon`, but
    this link type is non-conforming, ignored and **web authors must not
    use it anymore**.

[`license`](#license)

:   Valid on the [`<a>`](../element/a), [`<area>`](../element/area),
    [`<form>`](../element/form), [`<link>`](../element/link) elements,
    the `license` value indicates that the hyperlink leads to a document
    describing the licensing information; that the main content of the
    current document is covered by the copyright license described by
    the referenced document. If not inside the
    [`<head>`](../element/head) element, the standard doesn\'t
    distinguish between a hyperlink applying to a specific part of the
    document or to the document as a whole. Only the data on the page
    can indicate this.

    [html]

    ```html
    <link rel="license" href="#license" />
    ```
    

     
    **Note:** Although recognized, the synonym `copyright` is incorrect
    and must be avoided.

[`manifest`](#manifest) [Experimental]

:   [Web app
    manifest](https://developer.mozilla.org/en-US/docs/Web/Manifest).
    Requires the use of the CORS protocol for cross-origin fetching.

[`modulepreload`](#modulepreload)

:   Useful for improved performance, and relevant to the
    [`<link>`](../element/link) anywhere in the document, setting
    `rel="modulepreload"` tells the browser to preemptively fetch the
    script (and dependencies) and store it in the document\'s module map
    for later evaluation. `modulepreload` links can ensure network
    fetching is done with the module ready (but not evaluated) in the
    module map before it is necessarily needed. See also
    [`modulepreload`](rel/modulepreload).

[`next`](#next)

:   Relevant to [`<form>`](../element/form),
    [`<link>`](../element/link), [`<a>`](../element/a), and
    [`<area>`](../element/area), the `next` values indicates that the
    current document is a part of a series, and that the next document
    in the series is the referenced document. When included in a
    `<link>`, browsers may assume that document will be fetched next,
    and treat it as a resource hint.

[`nofollow`](#nofollow)

:   Relevant to [`<form>`](../element/form), [`<a>`](../element/a), and
    [`<area>`](../element/area), the `nofollow` keyword tells search
    engine spiders to ignore the link relationship. The nofollow
    relationship may indicate the current document\'s owner does not
    endorse the referenced document. It is often included by Search
    Engine Optimizers pretending their link farms are not spam pages.

[`noopener`](#noopener)

:   Relevant to [`<form>`](../element/form), [`<a>`](../element/a), and
    [`<area>`](../element/area), creates a top-level browsing context
    that is not an auxiliary browsing context if the hyperlink would
    create either of those to begin with (i.e., has an appropriate
    `target` attribute value). In other words, it makes the link behave
    as if
    [`window.opener`](https://developer.mozilla.org/en-US/docs/Web/API/Window/opener)
    were null and `target="_parent"` were set.

    This is the opposite of [`opener`](#opener).

[`noreferrer`](#noreferrer)

:   Relevant to [`<form>`](../element/form), [`<a>`](../element/a), and
    [`<area>`](../element/area), including this value makes the referrer
    unknown (no `Referer` header will be included), and creates a
    top-level browsing context as if `noopener` were also set.

[`opener`](#opener)

:   Creates an auxiliary browsing context if the hyperlink would
    otherwise create a top-level browsing context that is not an
    auxiliary browsing context (i.e., has \"`_blank`\" as `target`
    attribute value). Effectively, the opposite of
    [noopener](#noopener).

[`pingback`](#pingback)

:   Gives the address of the pingback server that handles pingbacks to
    the current document. See the [Pingback
    specification](https://www.hixie.ch/specs/pingback/pingback).

[`preconnect`](#preconnect)

:   Provides a hint to the browser suggesting that it open a connection
    to the linked website in advance, without disclosing any private
    information or downloading any content, so that when the link is
    followed the linked content can be fetched more quickly.

[`prefetch`](#prefetch)

:   Specifies that the user agent should preemptively fetch and cache
    the target resource as it is likely to be required for a followup
    navigation. See
    [prefetch](https://developer.mozilla.org/en-US/docs/Glossary/Prefetch)
    for more information.

[`preload`](#preload)

:   Specifies that the user agent must preemptively fetch and cache the
    target resource for current navigation according to the potential
    destination given by the [`as`](../element/link#as) attribute (and
    the priority associated with the corresponding destination). See the
    page for the [`preload`](rel/preload) value.

[`prerender`](#prerender) [Deprecated]

:   Specifies that the user agent should preemptively fetch the target
    resource and process it in a way that helps deliver a faster
    response in the future, for example by fetching its subresources or
    performing some rendering.

[`prev`](#prev)

:   Similar to the [`next`](#next) keyword, relevant to
    [`<form>`](../element/form), [`<link>`](../element/link),
    [`<a>`](../element/a), and [`<area>`](../element/area), the `prev`
    values indicates that the current document is a part of a series,
    and that the link references a previous document in the series is
    the referenced document.

    Note: The synonym `previous` is incorrect and should not be used.

[`search`](#search)

:   Relevant to [`<form>`](../element/form),
    [`<link>`](../element/link), [`<a>`](../element/a), and
    [`<area>`](../element/area) elements, the `search` keywords
    indicates that the hyperlink references a document whose interface
    is specially designed for searching in the current document, site,
    and related resources, providing a link to a resource that can be
    used to search.

    If the [`type`](../element/link#type) attribute is set to
    `application/opensearchdescription+xml` the resource is an
    [OpenSearch](https://developer.mozilla.org/en-US/docs/Web/OpenSearch)
    plugin that can be easily added to the interface of Firefox.

[`stylesheet`](#stylesheet)

:   Valid for the [`<link>`](../element/link) element, it imports an
    external resource to be used as a stylesheet. The
    [`type`](../element/link#type) attribute is not needed as it\'s a
    `text/css` stylesheet, as that is the default value. If it\'s not a
    stylesheet of type `text/css` it is best to declare the type.

    While this attribute defines the link as being a stylesheet, the
    interaction with other attributes and other key terms within the rel
    value impact whether the stylesheet is downloaded and/or used.

    When used with the [`alternate`](#alternate) keyword, it defines an
    alternative style sheet. In this case, include a non-empty
    [`title`](../element/link#title).

    The external stylesheet will not be used or even downloaded if the
    media does not match the value of the
    [`media`](../element/link#media) attribute.

    Requires the use of the CORS protocol for cross-origin fetching.

[`tag`](#tag)

:   Valid for the [`<a>`](../element/a), and [`<area>`](../element/area)
    elements, it gives a tag (identified by the given address) that
    applies to the current document. The tag value denotes that the link
    refers to a document describing a tag applying to the document on
    which it is located. This link type is not meant for tags within a
    tag cloud, as those tags apply to a group of pages, whereas the
    `tag` value of the `rel` attribute is for a single document.

### Non-standard values

[`apple-touch-icon`](#apple-touch-icon)

:   Specifies the icon for a web application on an iOS device.

Specifications
--------------

  ----------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  linkTypes]](https://html.spec.whatwg.org/multipage/links.html#linkTypes)

  ----------------------------------------------------------------------------------

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

`noopener`

49

79

52Before Firefox 63, `rel="noopener"` created windows with all features
disabled by default. Starting with Firefox 63, these windows have the
same features enabled by default as any other window.

No

36

10.1

49

49

52Before Firefox 63, `rel="noopener"` created windows with all features
disabled by default. Starting with Firefox 63, these windows have the
same features enabled by default as any other window.

36

10.3

5.0

`noreferrer`

16

13

33

11Only supported in IE11 in later versions of Windows 10 (creators
update). (Per caniuse.com.)

15

5

4.4

18

33

14

4.2

1.5

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

`rel`

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

`noopener`

49

79

52Before Firefox 63, `rel="noopener"` created windows with all features
disabled by default. Starting with Firefox 63, these windows have the
same features enabled by default as any other window.

No

36

10.1

49

49

52Before Firefox 63, `rel="noopener"` created windows with all features
disabled by default. Starting with Firefox 63, these windows have the
same features enabled by default as any other window.

36

10.3

5.0

`noreferrer`

16

13

33

11Only supported in IE11 in later versions of Windows 10 (creators
update). (Per caniuse.com.)

15

5

4.4

18

33

14

4.2

1.5

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

`alternate_stylesheet`

1--48

No

3

8

15--35

No

4.4--48

18--48

4

14--35

No

1.0--5.0

`dns-prefetch`

46

≤79

3

No

33

No

46

Yes

4

No

No

Yes

`icon`

4If both ICO and PNG are available, will use ICO over PNG if ICO has
better matching sizes set. (Per caniuse.com.).

12In version 79 and later (Blink-based Edge), if both ICO and PNG are
available, will use ICO over PNG if ICO has better matching sizes set.
(Per caniuse.com.)

2Before Firefox 83, the `crossorigin` attribute is not supported for
`rel="icon"`.

11

9In version 15 and later (Blink-based Opera), if both ICO and PNG are
available, will use ICO over PNG if ICO has better matching sizes set.
(Per caniuse.com.)

3.1If both ICO and PNG are available, will ALWAYS use ICO file,
regardless of sizes set. (Per caniuse.com.)

38

18

4

No

NoDoes not use favicons at all (but may have alternative for bookmarks,
etc.). (Per caniuse.com.)

4.0

`manifest`

No

No

No

No

No

No

39

39

No

No

No

4.0

`modulepreload`

66

≤79

115

No

53

No

66

66

115

47

No

9.0

`preconnect`

46

79

39Before Firefox 41, it doesn\'t obey the `crossorigin` attribute.

No

33

11.1

46

46

39Before Firefox 41, it doesn\'t obey the `crossorigin` attribute.

33

11.3

4.0

`prefetch`

8Requires secure context

12Requires secure context

2Requires secure context

11

15Requires secure context

13.1

4.4Requires secure context

18Requires secure context

4Requires secure context

14Requires secure context

13.4

1.5Requires secure context

`preload`

50Doesn't support `as="audio"`, `as="audioworklet"`, `as="document"`,
`as="embed"`, `as="manifest"`, `as="object"`, `as="paintworklet"`,
`as="report"`, `as="sharedworker"`, `as="video"`, `as="worker"`, or
`as="xslt"`.

≤79Doesn't support `as="audio"`, `as="audioworklet"`, `as="document"`,
`as="embed"`, `as="manifest"`, `as="object"`, `as="paintworklet"`,
`as="report"`, `as="sharedworker"`, `as="video"`, `as="worker"`, or
`as="xslt"`.

85

56--57Disabled due to various web compatibility issues (e.g. [bug
1405761](https://bugzil.la/1405761)).

No

37

No

50`as="document"` is unsupported. See [bug
593267](https://crbug.com/593267).

50Doesn't support `as="audio"`, `as="audioworklet"`, `as="document"`,
`as="embed"`, `as="manifest"`, `as="object"`, `as="paintworklet"`,
`as="report"`, `as="sharedworker"`, `as="video"`, `as="worker"`, or
`as="xslt"`.

85

56--57Disabled due to various web compatibility issues (e.g. [bug
1405761](https://bugzil.la/1405761)).

No

No

5.0`as="document"` is unsupported. See [bug
593267](https://crbug.com/593267).

`prerender`

13

79

No

11

15

No

4.4

18

No

14

No

1.5

### html.elements.link.rel

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### html.elements.a.rel

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### html.elements.area.rel

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

See also
--------

- [`HTMLLinkElement.relList`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement/relList)
- [`HTMLAnchorElement.relList`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/relList)
- [`HTMLAreaElement.relList`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/relList)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/rel>>
