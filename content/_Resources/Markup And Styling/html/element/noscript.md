\<noscript\>: The Noscript element
==================================

The `<noscript>` [HTML](../index) element defines a section of HTML to
be inserted if a script type on the page is unsupported or if scripting
is currently turned off in the browser.

  ------------------------------------ -------------------------------------------------------------------------------
  [Content                             [Metadata content](../content_categories#metadata_content), [flow
  categories](../content_categories)   content](../content_categories#flow_content), [phrasing
                                       content](../content_categories#phrasing_content).

  Permitted content                    When scripting is disabled and when it is a descendant of the [`<head>`](head)
                                       element: in any order, zero or more [`<link>`](link) elements, zero or more
                                       [`<style>`](style) elements, and zero or more [`<meta>`](meta) elements.\
                                       When scripting is disabled and when it isn\'t a descendant of the
                                       [`<head>`](head) element: any [transparent
                                       content](../content_categories#transparent_content_model), but no `<noscript>`
                                       element must be among its descendants.\
                                       Otherwise: flow content or phrasing content.

  Tag omission                         None, both the starting and ending tag are mandatory.

  Permitted parents                    Any element that accepts [phrasing
                                       content](../content_categories#phrasing_content), if there are no ancestor
                                       `<noscript>` element, or in a [`<head>`](head) element (but only for an HTML
                                       document), here again if there are no ancestor `<noscript>` element.

  Implicit ARIA role                   [No corresponding
                                       role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)

  Permitted ARIA roles                 No `role` permitted

  DOM interface                        [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  ------------------------------------ -------------------------------------------------------------------------------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Examples
--------

[html]

```html
<noscript>
  <!-- anchor linking to external file -->
  <a href="https://www.mozilla.org/">External Link</a>
</noscript>
<p>Rocks!</p>
```

### Result with scripting enabled

Rocks!

### Result with scripting disabled

[External Link](https://www.mozilla.org/)

Rocks!

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-noscript-element]](https://html.spec.whatwg.org/multipage/scripting.html#the-noscript-element)

  ------------------------------------------------------------------------------------------------------------

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

`noscript`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/noscript>>
