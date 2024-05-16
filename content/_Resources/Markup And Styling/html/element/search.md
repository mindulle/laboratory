\<search\>: The generic search element
======================================

The `<search>` [HTML](../index) element is a container representing the
parts of the document or application with form controls or other content
related to performing a search or filtering operation. The `<search>`
element semantically identifies the purpose of the element\'s contents
as having search or filtering capabilities. The search or filtering
functionality can be for the website or application, the current web
page or document, or the entire Internet or subsection thereof.

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

The `<search>` element is not for presenting search results. Rather,
search or filtered results should be presented as part of the main
content of that web page. That said, suggestions and links that are part
of \"quick search\" functionality within the search or filtering
functionality are appropriately nested within the contents of the
`<search>` element as they are search features.

Accessibility
-------------

The `<search>` element defines a
[`search`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/search_role)
landmark. This removes the need for adding `role=search` to a
[`<form>`](form) element.

Examples
--------

### Header search form

This example demonstrates the use of `<search>` as the container for a
search within a website header to perform a simple site-wide search. The
`<search>` is a semantic container for the [`<form>`](form) that submits
the user-entered search query to a server.

#### HTML

[html]

```html
<header>
  <h1>Movie website</h1>
  <search>
    <form action="./search/">
      <label for="movie">Find a Movie</label>
      <input type="search" id="movie" name="q" />
      <button type="submit">Search</button>
    </form>
  </search>
</header>
```

#### Result

### Web app search

This example demonstrates potential DOM content when dynamically
including JavaScript search functionality in a web application. When
search functionality is implemented entirely with JavaScript, if no form
is submitted, neither a [`<form>`](form) element nor a submit
[`<button>`](button) is required. For semantics, the `<search>` element
is included to contain the search and filtering capabilities.

#### HTML

[html]

```html
<search>
  <label>
    Find and filter your query
    <input type="search" id="query" />
  </label>
  <label>
    <input type="checkbox" id="exact-only" />
    Exact matches only
  </label>

  <section>
    <h3>Results:</h3>
    <ul id="results">
      <!-- search result content -->
    </ul>
    <output id="no-results">
      <!-- no results content -->
    </output>
  </section>
</search>
```

#### Result

**Note:** Remember that some users don\'t have JavaScript, and none of
your users have JavaScript running until the JavaScript is successfully
downloaded, parsed, and executed, ensure your users can access the
content of your site with JavaScript disabled.

### Multiple searches

This example demonstrates a page with two search features. The first is
a global site search located on the header. The second is a search and
filter based on the page context, in our example a car search.

#### HTML

[html]

```html
<body>
  <header>
    <h1>Car rental agency</h1>
    <search title="Website">...</search>
  </header>
  <main>
    <h2>Cars available for rent</h2>
    <search title="Cars">
      <h3>Filter results</h3>
      ...
    </search>
    <article>
      <!-- search result content -->
    </article>
  </main>
</body>
```

#### Result

Technical summary
-----------------

  --------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [palpable content](../content_categories#palpable_content).
  Permitted content                             [Flow content](../content_categories#flow_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Implicit ARIA role                            `search`
  Permitted ARIA roles                          [`form`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/form_role), [`group`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/group_role), [`none`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/none_role), [`presentation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role), [`region`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/region_role), [`search`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/search_role)
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-search-element]](https://html.spec.whatwg.org/multipage/grouping-content.html#the-search-element)

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

`search`

118

118

118

No

104

17

118

118

118

No

17

No

See also
--------

- Other search-related elements: [`<header>`](header),
    [`<footer>`](footer), [`<aside>`](aside), [`<nav>`](nav),
    [`<form>`](form)
- [ARIA: Search
    role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/search_role)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/search>>
