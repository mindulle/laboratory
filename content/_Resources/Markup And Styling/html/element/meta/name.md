Standard metadata names
=======================

The [`<meta>`](../meta) element can be used to provide document metadata
in terms of name-value pairs, with the [`name`](../meta#name) attribute
giving the metadata name, and the [`content`](../meta#content) attribute
giving the value.

### Standard metadata names defined in the HTML specification

The HTML specification defines the following set of standard metadata
names:

- `application-name`: the name of the application running in the web
    page.

    **Note:**

  - Browsers may use this to identify the application. It is
        different from the [`<title>`](../title) element, which usually
        contain the application name, but may also contain information
        like the document name or a status.
  - Simple web pages shouldn\'t define an application-name.

- `author`: the name of the document\'s author.
- `description`: a short and accurate summary of the content of the
    page. Several browsers, like Firefox and Opera, use this as the
    default description of bookmarked pages.
- `generator`: the identifier of the software that generated the page.
- `keywords`: words relevant to the page\'s content separated by
    commas.
- `referrer`: controls the HTTP
    [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer)
    header of requests sent from the document:

      ----------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
      `no-referrer`                       Do not send a HTTP [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer) header.
      `origin`                            Send the [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin) of the document.
      `no-referrer-when-downgrade`        Send the full URL when the destination is at least as secure as the current page (HTTP(S)→HTTPS), but send no referrer when it\'s less secure (HTTPS→HTTP). This is the default behavior.
      `origin-when-cross-origin`          Send the full URL (stripped of parameters) for same-origin requests, but only send the origin for other cases.
      `same-origin`                       Send the full URL (stripped of parameters) for same-origin requests. Cross-origin requests will contain no referrer header.
      `strict-origin`                     Send the origin when the destination is at least as secure as the current page (HTTP(S)→HTTPS), but send no referrer when it\'s less secure (HTTPS→HTTP).
      `strict-origin-when-cross-origin`   Send the full URL (stripped of parameters) for same-origin requests. Send the origin when the destination is at least as secure as the current page (HTTP(S)→HTTPS). Otherwise, send no referrer.
      `unsafe-URL`                        Send the full URL (stripped of parameters) for same-origin or cross-origin requests.
      ----------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

      :  Values for the `content` attribute of `<meta name="referrer">`

    **Note:**

  - Dynamically inserting `<meta name="referrer">` (with
        [`document.write()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/write)
        or
        [`appendChild()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild))
        makes the referrer behavior unpredictable.
  - When several conflicting policies are defined, the `no-referrer`
        policy is applied.

- [`theme-color`](name/theme-color): indicates a suggested color that
    user agents should use to customize the display of the page or of
    the surrounding user interface. The `content` attribute contains a
    valid CSS
    [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value).
    The `media` attribute with a valid media query list can be included
    to set the media the theme color metadata applies to.
- `color-scheme`: specifies one or more color schemes with which the
    document is compatible. The browser will use this information in
    tandem with the user\'s browser or device settings to determine what
    colors to use for everything from background and foregrounds to form
    controls and scrollbars. The primary use for
    `<meta name="color-scheme">` is to indicate compatibility with---and
    order of preference for---light and dark color modes. The value of
    the [`content`](../meta#content) property for `color-scheme` may be
    one of the following:

    [`normal`](#normal)

    :   The document is unaware of color schemes and should be rendered
        using the default color palette.

    [\[](#sect3)`light` \| `dark`\]+

    :   One or more color schemes supported by the document. Specifying
        the same color scheme more than once has the same effect as
        specifying it only once. Indicating multiple color schemes
        indicates that the first scheme is preferred by the document,
        but that the second specified scheme is acceptable if the user
        prefers it.

    [`only light`](#only_light)

    :   Indicates that the document *only* supports light mode, with a
        light background and dark foreground colors. By specification,
        `only dark` *is not valid*, because forcing a document to render
        in dark mode when it isn\'t truly compatible with it can result
        in unreadable content; all major browsers default to light mode
        if not otherwise configured.

    For example, to indicate that a document prefers dark mode but does
    render functionally in light mode as well:

    [html]

    ```html
    <meta name="color-scheme" content="dark light" />
    ```

    This works at the document level in the same way that the CSS
    [`color-scheme`](https://developer.mozilla.org/en-US/docs/Web/CSS/color-scheme)
    property lets individual elements specify their preferred and
    accepted color schemes. Your styles can adapt to the current color
    scheme using the
    [`prefers-color-scheme`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme)
    CSS media feature.

### Standard metadata names defined in other specifications

The CSS Device Adaptation specification defines the following metadata
name:

- `viewport`: gives hints about the size of the initial size of the
    [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport).

    +-----------------------+-----------------------+-----------------------+
    | Value                 | Possible subvalues    | Description           |
    +=======================+=======================+=======================+
    | `width`               | A positive integer    | Defines the pixel     |
    |                       | number, or the text   | width of the viewport |
    |                       | `device-width`        | that you want the     |
    |                       |                       | website to be         |
    |                       |                       | rendered at.          |
    +-----------------------+-----------------------+-----------------------+
    | `height`              | A positive integer,   | Defines the height of |
    |                       | or the text           | the viewport. Not     |
    |                       | `device-height`       | used by any browser.  |
    +-----------------------+-----------------------+-----------------------+
    | `initial-scale`       | A positive number     | Defines the ratio     |
    |                       | between `0.0` and     | between the device    |
    |                       | `10.0`                | width (`device-width` |
    |                       |                       | in portrait mode or   |
    |                       |                       | `device-height` in    |
    |                       |                       | landscape mode) and   |
    |                       |                       | the viewport size.    |
    +-----------------------+-----------------------+-----------------------+
    | `maximum-scale`       | A positive number     | Defines the maximum   |
    |                       | between `0.0` and     | amount to zoom in. It |
    |                       | `10.0`                | must be greater or    |
    |                       |                       | equal to the          |
    |                       |                       | `minimum-scale` or    |
    |                       |                       | the behavior is       |
    |                       |                       | undefined. Browser    |
    |                       |                       | settings can ignore   |
    |                       |                       | this rule and iOS10+  |
    |                       |                       | ignores it by         |
    |                       |                       | default.              |
    +-----------------------+-----------------------+-----------------------+
    | `minimum-scale`       | A positive number     | Defines the minimum   |
    |                       | between `0.0` and     | zoom level. It must   |
    |                       | `10.0`                | be smaller or equal   |
    |                       |                       | to the                |
    |                       |                       | `maximum-scale` or    |
    |                       |                       | the behavior is       |
    |                       |                       | undefined. Browser    |
    |                       |                       | settings can ignore   |
    |                       |                       | this rule and iOS10+  |
    |                       |                       | ignores it by         |
    |                       |                       | default.              |
    +-----------------------+-----------------------+-----------------------+
    | `user-scalable`       | `yes` or `no`         | If set to `no`, the   |
    |                       |                       | user is not able to   |
    |                       |                       | zoom in the webpage.  |
    |                       |                       | The default is `yes`. |
    |                       |                       | Browser settings can  |
    |                       |                       | ignore this rule, and |
    |                       |                       | iOS10+ ignores it by  |
    |                       |                       | default.              |
    +-----------------------+-----------------------+-----------------------+
    | `viewport-fit`        | `auto`, `contain` or  | The `auto` value      |
    |                       | `cover`               | doesn\'t affect the   |
    |                       |                       | initial layout        |
    |                       |                       | viewport, and the     |
    |                       |                       | whole web page is     |
    |                       |                       | viewable.             |
    |                       |                       |                       |
    |                       |                       | The `contain` value   |
    |                       |                       | means that the        |
    |                       |                       | viewport is scaled to |
    |                       |                       | fit the largest       |
    |                       |                       | rectangle inscribed   |
    |                       |                       | within the display.   |
    |                       |                       |                       |
    |                       |                       | The `cover` value     |
    |                       |                       | means that the        |
    |                       |                       | viewport is scaled to |
    |                       |                       | fill the device       |
    |                       |                       | display. It is highly |
    |                       |                       | recommended to make   |
    |                       |                       | use of the [safe area |
    |                       |                       | inset](https://dev>>    |
    |                       |                       | eloper.mozilla.org/en |
    |                       |                       | -US/docs/Web/CSS/env) |
    |                       |                       | variables to ensure   |
    |                       |                       | that important        |
    |                       |                       | content doesn\'t end  |
    |                       |                       | up outside the        |
    |                       |                       | display.              |
    +-----------------------+-----------------------+-----------------------+

    :  Values for the content of `<meta name="viewport">`

    **Warning:**

    Disabling zooming capabilities by setting `user-scalable` to a value
    of `no` prevents people experiencing low vision conditions from
    being able to read and understand page content.

  - [MDN Understanding WCAG, Guideline 1.4
        explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
  - [Understanding Success Criterion 1.4.4 \| W3C Understanding WCAG
        2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html)

### Other metadata names

The [WHATWG Wiki MetaExtensions
page](https://wiki.whatwg.org/wiki/MetaExtensions) contains a large set
of non-standard metadata names that have not been formally accepted yet;
however, some of the names included there are already used quite
commonly in practice --- including the following:

- `creator`: the name of the creator of the document, such as an
    organization or institution. If there are more than one, several
    [`<meta>`](../meta) elements should be used.
- `googlebot`, a synonym of `robots`, is only followed by Googlebot
    (the indexing crawler for Google).
- `publisher`: the name of the document\'s publisher.
- `robots`: the behavior that cooperative crawlers, or \"robots\",
    should use with the page. It is a comma-separated list of the values
    below:

      Value            Description                                                                   Used by
      ---------------- ----------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
      `index`          Allows the robot to index the page (default).                                 All
      `noindex`        Requests the robot to not index the page.                                     All
      `follow`         Allows the robot to follow the links on the page (default).                   All
      `nofollow`       Requests the robot to not follow the links on the page.                       All
      `all`            Equivalent to `index, follow`                                                 [Google](https://developers.google.com/search/docs/advanced/crawling/special-tags?visit_id=637855965067987211-415685194&rd=1)
      `none`           Equivalent to `noindex, nofollow`                                             [Google](https://developers.google.com/search/docs/advanced/crawling/special-tags?visit_id=637855965074074862-574753619&rd=1)
      `noarchive`      Requests the search engine not to cache the page content.                     [Google](https://developers.google.com/search/docs/advanced/robots/robots_meta_tag), [Yahoo](https://help.yahoo.com/kb/search-for-desktop/SLN2213.html), [Bing](https://www.bing.com/webmasters/help/which-robots-metatags-does-bing-support-5198d240)
      `nosnippet`      Prevents displaying any description of the page in search engine results.     [Google](https://developers.google.com/search/docs/advanced/robots/robots_meta_tag), [Bing](https://www.bing.com/webmasters/help/which-robots-metatags-does-bing-support-5198d240)
      `noimageindex`   Requests this page not to appear as the referring page of an indexed image.   [Google](https://developers.google.com/search/docs/advanced/robots/robots_meta_tag)
      `nocache`        Synonym of `noarchive`.                                                       [Bing](https://www.bing.com/webmasters/help/which-robots-metatags-does-bing-support-5198d240)

    **Note:**

  - Only cooperative robots follow these rules. Do not expect to
        prevent email harvesters with them.
  - The robot still needs to access the page in order to read these
        rules. To prevent bandwidth consumption, use a
        *[robots.txt](https://developer.mozilla.org/en-US/docs/Glossary/Robots.txt)*
        file.
  - If you want to remove a page, `noindex` will work, but only
        after the robot visits the page again. Ensure that the
        `robots.txt` file is not preventing revisits.
  - Some values are mutually exclusive, like `index` and `noindex`,
        or `follow` and `nofollow`. In these cases the robot\'s behavior
        is undefined and may vary between them.
  - Some crawler robots, like Google, Yahoo and Bing, support the
        same values for the HTTP header `X-Robots-Tag`; this allows
        non-HTML documents like images to use these rules.

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\# standard-metadata-names]](https://html.spec.whatwg.org/multipage/semantics.html#standard-metadata-names)

[Referrer Policy\
  [\#
  referrer-policy-delivery-meta]](https://w3c.github.io/webappsec-referrer-policy/#referrer-policy-delivery-meta)
  -------------------------------------------------------------------------------------------------------------------------

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

`name`

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

`color-scheme`

81

81

96

No

68

12.1

81

81

96

No

12.2

13.0

`referrer`

17Until Chrome 46, `content` values weren\'t constrained to the values
listed in the spec.

79

36The `referrer` value wasn\'t taken into account when navigation was
happening via the context menu or middle click until Firefox 39.

11Browsers initially supported an [early
draft](https://wiki.whatwg.org/wiki/Meta_referrer) of the specification
which can only use a meta tag and is only compatible with the `origin`
value from the new spec.

15Until Opera 46, `content` values weren\'t constrained to the values
listed in the spec.

11.1

37Until Chrome 46, `content` values weren\'t constrained to the values
listed in the spec.

18Until Chrome 46, `content` values weren\'t constrained to the values
listed in the spec.

36The `referrer` value wasn\'t taken into account when navigation was
happening via the context menu or middle click until Firefox 39.

No

12

1.0Until Samsung Internet 5.0, `content` values weren\'t constrained to
the values listed in the spec.

`scheme`

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

`theme-color`

73Chrome uses the color only on installed progressive web apps.

39--72Chrome reports support, but does not actually use the color
anywhere.

79Edge uses the color only on installed progressive web apps.

No

No

No

15

No

80Chrome for Android does not use the color on devices with native dark
mode enabled.

No

No

15

6.2

See also
--------

- [Viewport `<meta>` tag](../../viewport_meta_tag)
- [Metadata: the `<meta>`
    element](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#metadata_the_meta_element)
    in [What\'s in the head? Metadata in
    HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta/name>>
