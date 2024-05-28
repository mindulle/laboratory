:required
=========

The `:required` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents any
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input),
[`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select),
or
[`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)
element that has the
[`required`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#required)
attribute set on it.

Try it
------

This pseudo-class is useful for highlighting fields that must have valid
data before a form can be submitted.

**Note:** The [`:optional`](:optional) pseudo-class selects *optional*
form fields.

Syntax
------

[css]

```css
:required {
  /* ... */
}
```

Examples
--------

### The required field has a red border

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

input:required {
  border-color: #800000;
  border-width: 3px;
}

input:required:invalid {
  border-color: #c00000;
}
```

#### Result

Accessibility concerns
----------------------

Mandatory
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)s
should have the
[`required`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#required)
attribute applied to them. This will ensure that people navigating with
the aid of assistive technology such as a screen reader will be able to
understand which inputs need valid content to ensure a successful
submission.

If the form also contains [optional](:optional) inputs, required inputs
should be indicated visually using a treatment that does not rely solely
on color to convey meaning. Typically, descriptive text and/or an icon
are used.

- [MDN Understanding WCAG, Guideline 3.3
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Understandable#guideline_3.3_%e2%80%94_input_assistance_help_users_avoid_and_correct_mistakes)
- [Understanding Success Criterion 3.3.2 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/minimize-error-cues.html)

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-required]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-required)

[Selectors Level 4\
  [\# opt-pseudos]](https://drafts.csswg.org/selectors/#opt-pseudos)
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

`:required`

10

12

4

10

10

5

4.4.3

18

4

10.1

5

1.0

See also
--------

- Other validation-related pseudo-classes: [`:optional`](:optional),
    [`:invalid`](:invalid), [`:valid`](:valid)
- [Form data
    validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:required>
