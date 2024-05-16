HTML attribute: step
====================

The `step` attribute is a number that specifies the granularity that the
value must adhere to or the keyword `any`. It is valid for the numeric
input types, including the [date](../element/input/date),
[month](../element/input/month), [week](../element/input/week),
[time](../element/input/time),
[datetime-local](../element/input/datetime-local),
[number](../element/input/number) and [range](../element/input/range)
types.

The `step` sets the *stepping interval* when clicking up and down
spinner buttons, moving a slider left and right on a range, and
validating the different date types. If not explicitly included, `step`
defaults to 1 for `number` and `range`, and 1 unit type (minute, week,
month, day) for the date/time input types. The value can must be a
positive number - integer or float --- or the special value `any`, which
means no stepping is implied, and any value is allowed (barring other
constraints, such as [`min`](min) and [`max`](max)).

The default stepping value for `number` inputs is 1, allowing only
integers to be entered, *unless* the stepping base is not an integer.
The default stepping value for `time` is 1 second, with 900 being equal
to 15 minutes.

Syntax
------

  Input type                                          Value          Example
  --------------------------------------------------- -------------- -----------------------------------------------------------------
  [date](../element/input/date)                       1 (day)        `<input type="date" min="2019-12-25" step="1">`
  [month](../element/input/month)                     1 (month)      `<input type="month" min="2019-12" step="12">`
  [week](../element/input/week)                       1 (week)       `<input type="week" min="2019-W23" step="2">`
  [time](../element/input/time)                       60 (seconds)   `<input type="time" min="09:00" step="900">`
  [datetime-local](../element/input/datetime-local)   1 (second)     `<input type="datetime-local" min="2019-12-25T19:30" step="7">`
  [number](../element/input/number)                   1              `<input type="number" min="0" step="0.1" max="10">`
  [range](../element/input/range)                     1              `<input type="range" min="0" step="2" max="10">`

  : Default values for step

If `any` is not explicitly set, valid values for the `number`, date/time
input types, and `range` input types are equal to the basis for stepping

- the [`min`](min) value and increments of the step value, up to the
[`max`](max) value, if specified. For example, if we have
`<input type="number" min="10" step="2">` any even integer, 10 or
greater, is valid. If omitted, `<input type="number">`, any integer is
valid, but floats, like 4.2, are not valid, as `step` defaults to 1. For
4.2 to be valid, `step` would have had to be set to `any`, 0.1, 0.2, or
any the min value would have had to be a number ending in .2, such as
`<input type="number" min="-5.2">`

### min impact on step

The value of `min` and `step` define what are valid values, even if the
`step` attribute is not included, as `step` defaults to `0`.

We add a big red border around invalid inputs:

[css]

```css
input:invalid {
  border: solid red 3px;
}

```

Then define an input with a minimum value of 7.2, omitting the step
attribute, wherein it defaults to 1.

[html]

```html
<input id="myNumber" name="myNumber" type="number" step="2" min="1.2" />
```

Valid values include `1.2`, `3.2`, `5.2`, `7.2`, `9.2`, `11.2`, and so
on. Integers and even numbers followed by .2 are not valid. As we
included an invalid value, supporting browsers will show the value as
invalid. The number spinner, if present, will only show valid float
values of `1.2` and greater

**Note:** When the data entered by the user doesn\'t adhere to the
stepping configuration, the value is considered invalid in constraint
validation and will match the
[`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)
and
[`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)
pseudoclasses

See [Client-side validation](../constraint_validation) and
[`stepMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/stepMismatch)
for more information.

Accessibility concerns
----------------------

Provide instructions to help users understand how to complete the form
and use individual form controls. Indicate any required and optional
input, data formats, and other relevant information. When using the
`min` attribute, ensure this minimum requirement is understood by the
user. Providing instructions within the [`<label>`](../element/label)
may be sufficient. If providing instructions outside of labels, which
allows more flexible positioning and design, consider using
[`aria-labelledby`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-labelledby)
or
[`aria-describedby`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-describedby).

Specifications
--------------

  ----------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  attr-input-step]](https://html.spec.whatwg.org/multipage/input.html#attr-input-step)

  ----------------------------------------------------------------------------------------------

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

`step`

5

12

16

10

≤12.1

5

≤37

18

16

≤12.1

4

1.0

See also
--------

- [`max`](max)
- [`min`](min)
- [Constraint validation](../constraint_validation)
- [Form
    validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)
- [`validityState.stepMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/stepMismatch)
- [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)
- [`<input>`](../element/input)
- [date](../element/input/date), [month](../element/input/month),
    [week](../element/input/week), [time](../element/input/time),
    [datetime-local](../element/input/datetime-local),
    [number](../element/input/number) and
    [range](../element/input/range) types, and the
    [`<meter>`](../element/meter)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/step>>
