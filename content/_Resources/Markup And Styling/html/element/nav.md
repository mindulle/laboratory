\<nav\>: The Navigation Section element
=======================================

The `<nav>` [HTML](../index) element represents a section of a page
whose purpose is to provide navigation links, either within the current
document or to other documents. Common examples of navigation sections
are menus, tables of contents, and indexes.

Try it
------

  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [sectioning content](../content_categories#sectioning_content), palpable content.
  Permitted content                             [Flow content](../content_categories#flow_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content).
  Implicit ARIA role                            `navigation`
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

- It\'s not necessary for all links to be contained in a `<nav>`
    element. `<nav>` is intended only for a major block of navigation
    links; typically the [`<footer>`](footer) element often has a list
    of links that don\'t need to be in a [`<nav>`](nav) element.
- A document may have several [`<nav>`](nav) elements, for example,
    one for site navigation and one for intra-page navigation.
    [`aria-labelledby`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-labelledby)
    can be used in such case to promote accessibility, see
    [example](heading_elements#labeling_section_content).
- User agents, such as screen readers targeting disabled users, can
    use this element to determine whether to omit the initial rendering
    of navigation-only content.

Examples
--------

In this example, a `<nav>` block is used to contain an unordered list
([`<ul>`](ul)) of links. With appropriate CSS, this can be presented as
a sidebar, navigation bar, or drop-down menu.

[html]

```html
<nav class="menu">
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
```

The semantics of the `nav` element is that of providing links. However a
`nav` element doesn\'t have to contain a list, it can contain other
kinds of content as well. In this navigation block, links are provided
in prose:

[html]

```html
<nav>
  <h2>Navigation</h2>
  <p>
    You are on my home page. To the north lies <a href="/blog">my blog</a>, from
    whence the sounds of battle can be heard. To the east you can see a large
    mountain, upon which many <a href="/school">school papers</a> are littered.
    Far up this mountain you can spy a little figure who appears to be me,
    desperately scribbling a <a href="/school/thesis">thesis</a>.
  </p>
  <p>
    To the west are several exits. One fun-looking exit is labeled
    <a href="https://games.example.com/">"games"</a>. Another more
    boring-looking exit is labeled <a href="https://isp.example.net/">ISP™</a>.
  </p>
  <p>
    To the south lies a dark and dank <a href="/about">contacts page</a>.
    Cobwebs cover its disused entrance, and at one point you see a rat run
    quickly out of the page.
  </p>
</nav>
```

### Result

Specifications
--------------

  -------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-nav-element]](https://html.spec.whatwg.org/multipage/sections.html#the-nav-element)

  -------------------------------------------------------------------------------------------------

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

`nav`

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
    [`<article>`](article), [`<section>`](section), [`<aside>`](aside),
    [h1](heading_elements), [h2](heading_elements),
    [h3](heading_elements), [h4](heading_elements),
    [h5](heading_elements), [h6](heading_elements),
    [`<hgroup>`](hgroup), [`<header>`](header), [`<footer>`](footer),
    [`<address>`](address);
- [Sections and outlines of an HTML document](heading_elements).
- [ARIA: Navigation
    role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/navigation_role)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav>>
