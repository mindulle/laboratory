\<summary\>: The Disclosure Summary element
===========================================

The `<summary>` [HTML](../index) element specifies a summary, caption,
or legend for a [`<details>`](details) element\'s disclosure box.
Clicking the `<summary>` element toggles the state of the parent
`<details>` element open and closed.

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

The `<summary>` element\'s contents can be any heading content, plain
text, or HTML that can be used within a paragraph.

A `<summary>` element may *only* be used as the first child of a
`<details>` element. When the user clicks on the summary, the parent
`<details>` element is toggled open or closed, and then a
[`toggle`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDetailsElement/toggle_event)
event is sent to the `<details>` element, which can be used to let you
know when this state change occurs.

### Default label text

If a `<details>` element\'s first child is not a `<summary>` element,
the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
will use a default string (typically \"Details\") as the label for the
disclosure box.

### Default style

Per the HTML specification, the default style for `<summary>` elements
includes `display: list-item`. This makes it possible to change or
remove the icon displayed as the disclosure widget next to the label
from the default, which is typically a triangle.

You can also change the style to `display: block` to remove the
disclosure triangle.

See the [Browser compatibility](#browser_compatibility) section for
details, as not all browsers support full functionality of this element
yet.

For Webkit-based browsers, such as Safari, it is possible to control the
icon display through the non-standard CSS pseudo-element
`::-webkit-details-marker`. To remove the disclosure triangle, use
`summary::-webkit-details-marker { display: none }`.

Examples
--------

Below are some examples showing `<summary>` in use. You can find more
examples in the documentation for the [`<details>`](details) element.

### Basic example

A simple example showing the use of `<summary>` in a
[`<details>`](details) element:

[html]

```html
<details open>
  <summary>Overview</summary>
  <ol>
    <li>Cash on hand: $500.00</li>
    <li>Current invoice: $75.30</li>
    <li>Due date: 5/6/19</li>
  </ol>
</details>
```

#### Result

### Summaries as headings

You can use heading elements in `<summary>`, like this:

[html]

```html
<details open>
  <summary><h4>Overview</h4></summary>
  <ol>
    <li>Cash on hand: $500.00</li>
    <li>Current invoice: $75.30</li>
    <li>Due date: 5/6/19</li>
  </ol>
</details>
```

#### Result

This currently has some spacing issues that could be addressed using
CSS.

**Warning:** Because the `<summary>` element has a default role of
[button](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/button_role)
(which strips all roles from child elements), this example will not work
for users of assistive technologies such as screen readers. The `<h4>`
will have its role removed and thus will not be treated as a heading for
these users.

### HTML in summaries

This example adds some semantics to the `<summary>` element to indicate
the label as important:

[html]

```html
<details open>
  <summary><strong>Overview</strong></summary>
  <ol>
    <li>Cash on hand: $500.00</li>
    <li>Current invoice: $75.30</li>
    <li>Due date: 5/6/19</li>
  </ol>
</details>
```

#### Result

Technical summary
-----------------

  ---------------------- ---------------------------------------------------------------------------------------------------------------------------------------
  Permitted content      [Phrasing content](../content_categories#phrasing_content) or one element of [Heading content](../content_categories#heading_content)
  Tag omission           None; both the start tag and the end tag are mandatory.
  Permitted parents      The [`<details>`](details) element.
  Implicit ARIA role     [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles   No `role` permitted
  DOM interface          [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  ---------------------- ---------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-summary-element]](https://html.spec.whatwg.org/multipage/interactive-elements.html#the-summary-element)

  ---------------------------------------------------------------------------------------------------------------------

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

`summary`

12

79

49

No

15

6

4

18

49

14

6

1.0

`display_list_item`

89

89

49

No

75

No

89

89

49

63

No

15.0

See also
--------

- [`<details>`](details)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary>>
