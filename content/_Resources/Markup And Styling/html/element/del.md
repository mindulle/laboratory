\<del\>: The Deleted Text element
=================================

The `<del>` [HTML](../index) element represents a range of text that has
been deleted from a document. This can be used when rendering \"track
changes\" or source code diff information, for example. The
[`<ins>`](ins) element can be used for the opposite purpose: to indicate
text that has been added to the document.

Try it
------

This element is often (but need not be) rendered by applying a
strike-through style to the text.

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Phrasing content](../content_categories#phrasing_content), [flow content](../content_categories#flow_content).
  Permitted content                             [Transparent](../content_categories#transparent_content_model).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            `deletion`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLModElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLModElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------

Attributes
----------

This element\'s attributes include the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`cite`](#cite)

:   A URI for a resource that explains the change (for example, meeting
    minutes).

[`datetime`](#datetime)

:   This attribute indicates the time and date of the change and must be
    a valid date string with an optional time. If the value cannot be
    parsed as a date with an optional time string, the element does not
    have an associated timestamp. For the format of the string without a
    time, see [Date strings](../date_and_time_formats#date_strings). The
    format of the string if it includes both date and time is covered in
    [Local date and time
    strings](../date_and_time_formats#local_date_and_time_strings).

Examples
--------

[html]

```html
<p><del>This text has been deleted</del>, here is the rest of the paragraph.</p>
<del><p>This paragraph has been deleted.</p></del>
```

### Result

Accessibility concerns
----------------------

The presence of the `del` element is not announced by most screen
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
del::before,
del::after {
  clip-path: inset(100%);
  clip: rect(1px, 1px, 1px, 1px);
  height: 1px;
  overflow: hidden;
  position: absolute;
  white-space: nowrap;
  width: 1px;
}

del::before {
  content: " [deletion start] ";
}

del::after {
  content: " [deletion end] ";
}

```

Some people who use screen readers deliberately disable announcing
content that creates extra verbosity. Because of this, it is important
to not abuse this technique and only apply it in situations where not
knowing content has been deleted would adversely affect understanding.

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
  the-del-element]](https://html.spec.whatwg.org/multipage/edits.html#the-del-element)

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

`del`

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

- [`<ins>`](ins) element for insertions into a text
- [`<s>`](s) element for strikethrough separate from representing
    deletion of text

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/del>
