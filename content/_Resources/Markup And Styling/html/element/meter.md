\<meter\>: The HTML Meter element
=================================

The `<meter>` [HTML](../index) element represents either a scalar value
within a known range or a fractional value.

Try it
------

  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), labelable content, palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content), but there must be no `<meter>` element among its descendants.
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            `meter`
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLMeterElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMeterElement)
  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`value`](#value)

:   The current numeric value. This must be between the minimum and
    maximum values (`min` attribute and `max` attribute) if they are
    specified. If unspecified or malformed, the value is `0`. If
    specified, but not within the range given by the `min` attribute and
    `max` attribute, the value is equal to the nearest end of the range.

    **Note:** Unless the `value` attribute is between `0` and `1`
    (inclusive), the `min` and `max` attributes should define the range
    so that the `value` attribute\'s value is within it.

[`min`](#min)

:   The lower numeric bound of the measured range. This must be less
    than the maximum value (`max` attribute), if specified. If
    unspecified, the minimum value is `0`.

[`max`](#max)

:   The upper numeric bound of the measured range. This must be greater
    than the minimum value (`min` attribute), if specified. If
    unspecified, the maximum value is `1`.

[`low`](#low)

:   The upper numeric bound of the low end of the measured range. This
    must be greater than the minimum value (`min` attribute), and it
    also must be less than the high value and maximum value (`high`
    attribute and `max` attribute, respectively), if any are specified.
    If unspecified, or if less than the minimum value, the `low` value
    is equal to the minimum value.

[`high`](#high)

:   The lower numeric bound of the high end of the measured range. This
    must be less than the maximum value (`max` attribute), and it also
    must be greater than the low value and minimum value (`low`
    attribute and `min` attribute, respectively), if any are specified.
    If unspecified, or if greater than the maximum value, the `high`
    value is equal to the maximum value.

[`optimum`](#optimum)

:   This attribute indicates the optimal numeric value. It must be
    within the range (as defined by the `min` attribute and `max`
    attribute). When used with the `low` attribute and `high` attribute,
    it gives an indication where along the range is considered
    preferable. For example, if it is between the `min` attribute and
    the `low` attribute, then the lower range is considered preferred.
    The browser may color the meter\'s bar differently depending on
    whether the value is less than or equal to the optimum value.

[`form`](#form)

:   This optional attribute is used to explicitly set a [`<form>`](form)
    owner for the `<meter>` element. If omitted, the `<meter>` is
    associated with its ancestor `<form>` element or the form
    association set by the `form` attribute on another ancestor element,
    such as on a [`<fieldset>`](fieldset), if any. If included, the
    value must be the [`id`](../global_attributes/id) of a `<form>` in
    the same tree.

Examples
--------

### Simple example

#### HTML

[html]

```html
<p>
  Heat the oven to <meter min="200" max="500" value="350">350 degrees</meter>.
</p>
```

#### Result

On Google Chrome, the resulting meter looks like this:

![A screenshot of the meter element in Google
Chrome]

### High and Low range example

Note that in this example the [`min`](#min) attribute is omitted. This
is allowed, as it will default to `0`.

#### HTML

[html]

```html
<p>
  He got a <meter low="69" high="80" max="100" value="84">B</meter> on the exam.
</p>
```

#### Result

On Google Chrome, the resulting meter looks like this:

![red meter in Google
Chrome]

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-meter-element]](https://html.spec.whatwg.org/multipage/form-elements.html#the-meter-element)

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

`meter`

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

`form`

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

`high`

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

`low`

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

`optimum`

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

`value`

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

See also
--------

- [`<progress>`](progress)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meter>>
