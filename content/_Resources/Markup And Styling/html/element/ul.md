\<ul\>: The Unordered List element
==================================

The `<ul>` [HTML](../index) element represents an unordered list of
items, typically rendered as a bulleted list.

Try it
------

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`compact`](#compact) [Deprecated]

:   This Boolean attribute hints that the list should be rendered in a
    compact style. The interpretation of this attribute depends on the
    [user
    agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent),
    and it doesn\'t work in all browsers.

    **Warning:** Do not use this attribute, as it has been deprecated:
    use [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) instead.
    To give a similar effect as the `compact` attribute, the CSS
    property
    [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height)
    can be used with a value of `80%`.

[`type`](#type) [Deprecated]

:   This attribute sets the bullet style for the list. The values
    defined under HTML3.2 and the transitional version of HTML 4.0/4.01
    are:

    -   `circle`
    -   `disc`
    -   `square`

    A fourth bullet type has been defined in the WebTV interface, but
    not all browsers support it: `triangle`.

    If not present and if no
    [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
    [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)
    property applies to the element, the user agent selects a bullet
    type depending on the nesting level of the list.

     
    **Warning:** Do not use this attribute, as it has been deprecated;
    use the [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
    [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)
    property instead.

Usage notes
-----------

- The `<ul>` element is for grouping a collection of items that do not
    have a numerical ordering, and their order in the list is
    meaningless. Typically, unordered-list items are displayed with a
    bullet, which can be of several forms, like a dot, a circle, or a
    square. The bullet style is not defined in the HTML description of
    the page, but in its associated CSS, using the
    [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)
    property.
- The `<ul>` and [`<ol>`](ol) elements may be nested as deeply as
    desired. Moreover, the nested lists may alternate between `<ol>` and
    `<ul>` without restriction.
- The [`<ol>`](ol) and `<ul>` elements both represent a list of items.
    They differ in that, with the [`<ol>`](ol) element, the order is
    meaningful. To determine which one to use, try changing the order of
    the list items; if the meaning is changed, the [`<ol>`](ol) element
    should be used, otherwise you can use `<ul>`.

Examples
--------

### Simple example

[html]

```html
<ul>
  <li>first item</li>
  <li>second item</li>
  <li>third item</li>
</ul>
```

#### Result

### Nesting a list

[html]

```html
<ul>
  <li>first item</li>
  <li>
    second item
    <!-- Look, the closing </li> tag is not placed here! -->
    <ul>
      <li>second item first subitem</li>
      <li>
        second item second subitem
        <!-- Same for the second nested unordered list! -->
        <ul>
          <li>second item second subitem first sub-subitem</li>
          <li>second item second subitem second sub-subitem</li>
          <li>second item second subitem third sub-subitem</li>
        </ul>
      </li>
      <!-- Closing </li> tag for the li that
                  contains the third unordered list -->
      <li>second item third subitem</li>
    </ul>
    <!-- Here is the closing </li> tag -->
  </li>
  <li>third item</li>
</ul>
```

#### Result

### Ordered list inside unordered list

[html]

```html
<ul>
  <li>first item</li>
  <li>
    second item
    <!-- Look, the closing </li> tag is not placed here! -->
    <ol>
      <li>second item first subitem</li>
      <li>second item second subitem</li>
      <li>second item third subitem</li>
    </ol>
    <!-- Here is the closing </li> tag -->
  </li>
  <li>third item</li>
</ul>
```

#### Result

Technical summary
-----------------

  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), and if the `<ul>` element\'s children include at least one [`<li>`](li) element, [palpable content](../content_categories#palpable_content).
  Permitted content                             Zero or more [`<li>`](li), [`<script>`](script) and [`<template>`](template) elements.
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content).
  Implicit ARIA role                            `list`
  Permitted ARIA roles                          [`directory`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/directory_role), [`group`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/group_role), [`listbox`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/listbox_role), [`menu`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/menu_role), [`menubar`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/menubar_role), [`none`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/none_role), [`presentation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role), [`radiogroup`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/radiogroup_role), [`tablist`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/tablist_role), [`toolbar`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/toolbar_role), [`tree`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/tree_role)
  DOM Interface                                 [`HTMLUListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLUListElement)
  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-ul-element]](https://html.spec.whatwg.org/multipage/grouping-content.html#the-ul-element)

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

`ul`

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

`compact`

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

`type`

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

- Other list-related HTML Elements: [`<ol>`](ol), [`<li>`](li),
    [`<menu>`](menu)
- CSS properties that may be specially useful to style the `<ul>`
    element:
  - the
        [`list-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style)
        property, to choose the way the ordinal displays.
  - [CSS
        counters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles/Using_CSS_counters),
        to handle complex nested lists.
  - the
        [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height)
        property, to simulate the deprecated [`compact`](#compact)
        attribute.
  - the
        [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)
        property, to control the list indentation.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul>>
