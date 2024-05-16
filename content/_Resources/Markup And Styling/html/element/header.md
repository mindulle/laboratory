\<header\>
==========

The `<header>` [HTML](../index) element represents introductory content,
typically a group of introductory or navigational aids. It may contain
some heading elements but also a logo, a search form, an author name,
and other elements.

Try it
------

Usage notes
-----------

The `<header>` element has an identical meaning to the site-wide
[`banner`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/banner_role)
landmark role, unless nested within sectioning content. Then, the
`<header>` element is not a landmark.

The `<header>` element can define a global site header, described as a
`banner` in the accessibility tree. It usually includes a logo, company
name, search feature, and possibly the global navigation or a slogan. It
is generally located at the top of the page.

Otherwise, it is a `section` in the accessibility tree, and usually
contains the surrounding section\'s heading (an `h1` -- `h6` element)
and optional subheading, but this is **not** required.

### Historical Usage

The `<header>` element originally existed at the very beginning of HTML
for headings. It is seen in [the very first
website](http://info.cern.ch/). At some point, headings became [`<h1>`
through `<h6>`](heading_elements), allowing `<header>` to be free to
fill a different role.

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Examples
--------

### Page Header

[html]

```html
<header>
  <h1>Main Page Title</h1>
  <img src="mdn-logo-sm.png" alt="MDN logo" />
</header>
```

#### Result

### Article Header

[html]

```html
<article>
  <header>
    <h2>The Planet Earth</h2>
    <p>
      Posted on Wednesday, <time datetime="2017-10-04">4 October 2017</time> by
      Jane Smith
    </p>
  </header>
  <p>
    We live on a planet that's blue and green, with so many things still unseen.
  </p>
  <p><a href="https://example.com/the-planet-earth/">Continue reading…</a></p>
</article>
```

#### Result

Accessibility
-------------

The `<header>` element defines a
[`banner`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/banner_role)
landmark when its context is the [`<body>`](body) element. The HTML
header element is not considered a banner landmark when it is descendant
of an [`<article>`](article), [`<aside>`](aside), [`<main>`](main),
[`<nav>`](nav), or [`<section>`](section) element.

Technical summary
-----------------

  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [palpable content](../content_categories#palpable_content).
  Permitted content                             [Flow content](../content_categories#flow_content), but with no `<header>` or [`<footer>`](footer) descendant.
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content). Note that a `<header>` element must not be a descendant of an [`<address>`](address), [`<footer>`](footer) or another [`<header>`](header) element.
  Implicit ARIA role                            [banner](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/banner_role), or [generic](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/generic_role) if a descendant of an `article`, `aside`, `main`, `nav` or `section` element, or an element with `role=article`, `complementary`, `main`, `navigation` or `region`
  Permitted ARIA roles                          [`group`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/group_role), [`presentation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role) or [`none`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/none_role)
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-header-element]](https://html.spec.whatwg.org/multipage/sections.html#the-header-element)

  -------------------------------------------------------------------------------------------------------

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

`header`

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
    [h6](heading_elements), [`<footer>`](footer),
    [`<section>`](section), [`<address>`](address).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header>>
