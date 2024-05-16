\<article\>: The Article Contents element
=========================================

The `<article>` [HTML](../index) element represents a self-contained
composition in a document, page, application, or site, which is intended
to be independently distributable or reusable (e.g., in syndication).
Examples include: a forum post, a magazine or newspaper article, or a
blog entry, a product card, a user-submitted comment, an interactive
widget or gadget, or any other independent item of content.

Try it
------

A given document can have multiple articles in it; for example, on a
blog that shows the text of each article one after another as the reader
scrolls, each post would be contained in an `<article>` element,
possibly with one or more `<section>`s within.

  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [sectioning content](../content_categories#sectioning_content), [palpable content](../content_categories#palpable_content)
  Permitted content                             [Flow content](../content_categories#flow_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content). Note that an `<article>` element must not be a descendant of an [`<address>`](address) element.
  Implicit ARIA role                            `article`
  Permitted ARIA roles                          [`application`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/application_role), [`document`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/document_role), [`feed`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/feed_role), [`main`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/main_role), [`none`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/none_role), [`presentation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role), [`region`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/region_role)
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

- Each `<article>` should be identified, typically by including a
    heading ([`<h1>` - `<h6>`](heading_elements) element) as a child of
    the `<article>` element.
- When an `<article>` element is nested, the inner element represents
    an article related to the outer element. For example, the comments
    of a blog post can be `<article>` elements nested in the `<article>`
    representing the blog post.
- Author information of an `<article>` element can be provided through
    the [`<address>`](address) element, but it doesn\'t apply to nested
    `<article>` elements.
- The publication date and time of an `<article>` element can be
    described using the [`datetime`](time#datetime) attribute of a
    [`<time>`](time) element.

Examples
--------

[html]

```html
<article class="film_review">
  <h2>Jurassic Park</h2>
  <section class="main_review">
    <h3>Review</h3>
    <p>Dinos were great!</p>
  </section>
  <section class="user_reviews">
    <h3>User reviews</h3>
    <article class="user_review">
      <h4>Too scary!</h4>
      <p>Way too scary for me.</p>
      <footer>
        <p>
          Posted on
          <time datetime="2015-05-16 19:00">May 16</time>
          by Lisa.
        </p>
      </footer>
    </article>
    <article class="user_review">
      <h4>Love the dinos!</h4>
      <p>I agree, dinos are my favorite.</p>
      <footer>
        <p>
          Posted on
          <time datetime="2015-05-17 19:00">May 17</time>
          by Tom.
        </p>
      </footer>
    </article>
  </section>
  <footer>
    <p>
      Posted on
      <time datetime="2015-05-15 19:00">May 15</time>
      by Staff.
    </p>
  </footer>
</article>
```

Result
------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-article-element]](https://html.spec.whatwg.org/multipage/sections.html#the-article-element)

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

`article`

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
    [`<section>`](section), [`<aside>`](aside), [h1](heading_elements),
    [h2](heading_elements), [h3](heading_elements),
    [h4](heading_elements), [h5](heading_elements),
    [h6](heading_elements), [`<hgroup>`](hgroup), [`<header>`](header),
    [`<footer>`](footer), [`<address>`](address)
- [Using HTML sections and outlines](heading_elements)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article>>
