:user-valid
===========

The `:user-valid` CSS [pseudo-class](pseudo-classes.md) represents any
validated form element whose value validates correctly based on its
[validation
constraints](https://developer.mozilla.org/en-US/docs/Learn/Forms#constraint_validation).
However, unlike [`:valid`](:valid) it only matches once the user has
interacted with it.

This pseudo-class is applied according to the following rules:

- If the control does not have focus, and the value is valid, apply
    this pseudo-class.
- If the control has focus, and the value was valid (including empty)
    when it gained focus, apply this pseudo-class.
- If the control has focus, and the value was invalid when it gained
    focus, re-validate on every keystroke.
- If the element is required, the preceding rules apply only if the
    user has changed the value or attempted to submit the form.

The result is that if the control was valid when the user started
interacting with it, the validity styling is changed only when the user
shifts focus to another control. However, if the user is trying to
correct a previously-flagged value, the control shows immediately when
the value becomes valid. Required items are flagged as invalid only if
the user changes them or attempts to submit an unchanged invalid value.

Syntax
------

[css]

```css
:user-valid {
  /* ... */
}
```

Examples
--------

### Setting a color and symbol on :user-valid

In the following example, the green border and ✅ only display once the
user has interacted with the field. Try changing the email address to
another valid email to see it in action.

[html]

```html
<form>
  <label for="email">Email *: </label>
  <input
    id="email"
    name="email"
    type="email"
    value="test@example.com"
    required />
  <span></span>
</form>
```

[css]

```css
input:user-valid {
  border: 2px solid green;
}

input:user-valid + span::before {
  content: "✓";
  color: green;
}
```

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  user-valid-pseudo]](https://drafts.csswg.org/selectors/#user-valid-pseudo)

  ------------------------------------------------------------------------------------

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

`:user-valid`

119

119

884

No

No

16.5

No

119

884

No

16.5

No

See also
--------

- [`:valid`](:valid)
- [`:invalid`](:invalid)
- [`:required`](:required)
- [`:optional`](:optional)
- [`:user-invalid`](:user-invalid)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:user-valid>
