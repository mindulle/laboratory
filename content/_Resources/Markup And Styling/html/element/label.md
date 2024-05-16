\<label\>: The Label element
============================

The `<label>` [HTML](../index) element represents a caption for an item
in a user interface.

Try it
------

Associating a `<label>` with a form control, such as [`<input>`](input)
or [`<textarea>`](textarea) offers some major advantages:

- The label text is not only visually associated with its
    corresponding text input; it is programmatically associated with it
    too. This means that, for example, a screen reader will read out the
    label when the user is focused on the form input, making it easier
    for an assistive technology user to understand what data should be
    entered.
- When a user clicks or touches/taps a label, the browser passes the
    focus to its associated input (the resulting event is also raised
    for the input). That increased hit area for focusing the input
    provides an advantage to anyone trying to activate it --- including
    those using a touch-screen device.

To explicitly associate a `<label>` element with an `<input>` element,
you first need to add the `id` attribute to the `<input>` element. Next,
you add the `for` attribute to the `<label>` element, where the value of
`for` is the same as the `id` in the `<input>` element.

Alternatively, you can nest the `<input>` directly inside the `<label>`,
in which case the `for` and `id` attributes are not needed because the
association is implicit:

[html]

```html
<label>
  Do you like peas?
  <input type="checkbox" name="peas" />
</label>
```

The form control that a label is labeling is called the *labeled
control* of the label element. Multiple labels can be associated with
the same form control:

[html]

```html
<label for="username">Enter your username:</label>
<input id="username" name="username" type="text" />
<label for="username">Forgot your username?</label>
```

Elements that can be associated with a `<label>` element include
[`<button>`](button), [`<input>`](input) (except for `type="hidden"`),
[`<meter>`](meter), [`<output>`](output), [`<progress>`](progress),
[`<select>`](select) and [`<textarea>`](textarea).

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`for`](#for)

:   The value of the `for` attribute must be a single
    [`id`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#id) for a
    [labelable](../content_categories#labelable) form-related element in
    the same document as the `<label>` element. So, any given `label`
    element can be associated with only one form control.

    **Note:** To programmatically set the `for` attribute, use
    [`htmlFor`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement/htmlFor).
    

    The first element in the document with an `id` attribute matching
    the value of the `for` attribute is the *labeled control* for this
    `label` element --- if the element with that `id` is actually a
    [labelable
    element](https://html.spec.whatwg.org/multipage/forms.html#category-label).
    If it is *not* a labelable element, then the `for` attribute has no
    effect. If there are other elements that also match the `id` value,
    later in the document, they are not considered.

    Multiple `label` elements can be given the same value for their
    `for` attribute; doing so causes the associated form control (the
    form control that `for` value references) to have multiple labels.

     
    **Note:** A `<label>` element can have both a `for` attribute and a
    contained control element, as long as the `for` attribute points to
    the contained control element.

Styling with CSS
----------------

There are no special styling considerations for `<label>` elements ---
structurally they are simple inline elements, and so can be styled in
much the same way as a [`<span>`](span) or [`<a>`](a) element. You can
apply styling to them in any way you want, as long as you don\'t cause
the text to become difficult to read.

Examples
--------

### Defining an implicit label

[html]

```html
<label>Click me <input type="text" /></label>
```

### Defining an explicit label with the \"for\" attribute

[html]

```html
<label for="username">Click me to focus on the input field</label>
<input type="text" id="username" />
```

Accessibility concerns
----------------------

### Interactive content

Don\'t place interactive elements such as [anchors](a) or
[buttons](button) inside a `label`. Doing so makes it difficult for
people to activate the form input associated with the `label`.

**Don\'t do this:**

[html]

```html
<label for="tac">
  <input id="tac" type="checkbox" name="terms-and-conditions" />
  I agree to the <a href="terms-and-conditions.html">Terms and Conditions</a>
</label>
```

**Prefer this:**

[html]

```html
<label for="tac">
  <input id="tac" type="checkbox" name="terms-and-conditions" />
  I agree to the Terms and Conditions
</label>
<p>
  <a href="terms-and-conditions.html">Read our Terms and Conditions</a>
</p>
```

### Headings

Placing [heading elements](heading_elements) within a `<label>`
interferes with many kinds of assistive technology, because headings are
commonly used as [a navigation aid](heading_elements#navigation). If the
label\'s text needs to be adjusted visually, use CSS classes applied to
the `<label>` element instead.

If a [form](form), or a section of a form needs a title, use the
[`<legend>`](legend) element placed within a [`<fieldset>`](fieldset).

**Don\'t do this:**

[html]

```html
<label for="your-name">
  <h3>Your name</h3>
  <input id="your-name" name="your-name" type="text" />
</label>
```

**Prefer this:**

[html]

```html
<label class="large-label" for="your-name">
  Your name
  <input id="your-name" name="your-name" type="text" />
</label>
```

### Buttons

An [`<input>`](input) element with a `type="button"` declaration and a
valid `value` attribute does not need a label associated with it. Doing
so may actually interfere with how assistive technology parses the
button input. The same applies for the [`<button>`](button) element.

Technical summary
-----------------

  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), [interactive content](../content_categories#interactive_content), [form-associated element](../content_categories#form-associated_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content), but no descendant `label` elements. No [labelable](../content_categories#labelable) elements other than the labeled control are allowed.
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLLabelElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement)
  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  --------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-label-element]](https://html.spec.whatwg.org/multipage/forms.html#the-label-element)

  --------------------------------------------------------------------------------------------------

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

`label`

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

`for`

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

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label>>
