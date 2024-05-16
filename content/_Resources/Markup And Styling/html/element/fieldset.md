\<fieldset\>: The Field Set element
===================================

The `<fieldset>` [HTML](../index) element is used to group several
controls as well as labels ([`<label>`](label)) within a web form.

Try it
------

As the example above shows, the `<fieldset>` element provides a grouping
for a part of an HTML form, with a nested [`<legend>`](legend) element
providing a caption for the `<fieldset>`. It takes few attributes, the
most notable of which are `form`, which can contain the `id` of a
[`<form>`](form) on the same page, allowing you to make the `<fieldset>`
part of that `<form>` even if it is not nested inside it, and
`disabled`, which allows you to disable the `<fieldset>` and all its
contents in one go.

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`disabled`](#disabled)

:   If this Boolean attribute is set, all form controls that are
    descendants of the `<fieldset>`, are disabled, meaning they are not
    editable and won\'t be submitted along with the [`<form>`](form).
    They won\'t receive any browsing events, like mouse clicks or
    focus-related events. By default browsers display such controls
    grayed out. Note that form elements inside the [`<legend>`](legend)
    element won\'t be disabled.

[`form`](#form)

:   This attribute takes the value of the
    [`id`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#id) attribute of a [`<form>`](form)
    element you want the `<fieldset>` to be part of, even if it is not
    inside the form. Please note that usage of this is confusing --- if
    you want the [`<input>`](input) elements inside the `<fieldset>` to
    be associated with the form, you need to use the `form` attribute
    directly on those elements. You can check which elements are
    associated with a form via JavaScript, using
    [`HTMLFormElement.elements`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements).

[`name`](#name)

:   The name associated with the group.

    **Note:** The caption for the fieldset is given by the first
    [`<legend>`](legend) element nested inside it.

Styling with CSS
----------------

There are several special styling considerations for `<fieldset>`.

Its
[`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
value is `block` by default, and it establishes a [block formatting
context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context).
If the `<fieldset>` is styled with an inline-level `display` value, it
will behave as `inline-block`, otherwise it will behave as `block`. By
default there is a `2px` `groove` border surrounding the contents, and a
small amount of default padding. The element has
[`min-inline-size: min-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-inline-size)
by default.

If a [`<legend>`](legend) is present, it is placed over the
`block-start` border. The `<legend>` shrink-wraps, and also establishes
a formatting context. The `display` value is blockified. (For example,
`display: inline` behaves as `block`.)

There will be an anonymous box holding the contents of the `<fieldset>`,
which inherits certain properties from the `<fieldset>`. If the
`<fieldset>` is styled with `display: grid` or `display: inline-grid`,
then the anonymous box will be a grid formatting context. If the
`<fieldset>` is styled with `display: flex` or `display: inline-flex`,
then the anonymous box will be a flex formatting context. Otherwise, it
establishes a block formatting context.

You can feel free to style the `<fieldset>` and `<legend>` in any way
you want to suit your page design.

Examples
--------

### Simple fieldset

This example shows a really simple `<fieldset>` example, with a
`<legend>`, and a single control inside it.

[html]

```html
<form action="#">
  <fieldset>
    <legend>Do you agree?</legend>
    <input type="checkbox" id="chbx" name="agree" value="Yes!" />
    <label for="chbx">I agree</label>
  </fieldset>
</form>
```

#### Result

### Disabled fieldset

This example shows a disabled `<fieldset>` with two controls inside it.
Note how both the controls are disabled due to being inside a disabled
`<fieldset>`.

[html]

```html
<form action="#">
  <fieldset disabled>
    <legend>Disabled login fieldset</legend>
    <div>
      <label for="name">Name: </label>
      <input type="text" id="name" value="Chris" />
    </div>
    <div>
      <label for="pwd">Archetype: </label>
      <input type="password" id="pwd" value="Wookie" />
    </div>
  </fieldset>
</form>
```

#### Result

Technical summary
-----------------

  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [sectioning root](heading_elements#sectioning_root), [listed](../content_categories#form_listed), [form-associated](../content_categories#form-associated_content) element, palpable content.
  Permitted content                             An optional [`<legend>`](legend) element, followed by flow content.
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content).
  Implicit ARIA role                            [`group`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/group_role)
  Permitted ARIA roles                          [`radiogroup`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/radiogroup_role), [`presentation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role), [`none`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/none_role)
  DOM interface                                 [`HTMLFieldSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFieldSetElement)
  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-fieldset-element]](https://html.spec.whatwg.org/multipage/form-elements.html#the-fieldset-element)

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

`fieldset`

1Before version 86, this element did not support `flexbox` and `grid`
layouts within this element. See [bug 262679](https://crbug.com/262679).

12Before version 86, this element did not support `flexbox` and `grid`
layouts within this element. See [bug
4511145](https://developer.microsoft.com/microsoft-edge/platform/issues/4511145/).

1

Yes

≤15

≤4

4.4Before version 86, this element did not support `flexbox` and `grid`
layouts within this element. See [bug 262679](https://crbug.com/262679).

18Before version 86, this element did not support `flexbox` and `grid`
layouts within this element. See [bug 262679](https://crbug.com/262679).

4

≤14

≤3.2

1.0Before version 14.0, this element did not support `flexbox` and
`grid` layouts within this element. See [bug
262679](https://crbug.com/262679).

`disabled`

20

12Does not work with nested fieldsets. For example:
`<fieldset disabled><fieldset><!--Still enabled--></fieldset></fieldset>`

4

YesNot all form control descendants of a disabled fieldset are properly
disabled in IE11; see IE [bug 817488: input\[type=\'file\'\] not
disabled inside disabled
fieldset](https://connect.microsoft.com/IE/feedbackdetail/view/817488)
and IE [bug 962368: Can still edit input\[type=\'text\'\] within
fieldset\[disabled\]](https://connect.microsoft.com/IE/feedbackdetail/view/962368/can-still-edit-input-type-text-within-fieldset-disabled).

12

6

4.4

25

4

12

6

1.5

`form`

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

`name`

19

12

4

Yes

15

6

4.4

25

4

14

6

1.5

See also
--------

- The [`<legend>`](legend) element
- The [`<input>`](input) element
- The [`<label>`](label) element
- The [`<form>`](form) element

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset>>
