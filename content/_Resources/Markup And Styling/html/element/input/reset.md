\<input type=\"reset\"\>
========================

[`<input>`](../input) elements of type `reset` are rendered as buttons,
with a default
[`click`](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event)
event handler that resets all inputs in the form to their initial
values.

Try it
------

**Note:** You should usually avoid including reset buttons in your
forms. They\'re rarely useful, and are instead more likely to frustrate
users who click them by mistake (often while trying to click the [submit
button](submit)).

Value
-----

An `<input type="reset">` element\'s [`value`](../input#value) attribute
contains a string that is used as the button\'s label. Buttons such as
`reset` don\'t have a value otherwise.

### Setting the value attribute

[html]

```html
<input type="reset" value="Reset the form" />
```

### Omitting the value attribute

If you don\'t specify a `value`, you get a button with the default label
(typically \"Reset,\" but this will vary depending on the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)):

[html]

```html
<input type="reset" />
```

Using reset buttons
-------------------

`<input type="reset">` buttons are used to reset forms. If you want to
create a custom button and then customize the behavior using JavaScript,
you need to use [`<input type="button">`](button), or better still, a
[`<button>`](../button) element.

### A simple reset button

We\'ll begin by creating a simple reset button:

[html]

```html
<form>
  <div>
    <label for="example">Type in some sample text</label>
    <input id="example" type="text" />
  </div>
  <div>
    <input type="reset" value="Reset the form" />
  </div>
</form>
```

This renders like so:

Try entering some text into the text field, and then pressing the reset
button.

### Adding a reset keyboard shortcut

To add a keyboard shortcut to a reset button --- just as you would with
any [`<input>`](../input) for which it makes sense --- you use the
[`accesskey`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#accesskey) global attribute.

In this example, [r] is specified as the access key (you\'ll need
to press [r] plus the particular modifier keys for your browser/OS
combination; see [`accesskey`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#accesskey) for a
useful list of those).

[html]

```html
<form>
  <div>
    <label for="example">Type in some sample text</label>
    <input id="example" type="text" />
  </div>
  <div>
    <input type="reset" value="Reset the form" accesskey="r" />
  </div>
</form>
```

The problem with the above example is that there\'s no way for the user
to know what the access key is! This is especially true since the
modifiers are typically non-standard to avoid conflicts. When building a
site, be sure to provide this information in a way that doesn\'t
interfere with the site design (for example by providing an easily
accessible link that points to information on what the site access keys
are). Adding a tooltip to the button (using the
[`title`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#title) attribute) can also help,
although it\'s not a complete solution for accessibility purposes.

### Disabling and enabling a reset button

To disable a reset button, specify the [`disabled`](../input#disabled)
attribute on it, like so:

[html]

```html
<input type="reset" value="Disabled" disabled />
```

You can enable and disable buttons at run time by setting `disabled` to
`true` or `false`; in JavaScript this looks like `btn.disabled = true`
or `btn.disabled = false`.

**Note:** See the
[`<input type="button">`](button#disabling_and_enabling_a_button) page
for more ideas about enabling and disabling buttons.

Validation
----------

Buttons don\'t participate in constraint validation; they have no real
value to be constrained.

Examples
--------

We\'ve included simple examples above. There isn\'t really anything more
to say about reset buttons.

Technical summary
-----------------

  --------------------------------- -----------------------------------------------------------------------------------------------
  **[Value](#value)**               A string used as the button\'s label
  **Events**                        [`click`](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event)
  **Supported common attributes**   [`type`](../input#type) and [`value`](../input#value)
  **IDL attributes**                `value`
  **DOM interface**                 [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
  **Methods**                       None
  **Implicit ARIA Role**            [`button`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/button_role)
  --------------------------------- -----------------------------------------------------------------------------------------------

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  reset-button-state-(type=reset)]](https://html.spec.whatwg.org/multipage/input.html#reset-button-state-(type=reset))

  ------------------------------------------------------------------------------------------------------------------------------

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

`reset`

1

12

1Unlike other browsers, Firefox by default [persists the dynamic
disabled
state](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing)
of a `<button>` across page loads. Use the `autocomplete` attribute to
control this feature.

Yes

15

1

4.4

18

4Unlike other browsers, Firefox by default [persists the dynamic
disabled
state](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing)
of a `<button>` across page loads. Use the `autocomplete` attribute to
control this feature.

14

1

1.0

See also
--------

- [`<input>`](../input) and the
    [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
    interface which implements it.
- [Forms and
    buttons](https://developer.mozilla.org/en-US/docs/Learn/Forms/Basic_native_form_controls#actual_buttons)
- [HTML forms](https://developer.mozilla.org/en-US/docs/Learn/Forms)
- The [`<button>`](../button) element
- [Compatibility of CSS
    properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/reset>>
