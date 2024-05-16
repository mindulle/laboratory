\<div\>: The Content Division element
=====================================

The `<div>` [HTML](../index) element is the generic container for flow
content. It has no effect on the content or layout until styled in some
way using [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS)
(e.g. styling is directly applied to it, or some kind of layout model
like
[Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout)
is applied to its parent element).

Try it
------

As a \"pure\" container, the `<div>` element does not inherently
represent anything. Instead, it\'s used to group content so it can be
easily styled using the [`class`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#class) or
[`id`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#id) attributes, marking a section of a
document as being written in a different language (using the
[`lang`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#lang) attribute), and so on.

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

**Note:** The `align` attribute is obsolete; do not use it anymore.
Instead, you should use CSS properties or techniques such as [CSS
Grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout)
or [CSS
Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)
to align and position `<div>` elements on the page.

Usage notes
-----------

- The `<div>` element should be used only when no other semantic
    element (such as [`<article>`](article) or [`<nav>`](nav)) is
    appropriate.

Accessibility concerns
----------------------

The `<div>` element has [an implicit role of
`generic`](https://www.w3.org/TR/wai-aria-1.2/#generic), and not none.
This may affect certain ARIA combination declarations that expect a
direct descendant element with a certain role to function properly.

Examples
--------

### A simple example

[html]

```html
<div>
  <p>
    Any kind of content here. Such as &lt;p&gt;, &lt;table&gt;. You name it!
  </p>
</div>
```

#### Result

### A styled example

This example creates a shadowed box by applying a style to the `<div>`
using CSS. Note the use of the [`class`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#class)
attribute on the `<div>` to apply the style named `"shadowbox"` to the
element.

#### HTML

[html]

```html
<div class="shadowbox">
  <p>Here's a very interesting note displayed in a lovely shadowed box.</p>
</div>
```

#### CSS

[css]

```css
.shadowbox {
  width: 15em;
  border: 1px solid #333;
  box-shadow: 8px 8px 5px #444;
  padding: 8px 12px;
  background-image: linear-gradient(180deg, #fff, #ddd 40%, #ccc);
}

```

#### Result

Technical summary
-----------------

  ------------------------------------ -------------------------------------------------------------------------------------
  [Content                             [Flow content](../content_categories#flow_content), [palpable
  categories](../content_categories)   content](../content_categories#palpable_content).

  Permitted content                    [Flow content](../content_categories#flow_content).\
                                       Or (in [WHATWG](https://developer.mozilla.org/en-US/docs/Glossary/WHATWG) HTML): If
                                       the parent is a [`<dl>`](dl) element: one or more [`<dt>`](dt) elements followed by
                                       one or more [`<dd>`](dd) elements, optionally intermixed with [`<script>`](script)
                                       and [`<template>`](template) elements.

  Tag omission                         None, both the starting and ending tag are mandatory.

  Permitted parents                    Any element that accepts [flow content](../content_categories#flow_content).\
                                       Or (in [WHATWG](https://developer.mozilla.org/en-US/docs/Glossary/WHATWG) HTML):
                                       [`<dl>`](dl) element.

  Implicit ARIA role                   `generic`

  Permitted ARIA roles                 Any

  DOM interface                        [`HTMLDivElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDivElement)
  ------------------------------------ -------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-div-element]](https://html.spec.whatwg.org/multipage/grouping-content.html#the-div-element)

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

`div`

1

12

1

Yes

15

1

4.4

18

4

14

1

1.0

`align`

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

See also
--------

- Semantic sectioning elements: [`<section>`](section),
    [`<article>`](article), [`<nav>`](nav), [`<header>`](header),
    [`<footer>`](footer)
- [`<span>`](span) element for styling of phrasing content

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div>
