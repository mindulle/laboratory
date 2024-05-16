HTML attribute: crossorigin
===========================

The `crossorigin` attribute, valid on the [`<audio>`](../element/audio),
[`<img>`](../element/img), [`<link>`](../element/link),
[`<script>`](../element/script), and [`<video>`](../element/video)
elements, provides support for
[CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS), defining
how the element handles cross-origin requests, thereby enabling the
configuration of the CORS requests for the element\'s fetched data.
Depending on the element, the attribute can be a CORS settings
attribute.

The `crossorigin` content attribute on media elements is a CORS settings
attribute.

These attributes are
[enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated),
and have the following possible values:

[`anonymous`](#anonymous)

:   Request uses CORS headers and credentials flag is set to
    `'same-origin'`. There is no exchange of **user credentials** via
    cookies, client-side TLS certificates or HTTP authentication, unless
    destination is the same origin.

[`use-credentials`](#use-credentials)

:   Request uses CORS headers, credentials flag is set to `'include'`
    and **user credentials** are always included.

[`""`](#sect1)

:   Setting the attribute name to an empty value, like `crossorigin` or
    `crossorigin=""`, is the same as `anonymous`.

An invalid keyword and an empty string will be handled as the
`anonymous` keyword.

By default (that is, when the attribute is not specified), CORS is not
used at all. The user agent will not ask for permission for full access
to the resource and in the case of a cross-origin request, certain
limitations will be applied based on the type of element concerned:

  Element                   Restrictions
  ------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------
  `img`, `audio`, `video`   When resource is placed in [`<canvas>`](../element/canvas), element is marked as [*tainted*](../cors_enabled_image#security_and_tainted_canvases).
  `script`                  Access to error logging via [`window.onerror`](https://developer.mozilla.org/en-US/docs/Web/API/Window/error_event) will be limited.
  `link`                    Request with no appropriate `crossorigin` header may be discarded.

**Note:** The `crossorigin` attribute is not supported for
[`rel="icon"`](rel#icon) in Chromium-based browsers. See the [open
Chromium issue](https://crbug.com/1121645).

### Example: `crossorigin` with the `<script>` element

You can use the following [`<script>`](../element/script) element to
tell a browser to execute the `https://example.com/example-framework.js`
script without sending user-credentials.

[html]

```html
<script
  src="https://example.com/example-framework.js"
  crossorigin="anonymous"></script>
```

### Example: Web manifest with credentials

The `use-credentials` value must be used when fetching a
[manifest](https://developer.mozilla.org/en-US/docs/Web/Manifest) that
requires credentials, even if the file is from the same origin.

[html]

```html
<link rel="manifest" href="/app.webmanifest" crossorigin="use-credentials" />
```

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  cors-settings-attributes]](https://html.spec.whatwg.org/multipage/urls-and-fetching.html#cors-settings-attributes)

  ----------------------------------------------------------------------------------------------------------------------------

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

`crossorigin`

33

≤18

74

12--74With `crossorigin="use-credentials"`, cookies aren\'t sent during
seek. See [bug 1532722](https://bugzil.la/1532722).

No

20

10

4.4.3

33

79

14--79With `crossorigin="use-credentials"`, cookies aren\'t sent during
seek. See [bug 1532722](https://bugzil.la/1532722).

20

10

2.0

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

`crossorigin`

19

14

14

No

12

6The `crossorigin` attribute was implemented in WebKit in WebKit [bug
81438](https://webkit.org/b/81438).

4.4

25

14

12

6The `crossorigin` attribute was implemented in WebKit in WebKit [bug
81438](https://webkit.org/b/81438).

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

### html.elements.img.crossorigin

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### html.elements.link.crossorigin

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### html.elements.script.crossorigin

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### html.elements.video.crossorigin

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

See also
--------

- [Cross-Origin Resource Sharing
    (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTML attribute: `rel`](rel)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/crossorigin>>
