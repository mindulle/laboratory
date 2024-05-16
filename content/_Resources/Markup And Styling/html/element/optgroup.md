\<optgroup\>: The Option Group element
======================================

The `<optgroup>` [HTML](../index) element creates a grouping of options
within a [`<select>`](select) element.

Try it
------

**Note:** Optgroup elements may not be nested.

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`disabled`](#disabled)

:   If this Boolean attribute is set, none of the items in this option
    group is selectable. Often browsers grey out such control and it
    won\'t receive any browsing events, like mouse clicks or
    focus-related ones.

[`label`](#label)

:   The name of the group of options, which the browser can use when
    labeling the options in the user interface. This attribute is
    mandatory if this element is used.

Examples
--------

[html]

```html
<select>
  <optgroup label="Group 1">
    <option>Option 1.1</option>
  </optgroup>
  <optgroup label="Group 2">
    <option>Option 2.1</option>
    <option>Option 2.2</option>
  </optgroup>
  <optgroup label="Group 3" disabled>
    <option>Option 3.1</option>
    <option>Option 3.2</option>
    <option>Option 3.3</option>
  </optgroup>
</select>
```

### Result

Technical summary
-----------------

  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   None.
  Permitted content                             Zero or more [`<option>`](option) elements.
  Tag omission                                  The start tag is mandatory. The end tag is optional if this element is immediately followed by another `<optgroup>` element, or if the parent element has no more content.
  Permitted parents                             A [`<select>`](select) element.
  Implicit ARIA role                            [`group`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/group_role)
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLOptGroupElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptGroupElement)
  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-optgroup-element]](https://html.spec.whatwg.org/multipage/form-elements.html#the-optgroup-element)

  ----------------------------------------------------------------------------------------------------------------

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

`optgroup`

1

12

1

5.5

15

≤4

4.4

18

4

14

≤3.2

1.0

`disabled`

1

12

1

8

15

≤4

4.4

18

4

14

≤3.2

1.0

`label`

1

12

1

5.5

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

- Other form-related elements: [`<form>`](form), [`<legend>`](legend),
    [`<label>`](label), [`<button>`](button), [`<select>`](select),
    [`<datalist>`](datalist), [`<option>`](option),
    [`<fieldset>`](fieldset), [`<textarea>`](textarea),
    [`<input>`](input), [`<output>`](output), [`<progress>`](progress)
    and [`<meter>`](meter).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/optgroup>>
