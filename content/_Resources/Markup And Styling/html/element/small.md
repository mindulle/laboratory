\<small\>: the side comment element
===================================

The `<small>` [HTML](../index) element represents side-comments and
small print, like copyright and legal text, independent of its styled
presentation. By default, it renders text within it one font-size
smaller, such as from `small` to `x-small`.

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Examples
--------

### Basic usage

[html]

```html
<p>
  This is the first sentence.
  <small>This whole sentence is in small letters.</small>
</p>
```

#### Result

### CSS alternative

[html]

```html
<p>
  This is the first sentence.
  <span style="font-size:0.8em">This whole sentence is in small letters.</span>
</p>
```

#### Result

Notes
-----

Although the `<small>` element, like the [`<b>`](b) and [`<i>`](i)
elements, may be perceived to violate the principle of separation
between structure and presentation, all three are valid in HTML. Authors
are encouraged to use their best judgement when determining whether to
use `<small>` or CSS.

Technical summary
-----------------

  ---------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Content categories     [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content)
  Permitted content      [Phrasing content](../content_categories#phrasing_content)
  Tag omission           None; must have both a start tag and an end tag.
  Permitted parents      Any element that accepts [phrasing content](../content_categories#phrasing_content), or any element that accepts [flow content](../content_categories#flow_content).
  Implicit ARIA role     `generic`
  Permitted ARIA roles   Any
  DOM interface          [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  ---------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -----------------------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-small-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-small-element)

  -----------------------------------------------------------------------------------------------------------------

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

`small`

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

- [`<b>`](b)
- [`<sub>`](sub) and [`<sup>`](sup)
- [`<font>`](font)
- [`<style>`](style)
- HTML 4.01 Specification: [Font
    Styles](https://www.w3.org/TR/html4/present/graphics.html#h-15.2)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/small>>
