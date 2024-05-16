\<li\>: The List Item element
=============================

The `<li>` [HTML](../index) element is used to represent an item in a
list. It must be contained in a parent element: an ordered list
([`<ol>`](ol)), an unordered list ([`<ul>`](ul)), or a menu
([`<menu>`](menu)). In menus and unordered lists, list items are usually
displayed using bullet points. In ordered lists, they are usually
displayed with an ascending counter on the left, such as a number or
letter.

Try it
------

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`value`](#value)

:   This integer attribute indicates the current ordinal value of the
    list item as defined by the [`<ol>`](ol) element. The only allowed
    value for this attribute is a number, even if the list is displayed
    with Roman numerals or letters. List items that follow this one
    continue numbering from the value set. The **value** attribute has
    no meaning for unordered lists ([`<ul>`](ul)) or for menus
    ([`<menu>`](menu)).

[`type`](#type) [Deprecated]

:   This character attribute indicates the numbering type:

    -   `a`: lowercase letters
    -   `A`: uppercase letters
    -   `i`: lowercase Roman numerals
    -   `I`: uppercase Roman numerals
    -   `1`: numbers

    This type overrides the one used by its parent [`<ol>`](ol) element,
    if any.

     
    **Note:** This attribute has been deprecated; use the CSS
    [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)
    property instead.

Examples
--------

For more detailed examples, see the [`<ol>`](ol) and [`<ul>`](ul) pages.

### Ordered list

[html]

```html
<ol>
  <li>first item</li>
  <li>second item</li>
  <li>third item</li>
</ol>
```

#### Result

### Ordered list with a custom value

[html]

```html
<ol type="I">
  <li value="3">third item</li>
  <li>fourth item</li>
  <li>fifth item</li>
</ol>
```

#### Result

### Unordered list

[html]

```html
<ul>
  <li>first item</li>
  <li>second item</li>
  <li>third item</li>
</ul>
```

#### Result

Technical summary
-----------------

  --------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   None.
  Permitted content                             [Flow content](../content_categories#flow_content).
  Tag omission                                  The end tag can be omitted if the list item is immediately followed by another [`<li>`](li) element, or if there is no more content in its parent element.
  Permitted parents                             An [`<ul>`](ul), [`<ol>`](ol), or [`<menu>`](menu) element. Though not a conforming usage, the obsolete [`<dir>`](dir) can also be a parent.
  Implicit ARIA role                            `listitem` when child of an `ol`, `ul` or `menu`
  Permitted ARIA roles                          [`menuitem`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/menuitem_role), [`menuitemcheckbox`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/menuitemcheckbox_role), [`menuitemradio`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/menuitemradio_role), [`option`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/option_role), [`none`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/none_role), [`presentation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role), [`radio`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/radio_role), [`separator`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/separator_role), [`tab`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/tab_role), [`treeitem`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/treeitem_role)
  DOM interface                                 [`HTMLLIElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLIElement)
  --------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-li-element]](https://html.spec.whatwg.org/multipage/grouping-content.html#the-li-element)

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

`li`

1

12

1

5.5

≤12.1

3

4.4

18

4

≤12.1

1

1.0

`type`

1

12

1

≤6

≤12.1

≤4

4.4

18

4

≤12.1

≤3.2

1.0

`value`

1

12

1

≤6

≤12.1

≤4

4.4

18

4

≤12.1

≤3.2

1.0

See also
--------

- Other list-related HTML Elements: [`<ul>`](ul), [`<ol>`](ol),
    [`<menu>`](menu), and the obsolete [`<dir>`](dir);
- CSS properties that may be specially useful to style the `<li>`
    element:
  - the
        [`list-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style)
        property, to choose the way the ordinal is displayed,
  - [CSS
        counters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles/Using_CSS_counters),
        to handle complex nested lists,
  - the
        [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)
        property, to control the indent of the list item.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li>>
