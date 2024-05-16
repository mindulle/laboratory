\<main\>
========

The `<main>` [HTML](../index) element represents the dominant content of
the [`<body>`](body) of a document. The main content area consists of
content that is directly related to or expands upon the central topic of
a document, or the central functionality of an application.

Try it
------

A document mustn\'t have more than one `<main>` element that doesn\'t
have the [`hidden`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#hidden) attribute specified.

  --------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), palpable content.
  Permitted content                             [Flow content](../content_categories#flow_content).
  Tag omission                                  None; both the starting and ending tags are mandatory.
  Permitted parents                             Where [flow content](../content_categories#flow_content) is expected, but only if it is a [hierarchically correct `main` element](https://html.spec.whatwg.org/multipage/grouping-content.html#hierarchically-correct-main-element).
  Implicit ARIA role                            `main`
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

The content of a `<main>` element should be unique to the document.
Content that is repeated across a set of documents or document sections
such as sidebars, navigation links, copyright information, site logos,
and search forms shouldn\'t be included unless the search form is the
main function of the page.

`<main>` doesn\'t contribute to the document\'s outline; that is, unlike
elements such as [`<body>`](body), headings such as
[h2](heading_elements), and such, `<main>` doesn\'t affect the
[DOM\'s](https://developer.mozilla.org/en-US/docs/Glossary/DOM) concept
of the structure of the page. It\'s strictly informative.

Examples
--------

[html]

```html
<!-- other content -->

<main>
  <h1>Apples</h1>
  <p>The apple is the pomaceous fruit of the apple tree.</p>

  <article>
    <h2>Red Delicious</h2>
    <p>
      These bright red apples are the most common found in many supermarkets.
    </p>
    <p>…</p>
    <p>…</p>
  </article>

  <article>
    <h2>Granny Smith</h2>
    <p>These juicy, green apples make a great filling for apple pies.</p>
    <p>…</p>
    <p>…</p>
  </article>
</main>

<!-- other content -->
```

### Result

Accessibility concerns
----------------------

### Landmark

The `<main>` element behaves like a [`main`
landmark](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/main_role)
role.
[Landmarks](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques#landmark_roles)
can be used by assistive technology to quickly identify and navigate to
large sections of the document. Prefer using the `<main>` element over
declaring `role="main"`, unless there are [legacy browser support
concerns](#browser_compatibility).

### Skip navigation

Skip navigation, also known as \"skipnav\", is a technique that allows
an assistive technology user to quickly bypass large sections of
repeated content (main navigation, info banners, etc.). This lets the
user access the main content of the page faster.

Adding an [`id`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#id) attribute to the `<main>`
element lets it be a target of a skip navigation link.

[html]

```html
<body>
  <a href="#main-content">Skip to main content</a>

  <!-- navigation and header content -->

  <main id="main-content">
    <!-- main page content -->
  </main>
</body>
```

- [WebAIM: \"Skip Navigation\"
    Links](https://webaim.org/techniques/skipnav/)

### Reader mode

Browser reader mode functionality looks for the presence of the `<main>`
element, as well as [heading](heading_elements) and [](_Resources/Markup%20And%20Styling/html/element/index.md#content_sectioning) when converting content into a
specialized reader view.

- [Building websites for Safari Reader Mode and other reading
    apps.](https://medium.com/@mandy.michael/building-websites-for-safari-reader-mode-and-other-reading-apps-1562913c86c9)

Specifications
--------------

  -----------------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-main-element]](https://html.spec.whatwg.org/multipage/grouping-content.html#the-main-element)

  -----------------------------------------------------------------------------------------------------------

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

`main`

26

12

21

No

16

7

4.4

26

21

14

7

1.5

See also
--------

- Basic structural elements: [`<html>`](html), [`<head>`](head),
    [`<body>`](body)
- Section-related elements: [`<article>`](article),
    [`<aside>`](aside), [`<footer>`](footer), [`<header>`](header), or
    [`<nav>`](nav)
- [ARIA: Main
    role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/main_role)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/main>>
