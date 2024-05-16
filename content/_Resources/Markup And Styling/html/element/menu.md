\<menu\>: The Menu element
==========================

The `<menu>` [HTML](../index) element is described in the HTML
specification as a semantic alternative to [`<ul>`](ul), but treated by
browsers (and exposed through the accessibility tree) as no different
than [`<ul>`](ul). It represents an unordered list of items (which are
represented by [`<li>`](li) elements).

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

The `<menu>` and [`<ul>`](ul) elements both represent an unordered list
of items. The key difference is that [`<ul>`](ul) primarily contains
items for display, while `<menu>` was intended for interactive items.
The related [`<menuitem>`](menuitem) element has been deprecated.

**Note:** In early versions of the HTML specification, the `<menu>`
element had an additional use case as a context menu. This functionality
is considered obsolete and is not in the specification.

Examples
--------

### Toolbar

In this example, a `<menu>` is used to create a toolbar for an editing
application.

#### HTML

[html]

```html
<menu>
  <li><button onclick="copy()">Copy</button></li>
  <li><button onclick="cut()">Cut</button></li>
  <li><button onclick="paste()">Paste</button></li>
</menu>
```

Note that this is functionally no different from:

[html]

```html
<ul>
  <li><button onclick="copy()">Copy</button></li>
  <li><button onclick="cut()">Cut</button></li>
  <li><button onclick="paste()">Paste</button></li>
</ul>
```

#### CSS

[css]

```css
menu,
ul {
  display: flex;
  list-style: none;
  padding: 0;
  width: 400px;
}

li {
  flex-grow: 1;
}

button {
  width: 100%;
}

```

#### Result

Technical summary
-----------------

  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content). If the element\'s children include at least one [`<li>`](li) element: [Palpable content](../content_categories#palpable_content).
  Permitted content                             Zero or more occurrences of [`<li>`](li), [`<script>`](script), and [`<template>`](template).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content).
  Implicit ARIA role                            `list`
  Permitted ARIA roles                          [`directory`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/directory_role), [`group`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/group_role), `listbox`, [`menu`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/menu_role), [`menubar`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/menubar_role), [`none`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/none_role), [`presentation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role), [`radiogroup`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/radiogroup_role), [`tablist`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/tablist_role), [`toolbar`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/toolbar_role) or [`tree`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/tree_role)
  DOM interface                                 [`HTMLMenuElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMenuElement)
  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -----------------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-menu-element]](https://html.spec.whatwg.org/multipage/grouping-content.html#the-menu-element)

  -----------------------------------------------------------------------------------------------------------

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

`menu`

1

12

1

6

≤12.1

3

4.4

18

4

≤12.1

1

1.0

`hr_separator`

No

No

51--85

No

No

No

No

No

51--85

No

No

No

`label`

No

No

8--85

No

No

No

No

No

8--85Nested menus are not supported.

No

No

No

`type_menu`

No

≤18--79

8--85

No

No

No

No

No

8--85Nested menus are not supported.

No

No

No

See also
--------

- Other list-related HTML Elements: [`<ol>`](ol), [`<ul>`](ul), and
    [`<li>`](li).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/menu>
