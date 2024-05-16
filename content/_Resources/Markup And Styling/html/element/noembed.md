\<noembed\>: The Embed Fallback element
=======================================

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

The `<noembed>` [HTML](../index) element is an obsolete, non-standard
way to provide alternative, or \"fallback\", content for browsers that
do not support the [`<embed>`](embed) element or do not support the type
of [embedded content](../content_categories#embedded_content) an author
wishes to use. This element was deprecated in HTML 4.01 and above in
favor of placing fallback content between the opening and closing tags
of an [`<object>`](object) element.

**Note:** While this element currently still works in many browsers, it
is obsolete and should not be used. Use [`<object>`](object) instead,
with fallback content between the opening and closing tags of the
element.

Examples
--------

The message inside `<noembed>` tag will appear only when your browser
does not support `<embed>` tag.

### Show an alternative content

[html]

```html
<embed type="vide/webm" src="/media/examples/flower.mp4" width="200" height="200">
  <noembed>
    <h1>Alternative content</h1>
  </noembed>
</embed>
```

Specifications
--------------

  ---------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  noembed]](https://html.spec.whatwg.org/multipage/obsolete.html#noembed)

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

`noembed`

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

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/noembed>>
