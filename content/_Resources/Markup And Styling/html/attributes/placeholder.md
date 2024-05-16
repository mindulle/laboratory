HTML attribute: placeholder
===========================

The `placeholder` attribute defines the text displayed in a form control
when the control has no value. The placeholder text should provide a
brief hint to the user as to the expected type of data that should be
entered into the control.

Effective placeholder text includes a word or short phrase that hints at
the expected data type, not an explanation or prompt. The placeholder
must not be used instead of a [`<label>`](../element/label). As the
placeholder is not visible if the value of the form control is not null,
using `placeholder` instead of a `<label>` for a prompt harms usability
and accessibility.

The `placeholder` attribute is supported by the following input types:
`text`, `search`, `url`, `tel`, `email`, and `password`. It is also
supported by the `<textarea>` element. The [example](#example) below
shows the `placeholder` attribute in use to explain the expected format
of an input field.

**Note:** The `placeholder` attribute can\'t include any line feeds (LF)
or carriage returns (CR). If either is included in the value, the
placeholder text will be clipped.

Accessibility concerns
----------------------

Placeholders should only be used to show an example of the type of data
that should be entered into a form; never as a replacement for a
`<label>` element; doing so harms accessibility and user experience.

The `<label>` text is visually and programmatically associated with its
corresponding form control. Screen readers don\'t announce placeholder
content by default, but they do announce label content; it\'s the label
that informs assistive technology users what data should be entered in
the control. Labels also improve user experience for users of pointing
devices: When a user clicks, touches, or taps a `<label>`, focus is
moved to the the label\'s associated form control.

Placeholders can not be relied upon as a replacement for a label even
for those not relying on assistive technology. Placeholder text is
displayed at lower color contrast than the default form control text.
This is by design, as you don\'t want users to be confused by what is
placeholder text versus what is a filled-in form field. However, this
lack of contrast can cause issues for low-vision users. Additionally,
placeholder text disappears from form fields when users start entering
text. If the placeholder text contains instructional information or
examples that disappear, it can be confusing to users with cognitive
issues and can make the form inaccessible if the placeholder contained
the label.

Example
-------

### HTML

[html]

```html
<form action="/en-US/docs/Web/HTML/Attributes/placeholder">
  <label for="name">Enter your name:</label>
  <input type="text" id="name" name="name" placeholder="e.g. Mike Shinoda" />
  <button type="submit">Submit</button>
</form>
```

### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  attr-input-placeholder]](https://html.spec.whatwg.org/multipage/input.html#attr-input-placeholder)

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

`placeholder`

4

12

4

10

≤12.1

5

≤37

18

4

≤12.1

5

1.0

`line_breaks`

36

12

59

10

23

No

37

36

59

No

No

3.0

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

`placeholder`

3

12

4

10

≤12.1

4

≤37

18

4

≤12.1

3.2

1.0

### html.elements.input.placeholder

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### html.elements.textarea.placeholder

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

See also
--------

- HTML [`title`](../global_attributes/title)
- CSS
    [`:placeholder-shown`](https://developer.mozilla.org/en-US/docs/Web/CSS/:placeholder-shown)
    pseudo-class selector
- CSS
    [`::placeholder`](https://developer.mozilla.org/en-US/docs/Web/CSS/::placeholder)
    pseudo-element selector

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/placeholder>>
