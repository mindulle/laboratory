\<b\>: The Bring Attention To element
=====================================

The `<b>` [HTML](../index) element is used to draw the reader\'s
attention to the element\'s contents, which are not otherwise granted
special importance. This was formerly known as the Boldface element, and
most browsers still draw the text in boldface. However, you should not
use `<b>` for styling text or granting importance. If you wish to create
boldface text, you should use the CSS
[`font-weight`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight)
property. If you wish to indicate an element is of special importance,
you should use the [`<strong>`](strong) element.

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

- Use the `<b>` for cases like keywords in a summary, product names in
    a review, or other spans of text whose typical presentation would be
    boldfaced (but not including any special importance).
- Do not confuse the `<b>` element with the [`<strong>`](strong),
    [`<em>`](em), or [`<mark>`](mark) elements. The [`<strong>`](strong)
    element represents text of certain *importance*, [`<em>`](em) puts
    some emphasis on the text and the [`<mark>`](mark) element
    represents text of certain *relevance*. The `<b>` element doesn\'t
    convey such special semantic information; use it only when no others
    fit.
- Similarly, do not mark titles and headings using the `<b>` element.
    For this purpose, use the [h1](heading_elements) to
    [h6](heading_elements) tags. Further, stylesheets can change the
    default style of these elements, with the result that they are not
    *necessarily* displayed in bold.
- It is a good practice to use the
    [`class`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#class) attribute on the `<b>` element
    in order to convey additional semantic information as needed (for
    example `<b class="lead">` for the first sentence in a paragraph).
    This makes it easier to manage multiple use cases of `<b>` if your
    stylistic needs change, without the need to change all of its uses
    in the HTML.
- Historically, the `<b>` element was meant to make text boldface.
    Styling information has been deprecated since HTML4, so the meaning
    of the `<b>` element has been changed.
- If there is no semantic purpose to using the `<b>` element, you
    should use the CSS
    [`font-weight`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight)
    property with the value `"bold"` instead in order to make text bold.

Examples
--------

[html]

```html
<p>
  This article describes several <b class="keywords">text-level</b> elements. It
  explains their usage in an <b class="keywords">HTML</b> document.
</p>
Keywords are displayed with the default style of the
<b>element, likely in bold.</b>
```

### Result

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            `generic`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-b-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-b-element)

  ---------------------------------------------------------------------------------------------------------

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

`b`

1

12

1Before Firefox 4, this element implemented the `HTMLSpanElement`
interface instead of the standard `HTMLElement` interface.

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

- Other elements conveying text-level semantics: [`<a>`](a),
    [`<em>`](em), [`<strong>`](strong), [`<small>`](small),
    [`<cite>`](cite), [`<q>`](q), [`<dfn>`](dfn), [`<abbr>`](abbr),
    [`<time>`](time), [`<code>`](code), [`<var>`](var),
    [`<samp>`](samp), [`<kbd>`](kbd), [`<sub>`](sub), [`<sup>`](sup),
    [`<i>`](i), [`<mark>`](mark), [`<ruby>`](ruby), [`<rp>`](rp),
    [`<rt>`](rt), [`<bdo>`](bdo), [`<span>`](span), [`<br>`](br),
    [`<wbr>`](wbr).
- [Using \<b\> and \<i\> elements
    (W3C)](https://www.w3.org/International/questions/qa-b-and-i-tags)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/b>>
