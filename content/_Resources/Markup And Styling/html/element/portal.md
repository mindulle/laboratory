\<portal\>: The Portal element
==============================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `<portal>` [HTML](../index) element enables the embedding of another
HTML page into the current one for the purposes of allowing smoother
navigation into new pages.

A `<portal>` is similar to an `<iframe>`. An `<iframe>` allows a
separate [browsing
context](https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context)
to be embedded. However, the embedded content of a `<portal>` is more
limited than that of an `<iframe>`. It cannot be interacted with, and
therefore is not suitable for embedding widgets into a document.
Instead, the `<portal>` acts as a preview of the content of another
page. It can be navigated into therefore allowing for seamless
transition to the embedded content.

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`referrerpolicy`](#referrerpolicy)

:   Sets the [referrer
    policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy)
    to use when requesting the page at the URL given as the value of the
    `src` attribute.

[`src`](#src)

:   The URL of the page to embed.

Examples
--------

### Basic example

The following example will embed the contents of `https://example.com`
as a preview.

[html]

```html
<portal id="exampleportal" src="https://example.com/"></portal>
```

Accessibility concerns
----------------------

The preview displayed by a `<portal>` is not interactive, therefore does
not receive input events or focus. Therefore the embedded contents of
the portal are not exposed as elements in the [accessibility
tree](https://developer.mozilla.org/en-US/docs/Glossary/Accessibility_tree).
The portal can be navigated to and activated like a button, the default
behavior when clicking on the portal is to activate it.

Portals are given a default label which is the title of the embedded
page. If no title is present the visible text in the preview is
concatenated to create a label. The
[`aria-label`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label)
attribute can be used to override this.

Portals used for prerendering only should be hidden with the hidden HTML
attribute or the CSS
[`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
property with a value of `none`.

When using animations during portal activation the
[`prefers-reduced-motion`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion)
[media
feature](https://developer.mozilla.org/en-US/docs/Web/CSS/@media#media_features)
should be respected.

Technical summary
-----------------

  -------------------- ---------------------------------------------------------------------------------------------
  Implicit ARIA role   [button](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/button_role)
  DOM interface        [`HTMLPortalElement`]
  -------------------- ---------------------------------------------------------------------------------------------

Specifications
--------------

  ----------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------

  [Portals\
  [\#
  the-portal-element]](https://wicg.github.io/portals/#the-portal-element)

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

`portal`

85

90

No

No

73

No

?

85

No

No

No

No

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/portal>>
