\<strike\>
==========

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

The `<strike>` [HTML](../index) element places a strikethrough
(horizontal line) over text.

**Warning:** This element is deprecated in HTML 4 and XHTML 1, and
obsoleted in the [HTML Living
Standard](https://html.spec.whatwg.org/multipage/obsolete.html#strike).
If semantically appropriate, i.e., if it represents *deleted* content,
use [`<del>`](del) instead. In all other cases use [`<s>`](s).

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Examples
--------

[html]

```html
&lt;strike&gt;: <strike>Today's Special: Salmon</strike> SOLD OUT<br />
&lt;s&gt;: <s>Today's Special: Salmon</s> SOLD OUT
```

### Result

Technical summary
-----------------

  --------------- -------------------------------------------------------------------------------
  DOM interface   [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------- -------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  strike]](https://html.spec.whatwg.org/multipage/obsolete.html#strike)

  -------------------------------------------------------------------------------

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

`strike`

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

- The [`<s>`](s) element.
- The [`<del>`](del) element should be used if the data has been
    *deleted*.
- The CSS
    [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration)
    property can be used to style text with a strikethrough.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strike>>
