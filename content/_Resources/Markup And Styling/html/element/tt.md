\<tt\>: The Teletype Text element
=================================

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

The `<tt>` [HTML](../index) element creates inline text which is
presented using the [user
agent\'s](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
default monospace font face. This element was created for the purpose of
rendering text as it would be displayed on a fixed-width display such as
a teletype, text-only screen, or line printer.

The terms **non-proportional**, **monotype**, and **monospace** are used
interchangeably and have the same general meaning: they describe a
typeface whose characters are all the same number of pixels wide.

This element is obsolete, however. You should use the more semantically
helpful [`<code>`](code), [`<kbd>`](kbd), [`<samp>`](samp), or
[`<var>`](var) elements for inline text that needs to be presented in
monospace type, or the [`<pre>`](pre) tag for content that should be
presented as a separate block.

**Note:** If none of the semantic elements are appropriate for your use
case (for example, if you need to show some content in a
non-proportional font), you should consider using the [`<span>`](span)
element, styling it as desired using CSS. The
[`font-family`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family)
property is a good place to start.

Attributes
----------

This element only includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md)

Examples
--------

### Basic example

This example uses `<tt>` to show text entered into, and output by, a
terminal application.

[html]

```html
<p>
  Enter the following at the telnet command prompt:
  <code>set localecho</code><br />

  The telnet client should display: <tt>Local Echo is on</tt>
</p>
```

#### Result

### Overriding the default font

You can override the browser\'s default font---if the browser permits
you to do so, which it isn\'t required to do---using CSS:

#### CSS

[css]

```css
tt {
  font-family: "Lucida Console", "Menlo", "Monaco", "Courier", monospace;
}

```

#### HTML

[html]

```html
<p>
  Enter the following at the telnet command prompt:
  <code>set localecho</code><br />

  The telnet client should display: <tt>Local Echo is on</tt>
</p>
```

#### Result

Usage notes
-----------

The `<tt>` element is, by default, rendered using the browser\'s default
non-proportional font. You can override this using CSS by creating a
rule using the `tt` selector, as seen in the example [Overriding the
default font](#overriding_the_default_font) above.

**Note:** User-configured changes to the default monospace font setting
may take precedence over your CSS.

Although this element wasn\'t officially deprecated in HTML 4.01, its
use was discouraged in favor of the semantic elements and/or CSS. The
`<tt>` element is obsolete in HTML 5.

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [HTML Standard\
  [\#
  tt]](https://html.spec.whatwg.org/multipage/obsolete.html#tt)

  -----------------------------------------------------------------------

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

`tt`

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

- The semantic [`<code>`](code), [`<var>`](var), [`<kbd>`](kbd), and
    [`<samp>`](samp) elements
- The [`<pre>`](pre) element for displaying preformatted text blocks

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tt>>
