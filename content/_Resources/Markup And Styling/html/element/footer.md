\<footer\>
==========

The `<footer>` [HTML](../index) element represents a footer for its
nearest ancestor [sectioning
content](../content_categories#sectioning_content) or [sectioning
root](heading_elements#sectioning_root) element. A `<footer>` typically
contains information about the author of the section, copyright data or
links to related documents.

Try it
------

  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), palpable content.
  Permitted content                             [Flow content](../content_categories#flow_content), but with no `<footer>` or [`<header>`](header) descendants.
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content). Note that a `<footer>` element must not be a descendant of an [`<address>`](address), [`<header>`](header) or another `<footer>` element.
  Implicit ARIA role                            [contentinfo](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/contentinfo_role), or [generic](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/generic_role) if a descendant of an [article](article), [aside](aside), [main](main), [nav](nav) or [section](section) element, or an element with `role=article`, [complementary](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/complementary_role), [main](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/main_role), [navigation](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/navigation_role) or [region](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/region_role)
  Permitted ARIA roles                          [`group`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/group_role), [`presentation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role) or [`none`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/none_role)
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

- Enclose information about the author in an [`<address>`](address)
    element that can be included into the `<footer>` element.
- When the nearest ancestor sectioning content or sectioning root
    element is the body element the footer applies to the whole page.
- The `<footer>` element is not sectioning content and therefore
    doesn\'t introduce a new section in the [outline](heading_elements).

Examples
--------

[html]

```html
<body>
  <h3>FIFA World Cup top goalscorers</h3>
  <ol>
    <li>Miroslav Klose, 16</li>
    <li>Ronaldo Nazário, 15</li>
    <li>Gerd Müller, 14</li>
  </ol>

  <footer>
    <small>
      Copyright © 2023 Football History Archives. All Rights Reserved.
    </small>
  </footer>
</body>
```

[css]

```css
footer {
  text-align: center;
  padding: 5px;
  background-color: #abbaba;
  color: #000;
}

```

Accessibility concerns
----------------------

Prior to the release of Safari 13, the `contentinfo` [landmark
role](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#signpostslandmarks)
was not properly exposed by
[VoiceOver](https://help.apple.com/voiceover/info/guide/). If needing to
support legacy Safari browsers, add `role="contentinfo"` to the `footer`
element to ensure the landmark will be properly exposed.

- Related: [WebKit Bugzilla: 146930 -- AX: HTML native elements
    (header, footer, main, aside, nav) should work the same as ARIA
    landmarks, sometimes they don\'t](https://webkit.org/b/146930)

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-footer-element]](https://html.spec.whatwg.org/multipage/sections.html#the-footer-element)

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

`footer`

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
    [`<section>`](section), [`<address>`](address);
- [Using HTML sections and outlines](heading_elements)
- [ARIA: Contentinfo
    role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/contentinfo_role)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer>
