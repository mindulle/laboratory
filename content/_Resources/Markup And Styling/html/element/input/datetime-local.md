\<input type=\"datetime-local\"\>
=================================

[`<input>`](../input) elements of type `datetime-local` create input
controls that let the user easily enter both a date and a time,
including the year, month, and day as well as the time in hours and
minutes.

Try it
------

The control\'s UI varies in general from browser to browser. In browsers
with no support, these degrade gracefully to simple
[`<input type="text">`](text) controls.

The control is intended to represent *a local date and time*, not
necessarily *the user\'s local date and time*. In other words, the input
allows any valid combination of year, month, day, hour, and
minute---even if such a combination is invalid in the user\'s local time
zone (such as the one hour within a daylight saving time spring-forward
transition gap).

Value
-----

A string representing the value of the date entered into the input. The
format of the date and time value used by this input type is described
in [Local date and time
strings](../../date_and_time_formats#local_date_and_time_strings).

You can set a default value for the input by including a date and time
inside the [`value`](../input#value) attribute, like so:

[html]

```html
<label for="party">Enter a date and time for your party booking:</label>
<input
  id="party"
  type="datetime-local"
  name="partydate"
  value="2017-06-01T08:30" />
```

One thing to note is that the displayed date and time formats differ
from the actual `value`; the displayed date and time are formatted
according to the user\'s locale as reported by their operating system,
whereas the date/time `value` is always formatted `YYYY-MM-DDThh:mm`.
When the above value is submitted to the server, for example, it will
look like `partydate=2024-06-01T08:30`.

**Note:** Also bear in mind that if such data is submitted via HTTP
[`GET`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET),
the colon character will need to be escaped for inclusion in the URL
parameters, e.g. `partydate=2024-06-01T08%3A30`. See
[`encodeURI()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURI)
for one way to do this.

You can also get and set the date value in JavaScript using the
[`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
`value` property, for example:

[js]

```js
const dateControl = document.querySelector('input[type="datetime-local"]');
dateControl.value = "2017-06-01T08:30";
```

Additional attributes
---------------------

In addition to the attributes common to all [`<input>`](../input)
elements, `datetime-local` inputs offer the following attributes.

### max

The latest date and time to accept. If the [`value`](../input#value)
entered into the element is later than this timestamp, the element fails
[constraint validation](../../constraint_validation). If the value of
the `max` attribute isn\'t a valid string that follows the format
`YYYY-MM-DDThh:mm`, then the element has no maximum value.

This value must specify a date string later than or equal to the one
specified by the `min` attribute.

### min

The earliest date and time to accept; timestamps earlier than this will
cause the element to fail [constraint
validation](../../constraint_validation). If the value of the `min`
attribute isn\'t a valid string that follows the format
`YYYY-MM-DDThh:mm`, then the element has no minimum value.

This value must specify a date string earlier than or equal to the one
specified by the `max` attribute.

### step

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

For `datetime-local` inputs, the value of `step` is given in seconds,
with a scaling factor of 1000 (since the underlying numeric value is in
milliseconds). The default value of `step` is 60, indicating 60 seconds
(or 1 minute, or 60,000 milliseconds).

*At this time, it\'s unclear what a value of `any` means for `step` when
used with `datetime-local` inputs. This will be updated as soon as that
information is determined.*

Using datetime-local inputs
---------------------------

Date/time inputs are convenient for the developer; they provide an easy
UI for choosing dates and times, and they normalize the data format sent
to the server, regardless of the user\'s locale. However, it is
important to consider your users. Don\'t require your users to enter
data that is not needed for your app to function.

### Controlling input size

`<input type="datetime-local">` doesn\'t support form control sizing
attributes such as [`size`](../input#size). You\'ll have to resort to
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) for customizing
the sizes of these elements.

### Setting timezones

One thing the `datetime-local` input type doesn\'t provide is a way to
set the time zone and/or locale of the date/time control. This was
available in the `datetime` input type, but this type is now obsolete,
having been removed from the spec. The main reasons why this was removed
are a lack of implementation in browsers and concerns over the user
interface/experience. It is easier to just have a control (or controls)
for setting the date/time and then deal with the locale in a separate
control.

For example, if you are creating a system where the user is likely to
already be logged in, with their locale already set, you could provide
the timezone in a [`hidden`](hidden) input type. For example:

[html]

```html
<input type="hidden" id="timezone" name="timezone" value="-08:00" />
```

On the other hand, if you were required to allow the user to enter a
time zone along with a date/time input, you could have a
[`<select>`](../select) element to enable the user to set the right time
zone by choosing a particular location from among a set of locations:

[html]

```html
<select name="timezone" id="timezone">
  <option value="Pacific/Kwajalein">Eniwetok, Kwajalein</option>
  <option value="Pacific/Midway">Midway Island, Samoa</option>
  <option value="Pacific/Honolulu">Hawaii</option>
  <option value="Pacific/Marquesas">Taiohae</option>
  <!-- and so on -->
</select>
```

In either case, the date/time and time zone values would be submitted to
the server as separate data points, and then you\'d need to store them
appropriately in the database on the server-side.

Validation
----------

By default, `<input type="datetime-local">` does not apply any
validation to entered values. The UI implementations generally don\'t
let you enter anything that isn\'t a date/time --- which is helpful ---
but a user might still fill in no value and submit, or enter an invalid
date and/or time (e.g. the 32nd of April).

You can use [`min`](../input#min) and [`max`](../input#max) to restrict
the available dates (see [Setting maximum and minimum
dates](#setting_maximum_and_minimum_dates)), and you can use the
[`required`](../input#required) attribute to make filling in the
date/time mandatory. As a result, supporting browsers will display an
error if you try to submit a date that is outside the set bounds or an
empty date field.

Let\'s look at an example; here we\'ve set minimum and maximum date/time
values, and also made the field required:

[html]

```html
<form>
  <div>
    <label for="party">
      Choose your preferred party date and time (required, June 1st 8.30am to
      June 30th 4.30pm):
    </label>
    <input
      id="party"
      type="datetime-local"
      name="partydate"
      min="2017-06-01T08:30"
      max="2017-06-30T16:30"
      required />
    <span class="validity"></span>
  </div>
  <div>
    <input type="submit" value="Book party!" />
  </div>
</form>
```

If you try to submit the form with an incomplete date (or with a date
outside the set bounds), the browser displays an error. Try playing with
the example now:

Here\'s the CSS used in the above example. Here we make use of the
[`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid) and
[`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)
CSS properties to style the input based on whether the current value is
valid. We put the icons on a [`<span>`](../span) next to the input.

[css]

```css
div {
  margin-bottom: 10px;
  display: flex;
  align-items: center;
}

label {
  display: inline-block;
  width: 300px;
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

**Warning:** HTML form validation is *not* a substitute for scripts that
ensure that the entered data is in the proper format. It\'s far too easy
for someone to make adjustments to the HTML that allow them to bypass
the validation, or to remove it entirely. It\'s also possible for
someone to bypass your HTML entirely and submit the data directly to
your server. If your server-side code fails to validate the data it
receives, problems can arise when improperly-formatted data is submitted
(or data that is too large, is of the wrong type, and so forth).

**Note:** With a `datetime-local` input, the date value is always
normalized to the format `YYYY-MM-DDThh:mm`.

Examples
--------

### Basic uses of datetime-local

The simplest use of `<input type="datetime-local">` involves a basic
`<input>` and [`<label>`](../label) element combination, as seen below:

[html]

```html
<form>
  <label for="party">Enter a date and time for your party booking:</label>
  <input id="party" type="datetime-local" name="partydate" />
</form>
```

### Setting maximum and minimum dates and times

You can use the [`min`](../input#min) and [`max`](../input#max)
attributes to restrict the dates/times that can be chosen by the user.
In the following example, we are setting a minimum datetime of
`2024-06-01T08:30` and a maximum datetime of `2024-06-30T16:30`:

[html]

```html
<form>
  <label for="party">Enter a date and time for your party booking:</label>
  <input
    id="party"
    type="datetime-local"
    name="partydate"
    min="2024-06-01T08:30"
    max="2024-06-30T16:30" />
</form>
```

Only days in June 2024 can be selected. Depending on what browser you
are using, times outside the specified values might not be selectable.
In other browsers, invalid dates and times are selectable but will match
[`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)
and
[`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)
and will fail [validation](#validation).

In some browsers (Chrome and Edge), only the \"days\" part of the date
value will be editable, and dates outside June can\'t be scrolled. In
others (Safari), the date picker will appear to allow any date, but the
value will be clamped to the valid range when a date is selected.

The valid range included all times between the `min` and `max` values;
the time of day is only constrained on the first and last dates in the
range.

**Note:** You should be able to use the [`step`](../input#step)
attribute to vary the number of days jumped each time the date is
incremented (e.g. maybe you only want to make Saturdays selectable).
However, this does not seem to work effectively in any implementation at
the time of writing.

Technical summary
-----------------

  --------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **[Value](#value)**               A string representing a date and time (in the local time zone), or empty.
  **Events**                        [`change`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event) and [`input`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event)
  **Supported common attributes**   [`autocomplete`](../input#autocomplete), [`list`](../input#list), [`readonly`](../input#readonly), and [`step`](../input#step)
  **IDL attributes**                `list`, `value`, `valueAsNumber`.
  **DOM interface**                 [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
  **Methods**                       [`select()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select), [`stepDown()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepDown), [`stepUp()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepUp)
  **Implicit ARIA Role**            [`no corresponding role`](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  --------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  --------------------------------------------------------------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  local-date-and-time-state-(type=datetime-local)]](https://html.spec.whatwg.org/multipage/input.html#local-date-and-time-state-(type=datetime-local))

  --------------------------------------------------------------------------------------------------------------------------------------------------------------

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

`datetime-local`

20

12

93

No

11

14.1

4.4

25

93

11

5

1.5

See also
--------

- The generic [`<input>`](../input) element and the interface used to
    manipulate it,
    [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
- [`<input type="date">`](date) and [`<input type="time">`](time)
- [Date and time formats used in HTML](../../date_and_time_formats)
- [Date and Time picker
    tutorial](https://developer.mozilla.org/en-US/docs/Learn/Forms/Basic_native_form_controls#date_and_time_picker)
- [Compatibility of CSS
    properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/datetime-local>>
