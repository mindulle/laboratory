\<ol\>: The Ordered List element
================================

The `<ol>` [HTML](../index) element represents an ordered list of items
--- typically rendered as a numbered list.

Try it
------

Attributes
----------

This element also accepts the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`reversed`](#reversed)

:   This Boolean attribute specifies that the list\'s items are in
    reverse order. Items will be numbered from high to low.

[`start`](#start)

:   An integer to start counting from for the list items. Always an
    Arabic numeral (1, 2, 3, etc.), even when the numbering `type` is
    letters or Roman numerals. For example, to start numbering elements
    from the letter \"d\" or the Roman numeral \"iv,\" use `start="4"`.

[`type`](#type)

:   Sets the numbering type:

    -   `a` for lowercase letters
    -   `A` for uppercase letters
    -   `i` for lowercase Roman numerals
    -   `I` for uppercase Roman numerals
    -   `1` for numbers (default)

    The specified type is used for the entire list unless a different
    [`type`](li#type) attribute is used on an enclosed [`<li>`](li)
    element.

     
    **Note:** Unless the type of the list number matters (like legal or
    technical documents where items are referenced by their
    number/letter), use the CSS
    [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)
    property instead.

Usage notes
-----------

Typically, ordered list items display with a preceding
[marker](https://developer.mozilla.org/en-US/docs/Web/CSS/::marker),
such as a number or letter.

The `<ol>` and [`<ul>`](ul) elements may nest as deeply as desired,
alternating between `<ol>` and `<ul>` however you like.

The `<ol>` and [`<ul>`](ul) elements both represent a list of items. The
difference is with the `<ol>` element, the order is meaningful. For
example:

- Steps in a recipe
- Turn-by-turn directions
- The list of ingredients in decreasing proportion on nutrition
    information labels

To determine which list to use, try changing the order of the list
items; if the meaning changes, use the `<ol>` element --- otherwise you
can use [`<ul>`](ul).

Examples
--------

### Simple example

[html]

```html
<ol>
  <li>Fee</li>
  <li>Fi</li>
  <li>Fo</li>
  <li>Fum</li>
</ol>
```

#### Result

### Using Roman Numeral type

[html]

```html
<ol type="i">
  <li>Introduction</li>
  <li>List of Grievances</li>
  <li>Conclusion</li>
</ol>
```

#### Result

### Using the start attribute

[html]

```html
<p>Finishing places of contestants not in the winners' circle:</p>

<ol start="4">
  <li>Speedwalk Stu</li>
  <li>Saunterin' Sam</li>
  <li>Slowpoke Rodriguez</li>
</ol>
```

#### Result

### Nesting lists

[html]

```html
<ol>
  <li>first item</li>
  <li>
    second item
    <!-- closing </li> tag is not here! -->
    <ol>
      <li>second item first subitem</li>
      <li>second item second subitem</li>
      <li>second item third subitem</li>
    </ol>
  </li>
  <!-- Here's the closing </li> tag -->
  <li>third item</li>
</ol>
```

#### Result

### Unordered list inside ordered list

[html]

```html
<ol>
  <li>first item</li>
  <li>
    second item
    <!-- closing </li> tag is not here! -->
    <ul>
      <li>second item first subitem</li>
      <li>second item second subitem</li>
      <li>second item third subitem</li>
    </ul>
  </li>
  <!-- Here's the closing </li> tag -->
  <li>third item</li>
</ol>
```

#### Result

Technical summary
-----------------

  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), and if the `<ol>` element\'s children include at least one [`<li>`](li) element, [palpable content](../content_categories#palpable_content).
  Permitted content                             Zero or more [`<li>`](li), [`<script>`](script) and [`<template>`](template) elements.
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content).
  Implicit ARIA role                            `list`
  Permitted ARIA roles                          [`directory`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/directory_role), [`group`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/group_role), [`listbox`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/listbox_role), [`menu`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/menu_role), [`menubar`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/menubar_role), [`none`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/none_role), [`presentation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role), [`radiogroup`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/radiogroup_role), [`tablist`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/tablist_role), [`toolbar`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/toolbar_role), [`tree`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/tree_role)
  DOM interface                                 [`HTMLOListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOListElement)
  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-ol-element]](https://html.spec.whatwg.org/multipage/grouping-content.html#the-ol-element)

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

`ol`

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

`reversed`

18

≤79

18

No

15

6

4.4

18

18

14

6

1.0

`start`

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

- Other list-related HTML Elements: [`<ul>`](ul), [`<li>`](li),
    [`<menu>`](menu)
- CSS properties that may be specially useful to style the `<ol>`
    element:
  - the
        [`list-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style)
        property, to choose the way the ordinal displays
  - [CSS
        counters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles/Using_CSS_counters),
        to handle complex nested lists
  - the
        [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height)
        property, to simulate the deprecated [`compact`](#compact)
        attribute
  - the
        [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)
        property, to control the list indentation

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol>>
