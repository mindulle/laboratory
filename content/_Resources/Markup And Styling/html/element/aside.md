\<aside\>: The Aside element
============================

The `<aside>` [HTML](../index) element represents a portion of a
document whose content is only indirectly related to the document\'s
main content. Asides are frequently presented as sidebars or call-out
boxes.

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

- Do not use the `<aside>` element to tag parenthesized text, as this
    kind of text is considered part of the main flow.

Examples
--------

### Using \<aside\>

This example uses `<aside>` to mark up a paragraph in an article. The
paragraph is only indirectly related to the main article content:

[html]

```html
<article>
  <p>
    The Disney movie <cite>The Little Mermaid</cite> was first released to
    theatres in 1989.
  </p>
  <aside>
    <p>The movie earned $87 million during its initial release.</p>
  </aside>
  <p>More info about the movie…</p>
</article>
```

#### Result

Technical summary
-----------------

  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [sectioning content](../content_categories#sectioning_content), [palpable content](../content_categories#palpable_content).
  Permitted content                             [Flow content](../content_categories#flow_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content). Note that an `<aside>` element must not be a descendant of an [`<address>`](address) element.
  Implicit ARIA role                            `complementary`
  Permitted ARIA roles                          [`feed`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/feed_role), [`none`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/none_role), [`note`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/note_role), [`presentation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role), [`region`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/region_role), [`search`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/search_role)
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -----------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-aside-element]](https://html.spec.whatwg.org/multipage/sections.html#the-aside-element)

  -----------------------------------------------------------------------------------------------------

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

`aside`

5

12

4

9

11.1

5

4.4

18

4

11.1

4.2

1.0

See also
--------

- Other section-related elements: [`<body>`](body),
    [`<article>`](article), [`<section>`](section), [`<nav>`](nav),
    [h1](heading_elements), [h2](heading_elements),
    [h3](heading_elements), [h4](heading_elements),
    [h5](heading_elements), [h6](heading_elements),
    [`<hgroup>`](hgroup), [`<header>`](header), [`<footer>`](footer),
    [`<address>`](address);
- [Using HTML sections and outlines](heading_elements)
- [ARIA: Complementary
    role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/complementary_role)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside>>
