\<h1\>--\<h6\>: The HTML Section Heading elements
=================================================

The `<h1>` to `<h6>` [HTML](../index) elements represent six levels of
section headings. `<h1>` is the highest section level and `<h6>` is the
lowest. By default, all heading elements create a
[block-level](https://developer.mozilla.org/en-US/docs/Glossary/Block-level_content)
box in the layout, starting on a new line and taking up the full width
available in their containing block.

Try it
------

  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), heading content, palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content).
  Implicit ARIA role                            [heading](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/heading_role)
  Permitted ARIA roles                          [`tab`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/tab_role), [`presentation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role) or [`none`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/none_role)
  DOM interface                                 [`HTMLHeadingElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadingElement)
  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Attributes
----------

These elements only include the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

- Heading information can be used by user agents to construct a table
    of contents for a document automatically.
- Do not use heading elements to resize text. Instead, use the
    [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS)
    [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size)
    property.
- Do not skip heading levels: always start from `<h1>`, followed by
    `<h2>` and so on.

### Avoid using multiple `<h1>` elements on one page

While using multiple `<h1>` elements on one page is allowed by the HTML
standard (as long as they are not [nested](#nesting)), this is not
considered a best practice. A page should generally have a single `<h1>`
element that describes the content of the page (similar to the
document\'s [`<title> element`](title)).

**Note:** Nesting multiple `<h1>` elements in nested [](_Resources/Markup%20And%20Styling/html/element/index.md#content_sectioning) was allowed in older versions
of the HTML standard. However, this was never considered a best practice
and is now non-conforming. Read more in [There Is No Document Outline
Algorithm](https://adrianroselli.com/2016/08/there-is-no-document-outline-algorithm.html).

Prefer using only one `<h1>` per page and [nest headings](#nesting)
without skipping levels.

Examples
--------

### All headings

The following code shows all the heading levels, in use.

[html]

```html
<h1>Heading level 1</h1>
<h2>Heading level 2</h2>
<h3>Heading level 3</h3>
<h4>Heading level 4</h4>
<h5>Heading level 5</h5>
<h6>Heading level 6</h6>
```

### Example page

The following code shows a few headings with some content under them.

[html]

```html
<h1>Heading elements</h1>
<h2>Summary</h2>
<p>Some text here…</p>

<h2>Examples</h2>
<h3>Example 1</h3>
<p>Some text here…</p>

<h3>Example 2</h3>
<p>Some text here…</p>

<h2>See also</h2>
<p>Some text here…</p>
```

Accessibility concerns
----------------------

### Navigation

A common navigation technique for users of screen reading software is to
quickly jump from heading to heading in order to determine the content
of the page. Because of this, it is important to not skip one or more
heading levels. Doing so may create confusion, as the person navigating
this way may be left wondering where the missing heading is.

**Don\'t do this:**

[html]

```html
<h1>Heading level 1</h1>
<h3>Heading level 3</h3>
<h4>Heading level 4</h4>
```

**Prefer this:**

[html]

```html
<h1>Heading level 1</h1>
<h2>Heading level 2</h2>
<h3>Heading level 3</h3>
```

#### Nesting

Headings may be nested as subsections to reflect the organization of the
content of the page. Most screen readers can also generate an ordered
list of all the headings on a page, which can help a person quickly
determine the hierarchy of the content:

1. `h1` Beetles
    1. `h2` Etymology
    2. `h2` Distribution and Diversity
    3. `h2` Evolution
        1. `h3` Late Paleozoic
        2. `h3` Jurassic
        3. `h3` Cretaceous
        4. `h3` Cenozoic
    4. `h2` External Morphology
        1. `h3` Head
            1. `h4` Mouthparts
        2. `h3` Thorax
            1. `h4` Prothorax
            2. `h4` Pterothorax
        3. `h3` Legs
        4. `h3` Wings
        5. `h3` Abdomen

When headings are nested, heading levels may be \"skipped\" when closing
a subsection.

- [Headings • Page Structure • WAI Web Accessibility
    Tutorials](https://www.w3.org/WAI/tutorials/page-structure/headings/)
- [MDN Understanding WCAG, Guideline 1.3
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.3_%E2%80%94_create_content_that_can_be_presented_in_different_ways)
- [Understanding Success Criterion 1.3.1 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)
- [MDN Understanding WCAG, Guideline 2.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#guideline_2.4_%E2%80%94_navigable_provide_ways_to_help_users_navigate_find_content_and_determine_where_they_are)
- [Understanding Success Criterion 2.4.1 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-skip.html)
- [Understanding Success Criterion 2.4.6 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-descriptive.html)
- [Understanding Success Criterion 2.4.10 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-headings.html)

### Labeling section content

Another common navigation technique for users of screen reading software
is to generate a list of [](_Resources/Markup%20And%20Styling/html/element/index.md#content_sectioning) and use it to determine the
page\'s layout.

Sectioning content can be labeled using a combination of the
[`aria-labelledby`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-labelledby)
and [`id`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#id) attributes, with the label concisely
describing the purpose of the section. This technique is useful for
situations where there is more than one sectioning element on the same
page.

#### Sectioning content examples

[html]

```html
<header>
  <nav aria-labelledby="primary-navigation">
    <h2 id="primary-navigation">Primary navigation</h2>
    <!-- navigation items -->
  </nav>
</header>

<!-- page content -->

<footer>
  <nav aria-labelledby="footer-navigation">
    <h2 id="footer-navigation">Footer navigation</h2>
    <!-- navigation items -->
  </nav>
</footer>
```

In this example, screen reading technology would announce that there are
two [`<nav>`](nav) sections, one called \"Primary navigation\" and one
called \"Footer navigation\". If labels were not provided, the person
using screen reading software may have to investigate each `nav`
element\'s contents to determine their purpose.

- [Using the aria-labelledby
    attribute](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-labelledby)
- [Labeling Regions • Page Structure • W3C WAI Web Accessibility
    Tutorials](https://www.w3.org/WAI/tutorials/page-structure/labels/#using-aria-labelledby)

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-h1,-h2,-h3,-h4,-h5,-and-h6-elements]](https://html.spec.whatwg.org/multipage/sections.html#the-h1,-h2,-h3,-h4,-h5,-and-h6-elements)

  -------------------------------------------------------------------------------------------------------------------------------------------------

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

`Heading_Elements`

1

12

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

See also
--------

- [`<p>`](p)
- [`<div>`](div)
- [`<section>`](section)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements>>
