\<input type=\"number\"\>
=========================

[`<input>`](../input) elements of type `number` are used to let the user
enter a number. They include built-in validation to reject non-numerical
entries.

The browser may opt to provide stepper arrows to let the user increase
and decrease the value using their mouse or by tapping with a fingertip.

Try it
------

On browsers that don\'t support inputs of type `number`, a `number`
input falls back to type `text`.

Value
-----

A number representing the value of the number entered into the input.
You can set a default value for the input by including a number inside
the [`value`](../input#value) attribute, like so:

[html]

```html
<input id="number" type="number" value="42" />
```

Additional attributes
---------------------

In addition to the attributes commonly supported by all
[`<input>`](../input) types, inputs of type `number` support these
attributes.

### `list`

The values of the list attribute is the
[`id`](https://developer.mozilla.org/en-US/docs/Web/API/Element/id) of a
[`<datalist>`](../datalist) element located in the same document. The
[`<datalist>`](../datalist) provides a list of predefined values to
suggest to the user for this input. Any values in the list that are not
compatible with the [`type`](../input#type) are not included in the
suggested options. The values provided are suggestions, not
requirements: users can select from this predefined list or provide a
different value.

### `max`

The maximum value to accept for this input. If the
[`value`](../input#value) entered into the element exceeds this, the
element fails [constraint validation](../../constraint_validation). If
the value of the `max` attribute isn\'t a number, then the element has
no maximum value.

This value must be greater than or equal to the value of the `min`
attribute.

### `min`

The minimum value to accept for this input. If the
[`value`](../input#value) of the element is less than this, the element
fails [constraint validation](../../constraint_validation). If a value
is specified for `min` that isn\'t a valid number, the input has no
minimum value.

This value must be less than or equal to the value of the `max`
attribute.

### `placeholder`

The `placeholder` attribute is a string that provides a brief hint to
the user as to what kind of information is expected in the field. It
should be a word or short phrase that demonstrates the expected type of
data, rather than an explanatory message. The text *must not* include
carriage returns or line feeds.

If the control\'s content has one directionality
([LTR](https://developer.mozilla.org/en-US/docs/Glossary/LTR) or
[RTL](https://developer.mozilla.org/en-US/docs/Glossary/RTL)) but needs
to present the placeholder in the opposite directionality, you can use
Unicode bidirectional algorithm formatting characters to override
directionality within the placeholder; see [How to use Unicode controls
for bidi
text](https://www.w3.org/International/questions/qa-bidi-unicode-controls)
for more information.

**Note:** Avoid using the `placeholder` attribute if you can. It is not
as semantically useful as other ways to explain your form, and can cause
unexpected technical issues with your content. See [`<input>`
labels](../input#labels) for more information.

### `readonly`

A Boolean attribute which, if present, means this field cannot be edited
by the user. Its `value` can, however, still be changed by JavaScript
code directly setting the
[`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
`value` property.

**Note:** Because a read-only field cannot have a value, `required` does
not have any effect on inputs with the `readonly` attribute also
specified.

### `step`

The `step` attribute is a number that specifies the granularity that the
value must adhere to, or the special value `any`, which is described
below. Only values which are equal to the basis for stepping
([`min`](#min) if specified, [`value`](../input#value) otherwise, and an
appropriate default value if neither of those is provided) are valid.

A string value of `any` means that no stepping is implied, and any value
is allowed (barring other constraints, such as [`min`](#min) and
[`max`](#max)).

**Note:** When the data entered by the user doesn\'t adhere to the
stepping configuration, the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) may
round to the nearest valid value, preferring numbers in the positive
direction when there are two equally close options.

The default stepping value for `number` inputs is `1`, allowing only
integers to be entered---*unless* the stepping base is not an integer.

Using number inputs
-------------------

The `number` input type should only be used for incremental numbers,
especially when spinbutton incrementing and decrementing are helpful to
user experience. The `number` input type is not appropriate for values
that happen to only consist of numbers but aren\'t strictly speaking a
number, such as postal codes in many countries or credit card numbers.
For non-numeric inputs, consider using a different input type, such as
[`<input type="tel">`](tel) or other [`<input>`](../input) type with the
[`inputmode`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#inputmode) attribute:

[html]

```html
<input type="text" inputmode="numeric" pattern="\d*" />
```

`<input type="number">` elements can help simplify your work when
building the user interface and logic for entering numbers into a form.
When you create a number input with the proper `type` value, `number`,
you get automatic validation that the entered text is a number, and
usually a set of up and down buttons to step the value up and down.

**Warning:** Logically, you should not be able to enter characters
inside a number input other than numbers. Some browsers allow invalid
characters, others do not; see [Firefox bug
1398528](https://bugzil.la/1398528).

**Note:** A user can tinker with your HTML behind the scenes, so your
site *must not* use simple client-side validation for any security
purposes. You *must* verify on the server side any transaction in which
the provided value may have security implications of any kind.

Mobile browsers further help with the user experience by showing a
special keyboard more suited for entering numbers when the user tries to
enter a value.

### A simple number input

In its most basic form, a number input can be implemented like this:

[html]

```html
<label for="ticketNum">Number of tickets you would like to buy:</label>
<input id="ticketNum" type="number" name="ticketNum" value="0" />
```

A number input is considered valid when empty and when a single number
is entered, but is otherwise invalid. If the
[`required`](../input#required) attribute is used, the input is no
longer considered valid when empty.

**Note:** Any number is an acceptable value, as long as it is a [valid
floating point
number](https://html.spec.whatwg.org/multipage/infrastructure.html#valid-floating-point-number)
(that is, not
[NaN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN)
or
[Infinity](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity)).

### Placeholders

Sometimes it\'s helpful to offer an in-context hint as to what form the
input data should take. This can be especially important if the page
design doesn\'t offer descriptive labels for each [`<input>`](../input).
This is where **placeholders** come in. A placeholder is a value most
commonly used to provide a hint as to the format the input should take
`value`. It is displayed inside the edit box when the element\'s `value`
is `""`. Once data is entered into the box, the placeholder disappears;
if the box is emptied, the placeholder reappears.

Here, we have an `number` input with the placeholder
\"`Multiple of 10`\". Note how the placeholder disappears and reappears
as you manipulate the contents of the edit field.

[html]

```html
<input type="number" placeholder="Multiple of 10" />
```

### Controlling step size

By default, the up and down buttons provided for you to step the number
up and down will step the value up and down by 1. You can change this by
providing a [`step`](../input#step) attribute, which takes as its value
a number specifying the step amount. Our above example contains a
placeholder saying that the value should be a multiple of 10, so it
makes sense to add a `step` value of `10`:

[html]

```html
<input type="number" placeholder="multiple of 10" step="10" />
```

In this example, you should find that the up and down step arrows will
increase and decrease the value by 10 each time, not 1. You can still
manually enter a number that\'s not a multiple of 10, but it will be
considered invalid.

### Specifying minimum and maximum values

You can use the [`min`](../input#min) and [`max`](../input#max)
attributes to specify a minimum and maximum value that the field can
have. For example, let\'s give our example a minimum of `0`, and a
maximum of `100`:

[html]

```html
<input type="number" placeholder="multiple of 10" step="10" min="0" max="100" />
```

In this updated version, you should find that the up and down step
buttons will not allow you to go below 0 or above 100. You can still
manually enter a number outside these bounds, but it will be considered
invalid.

### Allowing decimal values

One issue with number inputs is that their step size is 1 by default. If
you try to enter a number with a decimal (such as \"1.0\"), it will be
considered invalid. If you want to enter a value that requires decimals,
you\'ll need to reflect this in the `step` value (e.g. `step="0.01"` to
allow decimals to two decimal places). Here\'s a simple example:

[html]

```html
<input type="number" placeholder="1.0" step="0.01" min="0" max="10" />
```

See that this example allows any value between `0.0` and `10.0`, with
decimals to two places. For example, \"9.52\" is valid, but \"9.521\" is
not.

### Controlling input size

[`<input>`](../input) elements of type `number` don\'t support form
sizing attributes such as [`size`](../input#size). You\'ll have to
resort to [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) to
change the size of these controls.

For example, to adjust the width of the input to be only as wide as is
needed to enter a three-digit number, we can change our HTML to include
an [`id`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#id) and to shorten our placeholder
since the field will be too narrow for the text we have been using so
far:

[html]

```html
<input
  type="number"
  placeholder="x10"
  step="10"
  min="0"
  max="100"
  id="number" />
```

Then we add some CSS to narrow the width of the element with the `id`
selector `#number`:

[css]

```css

# number {

  width: 3em;
}

```

The result looks like this:

### Offering suggested values

You can provide a list of default options from which the user can select
by specifying the [`list`](../input#list) attribute, which contains as
its value the [`id`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#id) of a
[`<datalist>`](../datalist), which in turn contains one
[`<option>`](../option) element per suggested value. Each `option`\'s
`value` is the corresponding suggested value for the number entry box.

[html]

```html
<input id="ticketNum" type="number" name="ticketNum" list="defaultNumbers" />
<span class="validity"></span>

<datalist id="defaultNumbers">
  <option value="10045678"></option>
  <option value="103421"></option>
  <option value="11111111"></option>
  <option value="12345678"></option>
  <option value="12999922"></option>
</datalist>
```

Validation
----------

We have already mentioned a number of validation features of `number`
inputs, but let\'s review them now:

- `<input type="number">` elements automatically invalidate any entry
    that isn\'t a number (or empty, unless `required` is specified).
- You can use the [`required`](../input#required) attribute to make an
    empty entry invalid. (In other words, the input *must* be filled
    in.)
- You can use the [`step`](../input#step) attribute to constrain valid
    values to a certain set of steps (e.g., multiples of 10).
- You can use the [`min`](../input#min) and [`max`](../input#max)
    attributes to constrain valid values to lower and upper bounds.

The following example exhibits all of the above features, as well as
using some CSS to display valid and invalid icons, depending on the
`input`\'s value:

[html]

```html
<form>
  <div>
    <label for="balloons">Number of balloons to order (multiples of 10):</label>
    <input
      id="balloons"
      type="number"
      name="balloons"
      step="10"
      min="0"
      max="100"
      required />
    <span class="validity"></span>
  </div>
  <div>
    <input type="submit" />
  </div>
</form>
```

Try submitting the form with different invalid values entered --- e.g.,
no value; a value below 0 or above 100; a value that is not a multiple
of 10; or a non-numerical value --- and see how the error messages the
browser gives you differ with different ones.

The CSS applied to this example is as follows:

[css]

```css
div {
  margin-bottom: 10px;
}

input:invalid + span::after {
  content: "✖";
  padding-left: 5px;
}

input:valid + span::after {
  content: "✓";
  padding-left: 5px;
}

```

Here we use the
[`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)
and [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid)
pseudo classes to display an appropriate invalid or valid icon as
generated content on the adjacent [`<span>`](../span) element, as a
visual indicator of validity.

We put it on a separate `<span>` element for added flexibility. Some
browsers don\'t display generated content very effectively on some types
of form inputs. (Read, for example, the section on
[`<input type="date">` validation](date#validation).)

**Warning:** HTML form validation is *not* a substitute for server-side
scripts that ensure that the entered data is in the proper format!

It\'s far too easy for someone to make adjustments to the HTML that
allow them to bypass the validation, or to remove it entirely. It\'s
also possible for someone to bypass your HTML and submit the data
directly to your server.

If your server-side code fails to validate the data it receives,
disaster could strike when improperly-formatted data is submitted (or
data which is too large, is of the wrong type, and so forth).

### Pattern validation

`<input type="number">` elements do not support use of the
[`pattern`](../input#pattern) attribute for making entered values
conform to a specific regex pattern.

The rationale for this is that number inputs won\'t be valid if they
contain anything except numbers, and you can constrain the minimum and
maximum number of valid digits using the [`min`](../input#min) and
[`max`](../input#max) attributes (as explained above).

Examples
--------

We\'ve already covered the fact that by default, the increment is `1`,
and you can use the [`step`](../input#step) attribute to allow decimal
inputs. Let\'s take a closer look.

In the following example is a form for entering the user\'s height. It
defaults to accepting a height in meters, but you can click the relevant
button to change the form to accept feet and inches instead. The input
for the height in meters accepts decimals to two places.

The HTML looks like this:

[html]

```html
<form>
  <div class="metersInputGroup">
    <label for="meters">Enter your height — meters:</label>
    <input
      id="meters"
      type="number"
      name="meters"
      step="0.01"
      min="0"
      placeholder="e.g. 1.78"
      required />
    <span class="validity"></span>
  </div>
  <div class="feetInputGroup" style="display: none;">
    <span>Enter your height — </span>
    <label for="feet">feet:</label>
    <input id="feet" type="number" name="feet" min="0" step="1" />
    <span class="validity"></span>
    <label for="inches">inches:</label>
    <input id="inches" type="number" name="inches" min="0" max="11" step="1" />
    <span class="validity"></span>
  </div>
  <div>
    <input
      type="button"
      class="meters"
      value="Enter height in feet and inches" />
  </div>
  <div>
    <input type="submit" value="Submit form" />
  </div>
</form>
```

You\'ll see that we are using many of the attributes we\'ve already
looked at in the article earlier on. Since we want to accept a meter
value in centimeters, we\'ve set the `step` value to `0.01`, so that
values like *1.78* are not seen as invalid. We\'ve also provided a
placeholder for that input.

We\'ve hidden the feet and inches inputs initially using
`style="display: none;"`, so that meters is the default entry type.

Now, onto the CSS. This looks very similar to the validation styling we
saw before; nothing remarkable here.

[css]

```css
div {
  margin-bottom: 10px;
  position: relative;
}

input[type="number"] {
  width: 100px;
}

input + span {
  padding-right: 30px;
}

input:invalid + span::after {
  position: absolute;
  content: "✖";
  padding-left: 5px;
}

input:valid + span::after {
  position: absolute;
  content: "✓";
  padding-left: 5px;
}

```

And finally, the JavaScript:

[js]

```js
const metersInputGroup = document.querySelector(".metersInputGroup");
const feetInputGroup = document.querySelector(".feetInputGroup");
const metersInput = document.querySelector("#meters");
const feetInput = document.querySelector("#feet");
const inchesInput = document.querySelector("#inches");
const switchBtn = document.querySelector('input[type="button"]');

switchBtn.addEventListener("click", () => {
  if (switchBtn.getAttribute("class") === "meters") {
    switchBtn.setAttribute("class", "feet");
    switchBtn.value = "Enter height in meters";

    metersInputGroup.style.display = "none";
    feetInputGroup.style.display = "block";

    feetInput.setAttribute("required", "");
    inchesInput.setAttribute("required", "");
    metersInput.removeAttribute("required");

    metersInput.value = "";
  } else {
    switchBtn.setAttribute("class", "meters");
    switchBtn.value = "Enter height in feet and inches";

    metersInputGroup.style.display = "block";
    feetInputGroup.style.display = "none";

    feetInput.removeAttribute("required");
    inchesInput.removeAttribute("required");
    metersInput.setAttribute("required", "");

    feetInput.value = "";
    inchesInput.value = "";
  }
});
```

After declaring a few variables, an event listener is added to the
`button` to control the switching mechanism. This is pretty simple,
mostly involving changing over the button\'s `class` and
[`<label>`](../label), and updating the display values of the two sets
of inputs when the button is pressed.

(Note that we\'re not converting back and forth between meters and
feet/inches here, which a real-life web application would probably do.)

**Note:** When the user clicks the button, the `required` attribute(s)
are removed from the input(s) we are hiding, and empty the `value`
attribute(s). This is so the form can be submitted if both input sets
aren\'t filled in. It also ensures that the form won\'t submit data that
the user didn\'t mean to.

If you didn\'t do this, you\'d have to fill in both feet/inches **and**
meters to submit the form!

Accessibility
-------------

The implicit
[role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles)
for the `<input type="number">` element is
[`spinbutton`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/spinbutton_role).
If spinbutton is not an important feature for your form control,
consider *not* using `type="number"`. Instead, use
[`inputmode="numeric"`](../../global_attributes/inputmode) along with a
[`pattern`](../../attributes/pattern) attribute that limits the
characters to numbers and associated characters. With
`<input type="number">`, there is a risk of users accidentally
incrementing a number when they\'re trying to do something else.
Additionally, if users try to enter something that\'s not a number,
there\'s no explicit feedback about what they\'re doing wrong.

Also consider using the [`autocomplete`](../../attributes/autocomplete)
attribute to help users complete forms more quickly and with fewer
chances of errors. For example, to enable autofill on a zip code field,
set `autocomplete="postal-code"`.

Technical summary
-----------------

  --------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **[Value](#value)**               A [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing a number, or empty
  **Events**                        [`change`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event) and [`input`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event)
  **Supported common attributes**   [`autocomplete`](../input#autocomplete), [`list`](../input#list), [`placeholder`](../input#placeholder), [`readonly`](../input#readonly)
  **IDL attributes**                `list`, `value`, `valueAsNumber`
  **DOM interface**                 [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
  **Methods**                       [`select()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select), [`stepUp()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepUp), [`stepDown()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepDown)
  **Implicit ARIA Role**            `spinbutton`
  --------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  --------------------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  number-state-(type=number)]](https://html.spec.whatwg.org/multipage/input.html#number-state-(type=number))

  --------------------------------------------------------------------------------------------------------------------

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

`number`

7

12

29

10

15

5.1

4.4

18

29

14

5

1.0

See also
--------

- [HTML forms
    guide](https://developer.mozilla.org/en-US/docs/Learn/Forms)
- [`<input>`](../input)
- [`<input type="tel">`](tel)
- [Compatibility of CSS
    properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)
- [Article: Why Gov.UK changed the input type for
    numbers](https://technology.blog.gov.uk/2020/02/24/why-the-gov-uk-design-system-team-changed-the-input-type-for-numbers/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/number>>
