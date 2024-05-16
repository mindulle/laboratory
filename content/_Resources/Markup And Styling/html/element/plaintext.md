\<plaintext\>: The Plain Text element (Deprecated)
==================================================

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

The `<plaintext>` [HTML](../index) element renders everything following
the start tag as raw text, ignoring any following HTML. There is no
closing tag, since everything after it is considered raw text.

**Warning:** Do not use this element.

- `<plaintext>` is deprecated since HTML 2, and not all browsers
    implemented it. Browsers that did implement it didn\'t do so
    consistently.
- `<plaintext>` is obsolete; browsers that accept it may instead treat
    it as a [`<pre>`](pre) element that still interprets HTML within.
- If `<plaintext>` is the first element on the page (other than any
    non-displayed elements, like [`<head>`](head)), do not use HTML at
    all. Instead serve a text file with the `text/plain`
    [MIME-type](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Configuring_server_MIME_types).
- Instead of `<plaintext>`, use the [`<pre>`](pre) element or, if
    semantically accurate (such as for inline text), the
    [`<code>`](code) element. Escape any `<`, `>` and `&` characters, to
    prevent browsers inadvertently parsing content the element content
    as HTML.
- A monospaced font can be applied to any HTML element via a
    [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
    [`font-family`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family)
    style with the `monospace` generic value.

Attributes
----------

This element has no other attributes than the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) common to all elements.

DOM interface
-------------

This element implements the
[`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
interface.

Specifications
--------------

  -------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  plaintext]](https://html.spec.whatwg.org/multipage/obsolete.html#plaintext)

  -------------------------------------------------------------------------------------

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

`plaintext`

1

12

4

1--4Before Firefox 4, this element implemented the `HTMLSpanElement`
interface instead of the standard `HTMLElement` interface.

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

See also
--------

- The [`<pre>`](pre) and [`<code>`](code) elements, which should be
    used instead.
- The [`<xmp>`](xmp) element, also obsolete, similar to
    [`<plaintext>`](plaintext).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/plaintext>>
