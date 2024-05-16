:user-invalid
=============

The `:user-invalid` CSS [pseudo-class](pseudo-classes.md) represents any
validated form element whose value isn\'t valid based on their
[validation
constraints](https://developer.mozilla.org/en-US/docs/Learn/Forms#constraint_validation),
after the user has interacted with it.

The `:user-invalid` pseudo-class must match an [`:invalid`](:invalid),
[`:out-of-range`](:out-of-range), or blank-but [`:required`](:required)
element between the time the user has attempted to submit the form and
before the user has interacted again with the form element.

Syntax
------

[css]

```css
:user-invalid {
  /* ... */
}
```

Examples
--------

### Setting a color and symbol on :user-invalid

In the following example, the red border and ❌ only display once the
user has interacted with the field. Try typing something other than an
email address to see it in action.

[html]

```html
<form>
  <label for="email">Email *: </label>
  <input id="email" name="email" type="email" required />
  <span></span>
</form>
```

[css]

```css
input:user-invalid {
  border: 2px solid red;
}

input:user-invalid + span::before {
  content: "✖";
  color: red;
}
```

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  user-invalid-pseudo]](https://drafts.csswg.org/selectors/#user-invalid-pseudo)

  ----------------------------------------------------------------------------------------

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

`:user-invalid`

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
- [`:user-valid`](:user-valid)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:user-invalid>
