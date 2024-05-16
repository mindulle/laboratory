HTML attribute: minlength
=========================

The `minlength` attribute defines the minimum [string
length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
that the user can enter into an [`<input>`](../element/input) or
[`<textarea>`](../element/textarea). The attribute must have an integer
value of 0 or higher.

The length is measured in UTF-16 code units, which ([for most
scripts](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length#strings_with_length_not_equal_to_the_number_of_characters))
is equivalent to the number of characters. If no `minlength` is
specified, or an invalid value is specified, the input has no minimum
length. This value must be less than or equal to the value of
[maxlength](maxlength), otherwise the value will never be valid, as it
is impossible to meet both criteria.

The input will fail constraint validation if the length of the text
value of the field is less than minlength UTF-16 code units long, with
[`validityState.tooShort`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooShort)
returning `true`. Constraint validation is only applied when the value
is changed by the user. Once submission fails, some browsers will
display an error message indicating the minimum length required and the
current length.

Try it
------

Examples
--------

By adding `minlength="5"`, the value must either be empty or five
characters or longer to be valid.

[html]

```html
<label for="fruit">Enter a fruit name that is at least 5 letters long</label>
<input type="text" minlength="5" id="fruit" />
```

We can use pseudoclasses to style the element based on whether the value
is valid. The value will be valid as long as it is either null (empty)
or five or more characters long. *Lime* is invalid, *lemon is valid*.

[css]

```css
input {
  border: 2px solid currentcolor;
}
input:invalid {
  border: 2px dashed red;
}
input:invalid:focus {
  background-image: linear-gradient(pink, lightgreen);
}

```

Specifications
--------------

  --------------------------------------------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-maxlength-and-minlength-attributes]](https://html.spec.whatwg.org/multipage/input.html#the-maxlength-and-minlength-attributes)

  --------------------------------------------------------------------------------------------------------------------------------------------

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

`minlength`

40

17

51

No

27

10.1

40

40

51

27

10.3

4.0

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

`minlength`

40

17

51

No

27

10.1

40

40

51

27

10.3

4.0

### html.elements.input.minlength

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### html.elements.textarea.minlength

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

See also
--------

- [`maxlength`](maxlength)
- [`size`](size)
- [`pattern`](pattern)
- [Constraint validation](../constraint_validation)
- [Form
    validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)
- [`<input>`](../element/input)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/minlength>
