\<span\>: The Content Span element
==================================

The `<span>` [HTML](../index) element is a generic inline container for
phrasing content, which does not inherently represent anything. It can
be used to group elements for styling purposes (using the
[`class`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#class) or [`id`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#id)
attributes), or because they share attribute values, such as
[`lang`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#lang). It should be used only when no
other semantic element is appropriate. `<span>` is very much like a
[`<div>`](div) element, but [`<div>`](div) is a [block-level
element](https://developer.mozilla.org/en-US/docs/Glossary/Block-level_content)
whereas a `<span>` is an [inline-level
element](https://developer.mozilla.org/en-US/docs/Glossary/Inline-level_content).

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Example
-------

### Example 1

#### HTML

[html]

```html
<p><span>Some text</span></p>
```

#### Result

### Example 2

#### HTML

[html]

```html
<li>
  <span>
    <a href="portfolio.html" target="_blank">See my portfolio</a>
  </span>
</li>
```

#### CSS

[css]

```css
li span {
  background: gold;
}

```

#### Result

Technical summary
-----------------

  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content).
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content), or any element that accepts [flow content](../content_categories#flow_content).
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement)
  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-span-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-span-element)

  ---------------------------------------------------------------------------------------------------------------

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

`span`

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

- HTML [`<div>`](div) element

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span>
