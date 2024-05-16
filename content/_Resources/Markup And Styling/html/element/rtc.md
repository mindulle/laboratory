\<rtc\>: The Ruby Text Container element
========================================

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

The `<rtc>` [HTML](../index) element embraces semantic annotations of
characters presented in a ruby of [`<rb>`](rb) elements used inside of
[`<ruby>`](ruby) element. [`<rb>`](rb) elements can have both
pronunciation ([`<rt>`](rt)) and semantic ([`<rtc>`](rtc)) annotations.

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Examples
--------

[html]

```html
<div class="info">
  <ruby>
    <rtc>
      <rb>旧</rb><rt>jiù</rt>
      <rb>金</rb><rt>jīn</rt>
      <rb>山</rb><rt>shān</rt>
    </rtc>
    <rtc>San Francisco</rtc>
  </ruby>
</div>
```

### Result

Technical summary
-----------------

  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   None.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content) or [`<rt>`](rt) elements.
  Tag omission                                  The closing tag can be omitted if it is immediately followed by a [`<rb>`](rb), [`<rtc>`](rtc) or [`<rt>`](rt) element opening tag or by its parent closing tag.
  Permitted parents                             A [`<ruby>`](ruby) element.
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------

  [HTML Standard\
  [\#
  rtc]](https://html.spec.whatwg.org/multipage/obsolete.html#rtc)

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

`rtc`

≤80

80

33

No

67

≤13.1

80

80

33

57

≤13.4

13.0

See also
--------

- [`<ruby>`](ruby)
- [`<rp>`](rp)
- [`<rb>`](rb)
- [`<rt>`](rt)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rtc>>
