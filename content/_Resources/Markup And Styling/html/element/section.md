\<section\>: The Generic Section element
========================================

The `<section>` [HTML](../index) element represents a generic standalone
section of a document, which doesn\'t have a more specific semantic
element to represent it. Sections should always have a heading, with
very few exceptions.

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

As mentioned above, `<section>` is a generic sectioning element, and
should only be used if there isn\'t a more specific element to represent
it. As an example, a navigation menu should be wrapped in a
[`<nav>`](nav) element, but a list of search results or a map display
and its controls don\'t have specific elements, and could be put inside
a `<section>`.

Also consider these cases:

- If the contents of the element represent a standalone, atomic unit
    of content that makes sense syndicated as a standalone piece (e.g. a
    blog post or blog comment, or a newspaper article), the
    [`<article>`](article) element would be a better choice.
- If the contents represent useful tangential information that works
    alongside the main content, but is not directly part of it (like
    related links, or an author bio), use an [`<aside>`](aside).
- If the contents represent the main content area of a document, use
    [`<main>`](main).
- If you are only using the element as a styling wrapper, use a
    [`<div>`](div) instead.

To reiterate, each `<section>` should be identified, typically by
including a heading ([h1](heading_elements) - [h6](heading_elements)
element) as a child of the `<section>` element, wherever possible. See
below for examples of where you might see a `<section>` without a
heading.

Examples
--------

### Simple usage example

#### Before

[html]

```html
<div>
  <h2>Heading</h2>
  <p>Bunch of awesome content</p>
</div>
```

##### Result

#### After

[html]

```html
<section>
  <h2>Heading</h2>
  <p>Bunch of awesome content</p>
</section>
```

##### Result

### Using a section without a heading

Circumstances where you might see `<section>` used without a heading are
typically found in web application/UI sections rather than in
traditional document structures. In a document, it doesn\'t really make
any sense to have a separate section of content without a heading to
describe its contents. Such headings are useful for all readers, but
particularly useful for users of assistive technologies like screen
readers, and they are also good for SEO.

Consider however a secondary navigation mechanism. If the global
navigation is already wrapped in a `<nav>` element, you could
conceivably wrap a previous/next menu in a `<section>`:

[html]

```html
<section>
  <a href="#">Previous article</a>
  <a href="#">Next article</a>
</section>
```

Or what about some kind of button bar for controlling your app? This
might not necessarily want a heading, but it is still a distinct section
of the document:

[html]

```html
<section>
  <button class="reply">Reply</button>
  <button class="reply-all">Reply to all</button>
  <button class="fwd">Forward</button>
  <button class="del">Delete</button>
</section>
```

#### Result

Depending on the content, including a heading could also be good for
SEO, so it is an option to consider.

Technical summary
-----------------

  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [Sectioning content](../content_categories#sectioning_content), [palpable content](../content_categories#palpable_content).
  Permitted content                             [Flow content](../content_categories#flow_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content). Note that a `<section>` element must not be a descendant of an [`<address>`](address) element.
  Implicit ARIA role                            `region` if the element has an [accessible name](https://developer.paciellogroup.com/blog/2017/04/what-is-an-accessible-name/), otherwise `generic`
  Permitted ARIA roles                          [`alert`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/alert_role), [`alertdialog`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/alertdialog_role), [`application`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/application_role), [`banner`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/banner_role), [`complementary`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/complementary_role), [`contentinfo`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/contentinfo_role), [`dialog`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/dialog_role), [`document`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/document_role), [`feed`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/feed_role), [`log`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/log_role), [`main`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/main_role), [`marquee`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/marquee_role), [`navigation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/navigation_role), [`none`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/none_role), [`note`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/note_role), [`presentation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role), [`search`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/search_role), [`status`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/status_role), [`tabpanel`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/tabpanel_role)
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-section-element]](https://html.spec.whatwg.org/multipage/sections.html#the-section-element)

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

`section`

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

- Other section-related elements: [`<body>`](body), [`<nav>`](nav),
    [`<article>`](article), [`<aside>`](aside), [h1](heading_elements),
    [h2](heading_elements), [h3](heading_elements),
    [h4](heading_elements), [h5](heading_elements),
    [h6](heading_elements), [`<hgroup>`](hgroup), [`<header>`](header),
    [`<footer>`](footer), [`<address>`](address)
- [Using HTML sections and outlines](heading_elements)
- [ARIA: Region
    role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/region_role)
- [Why You Should Choose HTML5 article Over
    section](https://www.smashingmagazine.com/2020/01/html5-article-section/),
    by Bruce Lawson

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section>>
