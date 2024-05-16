\<time\>: The (Date) Time element
=================================

The `<time>` [HTML](../index) element represents a specific period in
time. It may include the `datetime` attribute to translate dates into
machine-readable format, allowing for better search engine results or
custom features such as reminders.

It may represent one of the following:

- A time on a 24-hour clock.
- A precise date in the [Gregorian
    calendar](https://en.wikipedia.org/wiki/Gregorian_calendar) (with
    optional time and timezone information).
- [A valid time
    duration](https://html.spec.whatwg.org/multipage/common-microsyntaxes.html#valid-duration-string).

Try it
------

Attributes
----------

Like all other HTML elements, this element supports the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`datetime`](#datetime)

:   This attribute indicates the time and/or date of the element and
    must be in one of the formats described below.

Usage notes
-----------

This element is for presenting dates and times in a machine-readable
format. For example, this can help a user agent offer to add an event to
a user\'s calendar.

This element should not be used for dates prior to the introduction of
the Gregorian calendar (due to complications in calculating those
dates).

The *datetime value* (the machine-readable value of the datetime) is the
value of the element\'s `datetime` attribute, which must be in the
proper format (see below). If the element does not have a `datetime`
attribute, **it must not have any element descendants**, and the
*datetime value* is the element\'s child text content.

### Valid datetime values

[a valid year string](#a_valid_year_string)

:   `2011`

[a valid month string](#a_valid_month_string)

:   `2011-11`

[a valid date string](#a_valid_date_string)

:   `2011-11-18`

[a valid yearless date string](#a_valid_yearless_date_string)

:   `11-18`

[a valid week string](#a_valid_week_string)

:   `2011-W47`

[a valid time string](#a_valid_time_string)

:   `14:54`

    `14:54:39`

    `14:54:39.929`

[a valid local date and time string](#a_valid_local_date_and_time_string)

:   `2011-11-18T14:54:39.929`

    `2011-11-18 14:54:39.929`

[a valid global date and time string](#a_valid_global_date_and_time_string)

:   `2011-11-18T14:54:39.929Z`

    `2011-11-18T14:54:39.929-0400`

    `2011-11-18T14:54:39.929-04:00`

    `2011-11-18 14:54:39.929Z`

    `2011-11-18 14:54:39.929-0400`

    `2011-11-18 14:54:39.929-04:00`

[a valid duration string](#a_valid_duration_string)

:   `PT4H18M3S`

Examples
--------

### Simple example

#### HTML

[html]

```html
<p>The concert starts at <time datetime="2018-07-07T20:00:00">20:00</time>.</p>
```

#### Result

### `datetime` example

#### HTML

[html]

```html
<p>
  The concert took place on <time datetime="2001-05-15T19:00">May 15</time>.
</p>
```

#### Result

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            `time`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLTimeElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTimeElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-time-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-time-element)

  ---------------------------------------------------------------------------------------------------------------

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

`time`

62

≤18

22

No

4911.5--12

7

62

62

22

4611.5--12

4

8.0

`datetime`

62

≤18

22

No

4911.5--12

7

62

62

22

4611.5--12

4

8.0

See also
--------

- The [`<data>`](data) element, allowing to signal other kind of
    values.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/time>>
