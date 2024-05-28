:invalid
========

The `:invalid` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents any
[`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form),
[`<fieldset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset),
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
or other
[`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)
element whose contents fail to
[validate](https://developer.mozilla.org/en-US/docs/Web/HTML/Constraint_validation).

Try it
------

This pseudo-class is useful for highlighting field errors for the user.

Syntax
------

[css]

```css
:invalid {
  /* ... */
}
```

Examples
--------

### Coloring elements to show validation

#### HTML

[html]

```html
<form>
  <div class="field">
    <label for="url_input">Enter a URL:</label>
    <input type="url" id="url_input" />
  </div>

  <div class="field">
    <label for="email_input">Enter an email address:</label>
    <input type="email" id="email_input" required />
  </div>
</form>
```

#### CSS

[css]

```css
label {
  display: block;
  margin: 1px;
  padding: 1px;
}

.field {
  margin: 1px;
  padding: 1px;
}

input:invalid {
  background-color: #ffdddd;
}

form:invalid {
  border: 5px solid #ffdddd;
}

input:valid {
  background-color: #ddffdd;
}

form:valid {
  border: 5px solid #ddffdd;
}

input:required {
  border-color: #800000;
  border-width: 3px;
}

input:required:invalid {
  border-color: #c00000;
}
```

#### Result

### Showing sections in stages

In this example we use `:invalid` along with `~`, the
[subsequent-sibling combinator](subsequent-sibling_combinator.md), to make
a form appear in stages, so the form initially shows the first item to
complete, and when the user completes each item the form displays the
next one. When the whole form is complete the user can submit it.

#### HTML

[html]

```html
<form>
  <fieldset>
    <label for="form-name">Name</label><br />
    <input type="text" name="name" id="form-name" required />
  </fieldset>

  <fieldset>
    <label for="form-email">Email Address</label><br />
    <input type="email" name="email" id="form-email" required />
  </fieldset>

  <fieldset>
    <label for="form-message">Message</label><br />
    <textarea name="message" id="form-message" required></textarea>
  </fieldset>

  <button type="submit" name="send">Submit</button>
</form>
```

#### CSS

[css]

```css
/* Hide the fieldset after an invalid fieldset */
fieldset:invalid ~ fieldset {
  display: none;
}

/* Dim and disable the button while the form is invalid */
form:invalid button {
  opacity: 0.3;
  pointer-events: none;
}

input,
textarea {
  box-sizing: border-box;
  width: 100%;
  font-family: monospace;
  padding: 0.25em 0.5em;
}

button {
  width: 100%;
  border: thin solid darkgrey;
  font-size: 1.25em;
  background-color: darkgrey;
  color: white;
}
```

#### Result

Accessibility concerns
----------------------

The color red is commonly used to indicate invalid input. People who
have certain types of color blindness will be unable to determine the
input\'s state unless it is accompanied by an additional indicator that
does not rely on color to convey meaning. Typically, descriptive text
and/or an icon are used.

- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.1 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-without-color.html)

Notes
-----

### Radio buttons

If any one of the radio buttons in a group is `required`, the `:invalid`
pseudo-class is applied to all of them if none of the buttons in the
group is selected. (Grouped radio buttons share the same value for their
`name` attribute.)

### Gecko defaults

By default, Gecko does not apply a style to the `:invalid` pseudo-class.
However, it does apply a style (a red \"glow\" using the
[`box-shadow`](box-shadow.md) property) to the
[`:user-invalid`](:user-invalid) pseudo-class, which applies in a subset
of cases for `:invalid`.

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-invalid]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-invalid)

[Selectors Level 4\
  [\# validity-pseudos]](https://drafts.csswg.org/selectors/#validity-pseudos)
  ----------------------------------------------------------------------------------------------------------

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

`:invalid`

10

12

4

10

10

5

37

18

4

10.1

5

1.0

`form`

40

79

13

No

27

9

40

40

14

27

9

4.0

See also
--------

- Other validation-related pseudo-classes: [`:required`](:required),
    [`:optional`](:optional), [`:valid`](:valid)
- Related Mozilla pseudo-classes: [`:user-invalid`](:user-invalid),
    [`:-moz-submit-invalid`](:-moz-submit-invalid)
- [Form data
    validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)
- Accessing the [validity
    state](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState)
    from JavaScript

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid>
