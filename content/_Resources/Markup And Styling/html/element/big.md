\<big\>: The Bigger Text element
================================

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

The `<big>` [HTML](../index) deprecated element renders the enclosed
text at a font size one level larger than the surrounding text (`medium`
becomes `large`, for example). The size is capped at the browser\'s
maximum permitted font size.

**Warning:** This element has been removed from the specification and
shouldn\'t be used anymore. Use the CSS
[`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size)
property to adjust the font size.

Attributes
----------

This element has no other attributes than the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md), common to all elements.

Examples
--------

Here we see examples showing the use of `<big>` followed by an example
showing how to accomplish the same results using modern CSS syntax
instead.

### Using big

This example uses the obsolete `<big>` element to increase the size of
some text.

#### HTML

[html]

```html
<p>
  This is the first sentence.
  <big>This whole sentence is in bigger letters.</big>
</p>
```

#### Result

### Using CSS `font-size`

This example uses the CSS
[`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size)
property to increase the font size by one level.

#### CSS

[css]

```css
.bigger {
  font-size: larger;
}

```

#### HTML

[html]

```html
<p>
  This is the first sentence.
  <span class="bigger">This whole sentence is in bigger letters.</span>
</p>
```

#### Result

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
  big]](https://html.spec.whatwg.org/multipage/obsolete.html#big)

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

`big`

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

See also
--------

- CSS:
    [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size),
    [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font)
- HTML: [`<small>`](small), [`<font>`](font), [`<style>`](style)
- HTML 4.01 Specification: [Font
    Styles](https://www.w3.org/TR/html4/present/graphics.html#h-15.2)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/big>>
