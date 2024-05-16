\<xmp\>
=======

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

Summary
-------

The `<xmp>` [HTML](../index) element renders text between the start and
end tags without interpreting the HTML in between and using a monospaced
font. The HTML2 specification recommended that it should be rendered
wide enough to allow 80 characters per line.

**Note:** Do not use this element.

- It has been deprecated since HTML3.2 and was not implemented in a
    consistent way. It was completely removed from current HTML.
- Use the [`<pre>`](pre) element or, if semantically adequate, the
    [`<code>`](code) element instead. Note that you will need to escape
    the \'`<`\' character as \'`&lt;`\' and the \'`&`\' character as
    \'`&amp;`\' to make sure they are not interpreted as markup.
- A monospaced font can also be obtained on any element, by applying
    an adequate [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
    style using `monospace` as the generic-font value for the
    [`font-family`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family)
    property.

Attributes
----------

This element has no other attributes than the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md), common to all elements.

DOM interface
-------------

This element implements the
[`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
interface.

Specifications
--------------

  -------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------

  [HTML Standard\
  [\#
  xmp]](https://html.spec.whatwg.org/multipage/obsolete.html#xmp)

  -------------------------------------------------------------------------

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

`xmp`

1

12

1Before Firefox 4, this element implemented the `HTMLSpanElement`
interface instead of the standard `HTMLElement` interface.

Yes

15

≤4

4.4

18

4Before Firefox 4, this element implemented the `HTMLSpanElement`
interface instead of the standard `HTMLElement` interface.

14

≤3.2

1.0

See also
--------

- The [`<pre>`](pre) and [`<code>`](code) elements to be used instead.
- The [`<plaintext>`](plaintext) element, similar to [`<xmp>`](xmp)
    but also obsolete.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/xmp>>
