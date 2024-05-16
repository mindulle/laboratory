Constraint validation
=====================

The creation of web forms has always been a complex task. While marking
up the form itself is easy, checking whether each field has a valid and
coherent value is more difficult, and informing the user about the
problem may become a headache.
[HTML5](https://developer.mozilla.org/en-US/docs/Glossary/HTML5)
introduced new mechanisms for forms: it added new semantic types for the
[`<input>`](element/input) element and *constraint validation* to ease
the work of checking the form content on the client side. Basic, usual
constraints can be checked, without the need for JavaScript, by setting
new attributes; more complex constraints can be tested using the
Constraint Validation API.

For a basic introduction to these concepts, with examples, see the [Form
validation
tutorial](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation).

**Note:** HTML Constraint validation doesn\'t remove the need for
validation on the *server side*. Even though far fewer invalid form
requests are to be expected, invalid ones can still be sent such as by
bad people trying to trick your web application. Therefore, you need to
always also validate input constraints on the server side, in a way that
is consistent with what is done on the client side.

Intrinsic and basic constraints
-------------------------------

In HTML, basic constraints are declared in two ways:

- By choosing the most semantically appropriate value for the
    [`type`](element/input#type) attribute of the
    [`<input>`](element/input) element, e.g., choosing the `email` type
    automatically creates a constraint that checks whether the value is
    a valid email address.
- By setting values on validation-related attributes, allowing basic
    constraints to be described in a simple way, without the need for
    JavaScript.

### Semantic input types

The intrinsic constraints for the [`type`](element/input#type) attribute
are:

  Input type                                      Constraint description                                                                                                                                                                                     Associated violation
  ----------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------------
  [`<input type="URL">`](element/input/url)       The value must be an absolute [URL](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Web_mechanics/What_is_a_URL), as defined in the [URL Living Standard](https://url.spec.whatwg.org/).   **[TypeMismatch](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/typeMismatch)** constraint violation
  [`<input type="email">`](element/input/email)   The value must be a syntactically valid email address, which generally has the format `username@hostname.tld` but can also be local such as `username@hostname`.                                           **[TypeMismatch](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/typeMismatch)** constraint violation

For both of these input types, if the
[`multiple`](element/input#multiple) attribute is set, several values
can be set, as a comma-separated list. If any of these do not satisfy
the condition described here, the **Type mismatch** constraint violation
is triggered.

Note that most input types don\'t have intrinsic constraints, as some
are barred from constraint validation or have a sanitization algorithm
transforming incorrect values to a correct default.

### Validation-related attributes

In addition to the `type` attribute described above, the following
attributes are used to describe basic constraints:

Attribute

Input types supporting the attribute

Possible values

Constraint description

Associated violation

`pattern`

`text`, `search`, `url`, `tel`, `email`, `password`

A [JavaScript regular
expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions)
(compiled with the
[`global`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/global),
[`ignoreCase`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/ignoreCase),
and
[`multiline`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/multiline)
flags *disabled*)

The value must match the pattern.

[`patternMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/patternMismatch)
constraint violation

`min`

`range`, `number`

A valid number

The value must be greater than or equal to the value.

`rangeUnderflow` constraint violation

`date`, `month`, `week`

A valid date

`datetime-local`, `time`

A valid date and time

`max`

`range`, `number`

A valid number

The value must be less than or equal to the value

`rangeOverflow` constraint violation

`date`, `month`, `week`

A valid date

`datetime-local`, `time`

A valid date and time

`required`

`text`, `search`, `url`, `tel`, `email`, `password`, `date`,
`datetime-local`, `month`, `week`, `time`, `number`, `checkbox`,
`radio`, `file`; also on the [`<select>`](element/select) and
[`<textarea>`](element/textarea) elements

*none* as it is a Boolean attribute: its presence means *true*, its
absence means *false*

There must be a value (if set).

`valueMissing` constraint violation

`step`

`date`

An integer number of days

Unless the step is set to the `any` literal, the value must be **min** +
an integral multiple of the step.

`stepMismatch` constraint violation

`month`

An integer number of months

`week`

An integer number of weeks

`datetime-local`, `time`

An integer number of seconds

`range`, `number`

An integer

`minlength`

`text`, `search`, `url`, `tel`, `email`, `password`; also on the
[`<textarea>`](element/textarea) element

An integer length

The number of characters (code points) must not be less than the value
of the attribute, if non-empty. All newlines are normalized to a single
character (as opposed to CRLF pairs) for
[`<textarea>`](element/textarea).

`tooShort` constraint violation

`maxlength`

`text`, `search`, `url`, `tel`, `email`, `password`; also on the
[`<textarea>`](element/textarea) element

An integer length

The number of characters (code points) must not exceed the value of the
attribute.

`tooLong` constraint violation

Constraint validation process
-----------------------------

Constraint validation is done through the Constraint Validation API
either on a single form element or at the form level, on the
[`<form>`](element/form) element itself. The constraint validation is
done in the following ways:

- By a call to the `checkValidity()` or `reportValidity()` method of a
    form-associated DOM interface,
    ([`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement),
    [`HTMLSelectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement),
    [`HTMLButtonElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLButtonElement),
    [`HTMLOutputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOutputElement)
    or
    [`HTMLTextAreaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement)),
    which evaluates the constraints only on this element, allowing a
    script to get this information. The `checkValidity()` method returns
    a Boolean indicating whether the element\'s value passes its
    constraints. (This is typically done by the user-agent when
    determining which of the CSS pseudo-classes,
    [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid)
    or
    [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid),
    applies.) In contrast, the `reportValidity()` method reports any
    constraint failures to the user.
- By a call to the `checkValidity()` or `reportValidity()` method on
    the
    [`HTMLFormElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement)
    interface.
- By submitting the form itself.

Calling `checkValidity()` is called *statically* validating the
constraints, while calling `reportValidity()` or submitting the form is
called *interactively* validating the constraints.

**Note:**

- If the [`novalidate`](element/form#novalidate) attribute is set on
    the [`<form>`](element/form) element, interactive validation of the
    constraints doesn\'t happen.
- Calling the `submit()` method on the
    [`HTMLFormElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement)
    interface doesn\'t trigger a constraint validation. In other words,
    this method sends the form data to the server even if it doesn\'t
    satisfy the constraints. Call the `click()` method on a submit
    button instead.

Complex constraints using the Constraint Validation API
-------------------------------------------------------

Using JavaScript and the Constraint API, it is possible to implement
more complex constraints, for example, constraints combining several
fields, or constraints involving complex calculations.

Basically, the idea is to trigger JavaScript on some form field event
(like **onchange**) to calculate whether the constraint is violated, and
then to use the method `field.setCustomValidity()` to set the result of
the validation: an empty string means the constraint is satisfied, and
any other string means there is an error and this string is the error
message to display to the user.

### Constraint combining several fields: Postal code validation

The postal code format varies from one country to another. Not only do
most countries allow an optional prefix with the country code (like `D-`
in Germany, `F-` in France or Switzerland), but some countries have
postal codes with only a fixed number of digits; others, like the UK,
have more complex structures, allowing letters at some specific
positions.

**Note:** This is not a comprehensive postal code validation library,
but rather a demonstration of the key concepts.

As an example, we will add a script checking the constraint validation
for this simple form:

[html]

```html
<form>
  <label for="ZIP">ZIP : </label>
  <input type="text" id="ZIP" />
  <label for="Country">Country : </label>
  <select id="Country">
    <option value="ch">Switzerland</option>
    <option value="fr">France</option>
    <option value="de">Germany</option>
    <option value="nl">The Netherlands</option>
  </select>
  <input type="submit" value="Validate" />
</form>
```

This displays the following form:

First, we write a function checking the constraint itself:

[js]

```js
function checkZIP() {
  // For each country, defines the pattern that the ZIP has to follow
  const constraints = {
    ch: [
      "^(CH-)?\\d{4}$",
      "Switzerland ZIPs must have exactly 4 digits: e.g. CH-1950 or 1950",
    ],
    fr: [
      "^(F-)?\\d{5}$",
      "France ZIPs must have exactly 5 digits: e.g. F-75012 or 75012",
    ],
    de: [
      "^(D-)?\\d{5}$",
      "Germany ZIPs must have exactly 5 digits: e.g. D-12345 or 12345",
    ],
    nl: [
      "^(NL-)?\\d{4}\\s*([A-RT-Z][A-Z]|S[BCE-RT-Z])$",
      "Netherland ZIPs must have exactly 4 digits, followed by 2 letters except SA, SD and SS",
    ],
  };

  // Read the country id
  const country = document.getElementById("Country").value;

  // Get the NPA field
  const ZIPField = document.getElementById("ZIP");

  // Build the constraint checker
  const constraint = new RegExp(constraints[country][0], "");
  console.log(constraint);

  // Check it!
  if (constraint.test(ZIPField.value)) {
    // The ZIP follows the constraint, we use the ConstraintAPI to tell it
    ZIPField.setCustomValidity("");
  } else {
    // The ZIP doesn't follow the constraint, we use the ConstraintAPI to
    // give a message about the format required for this country
    ZIPField.setCustomValidity(constraints[country][1]);
  }
}
```

Then we link it to the **onchange** event for the
[`<select>`](element/select) and the **oninput** event for the
[`<input>`](element/input):

[js]

```js
window.onload = () => {
  document.getElementById("Country").onchange = checkZIP;
  document.getElementById("ZIP").oninput = checkZIP;
};
```

### Limiting the size of a file before its upload

Another common constraint is to limit the size of a file to be uploaded.
Checking this on the client side before the file is transmitted to the
server requires combining the Constraint Validation API, and especially
the `field.setCustomValidity()` method, with another JavaScript API,
here the File API.

Here is the HTML part:

[html]

```html
<label for="FS">Select a file smaller than 75 kB : </label>
<input type="file" id="FS" />
```

This displays:

The JavaScript reads the file selected, uses the `File.size()` method to
get its size, compares it to the (hard coded) limit, and calls the
Constraint API to inform the browser if there is a violation:

[js]

```js
function checkFileSize() {
  const FS = document.getElementById("FS");
  const files = FS.files;

  // If there is (at least) one file selected
  if (files.length > 0) {
    if (files[0].size > 75 * 1024) {
      // Check the constraint
      FS.setCustomValidity("The selected file must not be larger than 75 kB");
      return;
    }
  }
  // No custom constraint violation
  FS.setCustomValidity("");
}
```

Finally, we hook the method with the correct event:

[js]

```js
window.onload = () => {
  document.getElementById("FS").onchange = checkFileSize;
};
```

Visual styling of constraint validation
---------------------------------------

Apart from setting constraints, web developers want to control what
messages are displayed to the users and how they are styled.

### Controlling the look of elements

The look of elements can be controlled via CSS pseudo-classes.

#### :required and :optional CSS pseudo-classes

The
[`:required`](https://developer.mozilla.org/en-US/docs/Web/CSS/:required)
and
[`:optional`](https://developer.mozilla.org/en-US/docs/Web/CSS/:optional)
[pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
allow writing selectors that match form elements that have the
[`required`](element/input#required) attribute, or that don\'t have it.

#### :placeholder-shown CSS pseudo-class

See
[`:placeholder-shown`](https://developer.mozilla.org/en-US/docs/Web/CSS/:placeholder-shown).

#### :valid :invalid CSS pseudo-classes

The [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid)
and
[`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)
[pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
are used to represent \<input\> elements whose content validates and
fails to validate respectively according to the input\'s type setting.
These classes allow the user to style valid or invalid form elements to
make it easier to identify elements that are either formatted correctly
or incorrectly.

### Controlling the text of constraint violation

The following items can help with controlling the text of a constraint
violation:

- The `setCustomValidity(message)` method on the following elements:
  - [`<fieldset>`](element/fieldset). Note: Setting a custom
        validity message on fieldset elements will not prevent form
        submission in most browsers.
  - [`<input>`](element/input)
  - [`<output>`](element/output)
  - [`<select>`](element/select)
  - Submit buttons (created with either a
        [`<button>`](element/button) element with the `submit` type, or
        an `input` element with the [submit](element/input/submit) type.
        Other types of buttons do not participate in constraint
        validation.
  - [`<textarea>`](element/textarea)
- The
    [`ValidityState`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState)
    interface describes the object returned by the `validity` property
    of the element types listed above. It represents various ways that
    an entered value can be invalid. Together, they help explain why an
    element\'s value fails to validate, if it\'s not valid.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Constraint_validation>>
