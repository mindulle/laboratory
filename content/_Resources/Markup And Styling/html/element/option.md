\<option\>: The HTML Option element
===================================

The `<option>` [HTML](../index) element is used to define an item
contained in a [`<select>`](select), an [`<optgroup>`](optgroup), or a
[`<datalist>`](datalist) element. As such, `<option>` can represent menu
items in popups and other lists of items in an HTML document.

Try it
------

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`disabled`](#disabled)

:   If this Boolean attribute is set, this option is not checkable.
    Often browsers grey out such control and it won\'t receive any
    browsing event, like mouse clicks or focus-related ones. If this
    attribute is not set, the element can still be disabled if one of
    its ancestors is a disabled [`<optgroup>`](optgroup) element.

[`label`](#label)

:   This attribute is text for the label indicating the meaning of the
    option. If the `label` attribute isn\'t defined, its value is that
    of the element text content.

[`selected`](#selected)

:   If present, this Boolean attribute indicates that the option is
    initially selected. If the `<option>` element is the descendant of a
    [`<select>`](select) element whose [`multiple`](select#multiple)
    attribute is not set, only one single `<option>` of this
    [`<select>`](select) element may have the `selected` attribute.

[`value`](#value)

:   The content of this attribute represents the value to be submitted
    with the form, should this option be selected. If this attribute is
    omitted, the value is taken from the text content of the option
    element.

Styling with CSS
----------------

Styling the `<option>` element is highly limited. Options don\'t inherit
the font set on the parent. In Firefox, only
[`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) and
[`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color)
can be set, however in Chrome and Safari it\'s not possible to set any
properties. You can find more details about styling in [our guide to
advanced form
styling](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling).

Examples
--------

See [`<select>`](select) for examples.

Technical summary
-----------------

  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   None.
  Permitted content                             Text, possibly with escaped characters (like `&eacute;`).
  Tag omission                                  The start tag is mandatory. The end tag is optional if this element is immediately followed by another `<option>` element or an [`<optgroup>`](optgroup), or if the parent element has no more content.
  Permitted parents                             A [`<select>`](select), an [`<optgroup>`](optgroup) or a [`<datalist>`](datalist) element.
  Implicit ARIA role                            [`option`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/option_role)
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLOptionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionElement)
  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-option-element]](https://html.spec.whatwg.org/multipage/form-elements.html#the-option-element)

  ------------------------------------------------------------------------------------------------------------

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

`option`

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

`disabled`

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

`label`

1

12

1\[\"Before 77, Firefox didn\'t display the value of the `label`
attribute as option text if element\'s content was empty. See [bug
40545](https://bugzil.la/40545).\", \"Historically, Firefox has allowed
keyboard and mouse events to bubble up from the `<option>` element to
the parent `<select>` element, although this behavior is inconsistent
across many browsers. For better Web compatibility (and for technical
reasons), they will not bubble up when Firefox is in multi-process mode
and the `<select>` element is displayed as a drop-down list. The
behavior is unchanged if the `<select>` is presented inline and it has
either the `multiple` attribute defined or a `size` attribute set to
more than `1`. Rather than watching `<option>` elements for events, you
should watch for
[change](https://developer.mozilla.org/docs/Web/Events/change) events on
`<select>`. See [bug 1090602](https://bugzil.la/1090602) for details.\",
\"When Mozilla introduced dedicated content threads to Firefox (through
the Electrolysis, or e10s, project), support for styling `<option>`
elements was removed temporarily. Starting in Firefox 54, you can apply
foreground and background colors to `<option>` elements again, using the
`color` and `background-color` CSS properties. See [bug
910022](https://bugzil.la/910022) for more information. Note that this
is still disabled in Linux due to lack of contrast (see [bug
1338283](https://bugzil.la/1338283) for progress on this).\"\]

Yes

15

≤4

4.4

18

4Before 77, Firefox didn\'t display the value of the `label` attribute
as option text if element\'s content was empty. See [bug
40545](https://bugzil.la/40545).

14

≤3.2

1.0

`selected`

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

`value`

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

- Other form-related elements: [`<form>`](form), [`<legend>`](legend),
    [`<label>`](label), [`<button>`](button), [`<select>`](select),
    [`<datalist>`](datalist), [`<optgroup>`](optgroup),
    [`<fieldset>`](fieldset), [`<textarea>`](textarea),
    [`<input>`](input), [`<output>`](output), [`<progress>`](progress)
    and [`<meter>`](meter).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option>>
