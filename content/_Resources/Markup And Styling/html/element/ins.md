\<ins\>: The Inserted Text element
==================================

The `<ins>` [HTML](../index) element represents a range of text that has
been added to a document. You can use the [`<del>`](del) element to
similarly represent a range of text that has been deleted from the
document.

Try it
------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Phrasing content](../content_categories#phrasing_content), [flow content](../content_categories#flow_content).
  Permitted content                             [Transparent](../content_categories#transparent_content_model).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            `insertion`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLModElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLModElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`cite`](#cite)

:   This attribute defines the URI of a resource that explains the
    change, such as a link to meeting minutes or a ticket in a
    troubleshooting system.

[`datetime`](#datetime)

:   This attribute indicates the time and date of the change and must be
    a valid date with an optional time string. If the value cannot be
    parsed as a date with an optional time string, the element does not
    have an associated timestamp. For the format of the string without a
    time, see [Format of a valid date
    string](../date_and_time_formats#date_strings). The format of the
    string if it includes both date and time is covered in [Format of a
    valid local date and time
    string](../date_and_time_formats#local_date_and_time_strings).

Examples
--------

[html]

```html
<ins>This text has been inserted</ins>
```

### Result

Accessibility concerns
----------------------

The presence of the `<ins>` element is not announced by most screen
reading technology in its default configuration. It can be made to be
announced by using the CSS
[`content`](https://developer.mozilla.org/en-US/docs/Web/CSS/content)
property, along with the
[`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before)
and
[`::after`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after)
pseudo-elements.

[css]

```css
ins::before,
ins::after {
  clip-path: inset(100%);
  clip: rect(1px, 1px, 1px, 1px);
  height: 1px;
  overflow: hidden;
  position: absolute;
  white-space: nowrap;
  width: 1px;
}

ins::before {
  content: " [insertion start] ";
}

ins::after {
  content: " [insertion end] ";
}

```

Some people who use screen readers deliberately disable announcing
content that creates extra verbosity. Because of this, it is important
to not abuse this technique and only apply it in situations where not
knowing content has been inserted would adversely affect understanding.

- [Short note on making your mark (more accessible) \| The Paciello
    Group](https://www.tpgi.com/short-note-on-making-your-mark-more-accessible/)
- [Tweaking Text Level Styles \| Adrian
    Roselli](https://adrianroselli.com/2017/12/tweaking-text-level-styles.html)

Specifications
--------------

  ----------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-ins-element]](https://html.spec.whatwg.org/multipage/edits.html#the-ins-element)

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

`ins`

1

12

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

`cite`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`datetime`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

See also
--------

- [`<del>`](del) element for marking deletion into a document

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ins>
