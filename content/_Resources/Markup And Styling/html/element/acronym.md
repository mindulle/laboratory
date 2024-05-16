\<acronym\>
===========

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

Summary
-------

The `<acronym>` [HTML](../index) element allows authors to clearly
indicate a sequence of characters that compose an acronym or
abbreviation for a word.

**Warning:** Don\'t use this element. Use the [`<abbr>`](abbr) element
instead.

Attributes
----------

This element only has [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md), which
are common to all elements.

DOM Interface
-------------

This element implements the
[`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
interface.

Examples
--------

[html]

```html
<p>
  The <acronym title="World Wide Web">WWW</acronym> is only a component of the
  Internet.
</p>
```

### Result

Default styling
---------------

Though the purpose of this tag is purely for the convenience of the
author, its default styling varies from one browser to another:

- Opera, Firefox, Chrome, and some others add a dotted underline to
    the content of the element.
- A few browsers not only add a dotted underline, but also put it in
    small caps; to avoid this styling, adding something like
    [`font-variant`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant)`: none`
    in the CSS takes care of this case.

It is therefore recommended that web authors either explicitly style
this element, or accept some cross-browser variation.

Specifications
--------------

  ---------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  acronym]](https://html.spec.whatwg.org/multipage/obsolete.html#acronym)

  ---------------------------------------------------------------------------------

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

`acronym`

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

See also
--------

- The [`<abbr>`](abbr) HTML element

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/acronym>>
