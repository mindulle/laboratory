\<hgroup\>
==========

The `<hgroup>` [HTML](../index) element represents a heading and related
content. It groups a single [`<h1>–<h6>`](heading_elements) element with
one or more [`<p>`](p).

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

The `<hgroup>` element allows the grouping of a heading with any
secondary content, such as subheadings, an alternative title, or
tagline. Each of these types of content represented as a `<p>` element
within the `<hgroup>`.

The `<hgroup>` itself has no impact on the document outline of a web
page. Rather, the single allowed heading within the `<hgroup>`
contributes to the document outline.

Examples
--------

[html]

```html
<!doctype html>
<title>HTML Standard</title>
<body>
  <hgroup id="document-title">
    <h1>HTML: Living Standard</h1>
    <p>Last Updated 12 July 2022</p>
  </hgroup>
  <p>Some intro to the document.</p>
  <h2>Table of contents</h2>
  <ol id="toc">
    …
  </ol>
  <h2>First section</h2>
  <p>Some intro to the first section.</p>
</body>
```

### Result

Accessibility concerns
----------------------

The `<hgroup>` presently has no strong accessibility semantics. The
content of the element (a heading and optional paragraphs) is what is
exposed by browser accessibility APIs.

Technical summary
-----------------

  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), heading content, palpable content.
  Permitted content                             Zero or more [`<p>`](p) elements, followed by one [h1](heading_elements), [h2](heading_elements), [h3](heading_elements), [h4](heading_elements), [h5](heading_elements), or [h6](heading_elements) element, followed by zero or more [`<p>`](p) elements.
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content).
  Implicit ARIA role                            `generic`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-hgroup-element]](https://html.spec.whatwg.org/multipage/sections.html#the-hgroup-element)

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

`hgroup`

5

12

4

9

11.1

5

2.2

18

4

11.1

4.2

1.0

See also
--------

- Others section-related elements: [`<body>`](body),
    [`<article>`](article), [`<section>`](section), [`<aside>`](aside),
    [h1](heading_elements), [h2](heading_elements),
    [h3](heading_elements), [h4](heading_elements),
    [h5](heading_elements), [h6](heading_elements), [`<nav>`](nav),
    [`<header>`](header), [`<footer>`](footer), [`<address>`](address);
- [Sections and outlines of an HTML document](heading_elements).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/hgroup>>
