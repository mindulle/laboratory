\<datalist\>: The HTML Data List element
========================================

The `<datalist>` [HTML](../index) element contains a set of
[`<option>`](option) elements that represent the permissible or
recommended options available to choose from within other controls.

Try it
------

To bind the `<datalist>` element to the control, we give it a unique
identifier in the [`id`](../global_attributes/id) attribute, and then
add the [`list`](input#list) attribute to the [`<input>`](input) element
with the same identifier as value. Only certain types of
[`<input>`](input) support this behavior, and it can also vary from
browser to browser.

**Note:** The `<option>` element can store a value as internal content
and in the `value` and `label` attributes. Which one will be visible in
the drop-down menu depends on the browser, but when clicked, content
entered into control field will always come from the `value` attribute.

Attributes
----------

This element has no other attributes than the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md), common to all elements.

Examples
--------

### Textual types

Recommended values in types [text](input/text), [search](input/search),
[url](input/url), [tel](input/tel), [email](input/email) and
[number](input/number), are displayed in a drop-down menu when user
clicks or double-clicks on the control. Typically the right side of a
control will also have an arrow pointing to the presence of predefined
values.

[html]

```html
<label for="myBrowser">Choose a browser from this list:</label>
<input list="browsers" id="myBrowser" name="myBrowser" />
<datalist id="browsers">
  <option value="Chrome"></option>
  <option value="Firefox"></option>
  <option value="Opera"></option>
  <option value="Safari"></option>
  <option value="Microsoft Edge"></option>
</datalist>
```

### Date and Time types

The types [month](input/month), [week](input/week), [date](input/date),
[time](input/time) and [datetime-local](input/datetime-local) can show
an interface that allows a convenient selection of a date and time.
Predefined values can be shown there, allowing the user to quickly fill
the control value.

**Note:** When type is not supported, `text` type creating simple text
field will be used instead. That field will correctly recognize
recommended values and display them to the user in a drop-down menu.

[html]

```html
<input type="time" list="popularHours" />
<datalist id="popularHours">
  <option value="12:00"></option>
  <option value="13:00"></option>
  <option value="14:00"></option>
</datalist>
```

### Range type

The recommended values in the [range](input/range) type will be shown as
series of hash marks that the user can easily select.

[html]

```html
<label for="tick">Tip amount:</label>
<input type="range" list="tickmarks" min="0" max="100" id="tick" name="tick" />
<datalist id="tickmarks">
  <option value="0"></option>
  <option value="10"></option>
  <option value="20"></option>
  <option value="30"></option>
</datalist>
```

### Color type

The [color](input/color) type can show predefined colors in a
browser-provided interface.

[html]

```html
<label for="colors">Pick a color (preferably a red tone):</label>
<input type="color" list="redColors" id="colors" />
<datalist id="redColors">
  <option value="#800000"></option>
  <option value="#8B0000"></option>
  <option value="#A52A2A"></option>
  <option value="#DC143C"></option>
</datalist>
```

### Password type

The specification allows linking `<datalist>` with a
[password](input/password) type, but no browser supports it for security
reasons.

[html]

```html
<label for="pwd">Enter a password:</label>
<input type="password" list="randomPassword" id="pwd" />
<datalist id="randomPassword">
  <option value="5Mg[_3DnkgSu@!q#"></option>
</datalist>
```

Technical summary
-----------------

  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content).
  Permitted content                             Either [phrasing content](../content_categories#phrasing_content) or zero or more [`<option>`](option) elements.
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            [listbox](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/listbox_role)
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLDataListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDataListElement)
  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------

Accessibility concerns
----------------------

When deciding to use the `<datalist>` element, here are some
accessibility issues to be mindful of:

- The font size of the data list\'s options does not zoom, always
    remaining the same size. The contents of the autosuggest do not grow
    or shrink when the rest of the contents are zoomed in or out.
- As targeting the list of options with CSS is very limited to
    non-existent, rendering can not be styled for high-contrast mode.
- Some screen reader/browser combinations, including NVDA and Firefox,
    do not announce the contents of the autosuggest popup.

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-datalist-element]](https://html.spec.whatwg.org/multipage/form-elements.html#the-datalist-element)

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

`datalist`

20

12

4The `<datalist>` element will only create a dropdown for textual types,
such as `text`, `search`, `url`, `tel`, `email` and `number`. The
`date`, `time`, `range` and `color` types are not supported.

10

9.5

12.1

4.4.3

33

79The dropdown menu containing available options does not appear. See
[bug 1535985](https://bugzil.la/1535985).

4--79

20

12.2

2.0

See also
--------

- The [`<input>`](input) element, and more specifically its
    [`list`](input#list) attribute;
- The [`<option>`](option) element.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/datalist>>
