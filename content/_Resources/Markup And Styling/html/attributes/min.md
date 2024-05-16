HTML attribute: min
===================

The `min` attribute defines the minimum value that is acceptable and
valid for the input containing the attribute. If the
[`value`](../element/input#value) of the element is less than this, the
element fails
[validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation).
This value must be less than or equal to the value of the `max`
attribute.

Some input types have a default minimum. If the input has no default
minimum and a value is specified for `min` that can\'t be converted to a
valid number (or no minimum value is set), the input has no minimum
value.

It is valid for the input types including:
[date](../element/input/date), [month](../element/input/month),
[week](../element/input/week), [time](../element/input/time),
[datetime-local](../element/input/datetime-local),
[number](../element/input/number) and [range](../element/input/range)
types, and the [`<meter>`](../element/meter) element.

### Syntax

  Input type                                          Syntax                                                                  Example
  --------------------------------------------------- ----------------------------------------------------------------------- --------------------------------------------------------
  [date](../element/input/date)                       `yyyy-mm-dd`                                                            `<input type="date" min="2019-12-25" step="1">`
  [month](../element/input/month)                     `yyyy-mm`                                                               `<input type="month" min="2019-12" step="12">`
  [week](../element/input/week)                       `yyyy-W##`                                                              `<input type="week" min="2019-W23" step="">`
  [time](../element/input/time)                       `hh:mm`                                                                 `<input type="time" min="09:00" step="900">`
  [datetime-local](../element/input/datetime-local)   `yyyy-mm-ddThh:mm`                                                      `<input type="datetime-local" min="2019-12-25T19:30">`
  [number](../element/input/number)                   [\<number\>](https://developer.mozilla.org/en-US/docs/Web/CSS/number)   `<input type="number" min="0" step="5" max="100">`
  [range](../element/input/range)                     [\<number\>](https://developer.mozilla.org/en-US/docs/Web/CSS/number)   `<input type="range" min="60" step="5" max="100">`

  :  Syntax for `min` values by input `type`

**Note:** When the data entered by the user doesn\'t adhere to the min
value set, the value is considered invalid in constraint validation and
will match the
[`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)
and
[`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)
pseudo-classes.

See [Client-side validation](../constraint_validation) and
[`rangeUnderflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeUnderflow)
for more information.

For the [`<meter>`](../element/meter) element, the `min` attribute
defines the lower numeric bound of the measured range. This must be less
than the minimum value ([`max`](max) attribute), if specified. In both
cases, if omitted, the value defaults to 1.

  Input type                      Syntax                                                                  Example
  ------------------------------- ----------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------
  [`<meter>`](../element/meter)   [\<number\>](https://developer.mozilla.org/en-US/docs/Web/CSS/number)   `<meter id="fuel" min="0" max="100" low="33" high="66" optimum="80" value="40"> at 40/100</meter>`

  :  Syntax for `min` values for other elements

### Impact on step

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
<input id="myNumber" name="myNumber" type="number" min="7.2" value="8" />
```

Because `step` defaults to 1, valid values include `7.2`, `8.2`, `9.2`,
and so on. The value 8 is not valid. As we included an invalid value,
supporting browsers will show the value as invalid.

If not explicitly included, `step` defaults to 1 for `number` and
`range`, and 1 unit type (second, week, month, day) for the date/time
input types.

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

  --------------------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-min-and-max-attributes]](https://html.spec.whatwg.org/multipage/input.html#the-min-and-max-attributes)

[HTML Standard\
  [\# attr-meter-max]](https://html.spec.whatwg.org/multipage/form-elements.html#attr-meter-max)
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

`min`

6

≤18

16

No

11

6

No

18

16

11

10.3

1.0

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

`min`

4

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

### html.elements.input.min

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### html.elements.meter.min

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

See also
--------

- [`step`](step)
- [`max`](max)
- other meter attributes:
    [`low`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/low),
    [`high`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/high),
    [`optimum`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/optimum)
- [Constraint validation](../constraint_validation)
- [Form
    validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)
- [`validityState.rangeUnderflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeUnderflow)
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
https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/min>>
