HTML attribute: max
===================

The `max` attribute defines the maximum value that is acceptable and
valid for the input containing the attribute. If the
[`value`](../element/input#value) of the element is greater than this,
the element fails
[validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation).
This value must be greater than or equal to the value of the
[`min`](min) attribute. If the `max` attribute is present but is not
specified or is invalid, no `max` value is applied. If the `max`
attribute is valid and a non-empty value is greater than the maximum
allowed by the `max` attribute, constraint validation will prevent form
submission.

Valid for the numeric input types, including the
[date](../element/input/date), [month](../element/input/month),
[week](../element/input/week), [time](../element/input/time),
[datetime-local](../element/input/datetime-local),
[number](../element/input/number) and [range](../element/input/range)
types, and both the [`<progress>`](../element/progress) and
[`<meter>`](../element/meter) elements, the `max` attribute is a number
that specifies the most positive value a form control to be considered
valid.

If the value exceeds the max value allowed, the
[`validityState.rangeOverflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeOverflow)
will be true, and the control will be matched by the
[`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)
and
[`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)
pseudo-classes.

### Syntax

  Input type                                          Syntax                                                                  Example
  --------------------------------------------------- ----------------------------------------------------------------------- --------------------------------------------------------
  [date](../element/input/date)                       `yyyy-mm-dd`                                                            `<input type="date" max="2019-12-25" step="1">`
  [month](../element/input/month)                     `yyyy-mm`                                                               `<input type="month" max="2019-12" step="12">`
  [week](../element/input/week)                       `yyyy-W##`                                                              `<input type="week" max="2019-W23" step="">`
  [time](../element/input/time)                       `hh:mm`                                                                 `<input type="time" max="17:00" step="900">`
  [datetime-local](../element/input/datetime-local)   `yyyy-mm-ddThh:mm`                                                      `<input type="datetime-local" max="2019-12-25T23:59">`
  [number](../element/input/number)                   [\<number\>](https://developer.mozilla.org/en-US/docs/Web/CSS/number)   `<input type="number" min="0" step="5" max="100">`
  [range](../element/input/range)                     [\<number\>](https://developer.mozilla.org/en-US/docs/Web/CSS/number)   `<input type="range" min="60" step="5" max="100">`

  :  Syntax for `max` values by input `type`

**Note:** When the data entered by the user doesn\'t adhere to the
maximum value set, the value is considered invalid in constraint
validation and will match the
[`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)
and
[`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)
pseudo-classes.

See [Client-side validation](../constraint_validation) and
[`rangeOverflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeOverflow)
for more information.

For the [`<progress>`](../element/progress) element, the `max` attribute
describes how much work the task indicated by the `progress` element
requires. If present, must have a value greater than zero and be a valid
floating point number. For the [`<meter>`](../element/meter) element,
the `max` attribute defines the upper numeric bound of the measured
range. This must be greater than the minimum value ([`min`](min)
attribute), if specified. In both cases, if omitted, the value defaults
to 1.

  Input type                            Syntax                                                                  Example
  ------------------------------------- ----------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------
  [`<progress>`](../element/progress)   [\<number\>](https://developer.mozilla.org/en-US/docs/Web/CSS/number)   `<progress id="file" max="100" value="70"> 70% </progress>`
  [`<meter>`](../element/meter)         [\<number\>](https://developer.mozilla.org/en-US/docs/Web/CSS/number)   `<meter id="fuel" min="0" max="100" low="33" high="66" optimum="80" value="40"> at 40/100</meter>`

  :  Syntax for `max` values for other elements

Accessibility concerns
----------------------

Provide instructions to help users understand how to complete the form
and use individual form controls. Indicate any required and optional
input, data formats, and other relevant information. When using the
`max` attribute, ensure this maximum requirement is understood by the
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

[HTML Standard\
  [\# attr-progress-max]](https://html.spec.whatwg.org/multipage/form-elements.html#attr-progress-max)
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

`max`

6

12

6

10

11

6

4.4

18

6

11

7

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

`max`

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

`max`

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

### html.elements.input.max

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### html.elements.meter.max

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### html.elements.progress.max

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

See also
--------

- [`step`](step)
- [`min`](min)
- other meter attributes:
    [`low`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/low),
    [`high`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/high),
    [`optimum`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/optimum)
- [Constraint validation](../constraint_validation)
- [Form
    validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)
- [`validityState.rangeOverflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeOverflow)
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
https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/max>>
