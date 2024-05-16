\<form\>: The Form element
==========================

The `<form>` [HTML](../index) element represents a document section
containing interactive controls for submitting information.

Try it
------

It is possible to use the
[`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid) and
[`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)
CSS
[pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
to style a `<form>` element based on whether the
[`elements`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements)
inside the form are valid.

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`accept`](#accept) [Deprecated]

:   Comma-separated [content
    types](https://developer.mozilla.org/en-US/docs/Web/SVG/Content_type)
    the server accepts.

    **Note:** **This attribute has been deprecated and should not be
    used.** Instead, use the [`accept`](input#accept) attribute on
    `<input type=file>` elements.

[`accept-charset`](#accept-charset)

:   Space-separated [character
    encodings](https://developer.mozilla.org/en-US/docs/Glossary/Character_encoding)
    the server accepts. The browser uses them in the order in which they
    are listed. The default value means [the same encoding as the
    page](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Encoding).
    (In previous versions of HTML, character encodings could also be
    delimited by commas.)

[`autocapitalize`](#autocapitalize) [Non-standard]

:   A nonstandard attribute used by iOS Safari that controls how textual
    form elements should be automatically capitalized. `autocapitalize`
    attributes on a form elements override it on `<form>`. Possible
    values:

    -   `none`: No automatic capitalization.
    -   `sentences` (default): Capitalize the first letter of each
        sentence.
    -   `words`: Capitalize the first letter of each word.
    -   `characters`: Capitalize all characters --- that is, uppercase.

[`autocomplete`](#autocomplete)

:   Indicates whether input elements can by default have their values
    automatically completed by the browser. `autocomplete` attributes on
    form elements override it on `<form>`. Possible values:

    -   `off`: The browser may not automatically complete entries.
        (Browsers tend to ignore this for suspected login forms; see
        [The autocomplete attribute and login
        fields](https://developer.mozilla.org/en-US/docs/Web/Security/Securing_your_site/Turning_off_form_autocompletion#the_autocomplete_attribute_and_login_fields).)
    -   `on`: The browser may automatically complete entries.

[`name`](#name)

:   The name of the form. The value must not be the empty string, and
    must be unique among the `form` elements in the forms collection
    that it is in, if any.

[`rel`](#rel)

:   Controls the annotations and what kinds of links the form creates.
    Annotations include [`external`](../attributes/rel#external),
    [`nofollow`](../attributes/rel#nofollow),
    [`opener`](../attributes/rel#opener),
    [`noopener`](../attributes/rel#noopener), and
    [`noreferrer`](../attributes/rel#noreferrer). Link types include
    [`help`](../attributes/rel#help), [`prev`](../attributes/rel#prev),
    [`next`](../attributes/rel#next),
    [`search`](../attributes/rel#search), and
    [`license`](../attributes/rel#license). The
    [`rel`](../attributes/rel) value is a space-separated list of these
    enumerated values.

### Attributes for form submission

The following attributes control behavior during form submission.

[`action`](#action)

:   The URL that processes the form submission. This value can be
    overridden by a [`formaction`](button#formaction) attribute on a
    [`<button>`](button), [`<input type="submit">`](input/submit), or
    [`<input type="image">`](input/image) element. This attribute is
    ignored when `method="dialog"` is set.

[`enctype`](#enctype)

:   If the value of the `method` attribute is `post`, `enctype` is the
    [MIME type](https://en.wikipedia.org/wiki/Mime_type) of the form
    submission. Possible values:

    -   `application/x-www-form-urlencoded`: The default value.
    -   `multipart/form-data`: Use this if the form contains
        [`<input>`](input) elements with `type=file`.
    -   `text/plain`: Useful for debugging purposes.

    This value can be overridden by [`formenctype`](button#formenctype)
    attributes on [`<button>`](button),
    [`<input type="submit">`](input/submit), or
    [`<input type="image">`](input/image) elements.

[`method`](#method)

:   The [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP) method
    to submit the form with. The only allowed methods/values are (case
    insensitive):

    -   `post`: The
        [`POST`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST)
        method; form data sent as the [request
        body](https://developer.mozilla.org/en-US/docs/Web/API/Request/body).
    -   `get` (default): The
        [`GET`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET);
        form data appended to the `action` URL with a `?` separator. Use
        this method when the form [has no side
        effects](https://developer.mozilla.org/en-US/docs/Glossary/Idempotent).
    -   `dialog`: When the form is inside a [`<dialog>`](dialog), closes
        the dialog and causes a `submit` event to be fired on
        submission, without submitting data or clearing the form.

    This value is overridden by [`formmethod`](button#formmethod)
    attributes on [`<button>`](button),
    [`<input type="submit">`](input/submit), or
    [`<input type="image">`](input/image) elements.

[`novalidate`](#novalidate)

:   This Boolean attribute indicates that the form shouldn\'t be
    validated when submitted. If this attribute is not set (and
    therefore the form ***is*** validated), it can be overridden by a
    [`formnovalidate`](button#formnovalidate) attribute on a
    [`<button>`](button), [`<input type="submit">`](input/submit), or
    [`<input type="image">`](input/image) element belonging to the form.

[`target`](#target)

:   Indicates where to display the response after submitting the form.
    It is a name/keyword for a *browsing context* (for example, tab,
    window, or iframe). The following keywords have special meanings:

    -   `_self` (default): Load into the same browsing context as the
        current one.
    -   `_blank`: Load into a new unnamed browsing context. This
        provides the same behavior as setting [`rel="noopener"`](#rel)
        which does not set
        [`window.opener`](https://developer.mozilla.org/en-US/docs/Web/API/Window/opener).
    -   `_parent`: Load into the parent browsing context of the current
        one. If no parent, behaves the same as `_self`.
    -   `_top`: Load into the top-level browsing context (i.e., the
        browsing context that is an ancestor of the current one and has
        no parent). If no parent, behaves the same as `_self`.

    This value can be overridden by a [`formtarget`](button#formtarget)
    attribute on a [`<button>`](button),
    [`<input type="submit">`](input/submit), or
    [`<input type="image">`](input/image) element.

Examples
--------

[html]

```html
<!-- Form which will send a GET request to the current URL -->
<form method="get">
  <label>
    Name:
    <input name="submitted-name" autocomplete="name" />
  </label>
  <button>Save</button>
</form>

<!-- Form which will send a POST request to the current URL -->
<form method="post">
  <label>
    Name:
    <input name="submitted-name" autocomplete="name" />
  </label>
  <button>Save</button>
</form>

<!-- Form with fieldset, legend, and label -->
<form method="post">
  <fieldset>
    <legend>Do you agree to the terms?</legend>
    <label><input type="radio" name="radio" value="yes" /> Yes</label>
    <label><input type="radio" name="radio" value="no" /> No</label>
  </fieldset>
</form>
```

### Result

Technical summary
-----------------

  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [palpable content](../content_categories#palpable_content)
  Permitted content                             [Flow content](../content_categories#flow_content), but not containing `<form>` elements
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content)
  Implicit ARIA role                            `form`
  Permitted ARIA roles                          `search`, [`none`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/none_role) or [`presentation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role)
  DOM interface                                 [`HTMLFormElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement)
  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-form-element]](https://html.spec.whatwg.org/multipage/forms.html#the-form-element)

  ------------------------------------------------------------------------------------------------

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

`form`

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

`accept`

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

`accept-charset`

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

`action`

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

`autocapitalize`

43

79

111

No

30

No

43

43

111

30

Yes

4.0

`autocomplete`

14The Google Chrome UI for auto-complete request varies, depending on
whether `autocomplete` is set to `off` on `<input>` elements as well as
their form. Specifically, when a form has `autocomplete` set to `off`
and its `<input>` element\'s `autocomplete` attribute is not set, then
if the user asks for autofill suggestions for the `<input>` element,
Chrome might display a message saying \'autocomplete has been disabled
for this form.\' On the other hand, if both the form and the input
element have `autocomplete` set to `off`, the browser will not display
that message. For this reason, you should set `autocomplete` to `off`
for each `<input>` that has custom auto-completion.

12

4

Yes

15The Opera UI for auto-complete request varies, depending on whether
`autocomplete` is set to `off` on `<input>` elements as well as their
form. Specifically, when a form has `autocomplete` set to `off` and its
`<input>` element\'s `autocomplete` attribute is not set, then if the
user asks for autofill suggestions for the `<input>` element, Opera
might display a message saying \'autocomplete has been disabled for this
form.\' On the other hand, if both the form and the input element have
`autocomplete` set to `off`, the browser will not display that message.
For this reason, you should set `autocomplete` to `off` for each
`<input>` that has custom auto-completion.

6

4.4The Google Chrome UI for auto-complete request varies, depending on
whether `autocomplete` is set to `off` on `<input>` elements as well as
their form. Specifically, when a form has `autocomplete` set to `off`
and its `<input>` element\'s `autocomplete` attribute is not set, then
if the user asks for autofill suggestions for the `<input>` element,
Chrome might display a message saying \'autocomplete has been disabled
for this form.\' On the other hand, if both the form and the input
element have `autocomplete` set to `off`, the browser will not display
that message. For this reason, you should set `autocomplete` to `off`
for each `<input>` that has custom auto-completion.

18The Google Chrome UI for auto-complete request varies, depending on
whether `autocomplete` is set to `off` on `<input>` elements as well as
their form. Specifically, when a form has `autocomplete` set to `off`
and its `<input>` element\'s `autocomplete` attribute is not set, then
if the user asks for autofill suggestions for the `<input>` element,
Chrome might display a message saying \'autocomplete has been disabled
for this form.\' On the other hand, if both the form and the input
element have `autocomplete` set to `off`, the browser will not display
that message. For this reason, you should set `autocomplete` to `off`
for each `<input>` that has custom auto-completion.

4

14The Opera UI for auto-complete request varies, depending on whether
`autocomplete` is set to `off` on `<input>` elements as well as their
form. Specifically, when a form has `autocomplete` set to `off` and its
`<input>` element\'s `autocomplete` attribute is not set, then if the
user asks for autofill suggestions for the `<input>` element, Opera
might display a message saying \'autocomplete has been disabled for this
form.\' On the other hand, if both the form and the input element have
`autocomplete` set to `off`, the browser will not display that message.
For this reason, you should set `autocomplete` to `off` for each
`<input>` that has custom auto-completion.

6

1.0The Samsung Internet UI for auto-complete request varies, depending
on whether `autocomplete` is set to `off` on `<input>` elements as well
as their form. Specifically, when a form has `autocomplete` set to `off`
and its `<input>` element\'s `autocomplete` attribute is not set, then
if the user asks for autofill suggestions for the `<input>` element,
Samsung Internet might display a message saying \'autocomplete has been
disabled for this form.\' On the other hand, if both the form and the
input element have `autocomplete` set to `off`, the browser will not
display that message. For this reason, you should set `autocomplete` to
`off` for each `<input>` that has custom auto-completion.

`enctype`

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

`method`

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

`name`

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

`novalidate`

10

12

4

10

15

10.1

37

18

4

14

10.3

1.0

`rel`

108

108

111

No

94

15.4

108

108

111

73

15.4

21.0

`target`

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

- [HTML forms
    guide](https://developer.mozilla.org/en-US/docs/Learn/Forms)
- Other elements that are used when creating forms:
    [`<button>`](button), [`<datalist>`](datalist),
    [`<fieldset>`](fieldset), [`<input>`](input), [`<label>`](label),
    [`<legend>`](legend), [`<meter>`](meter), [`<optgroup>`](optgroup),
    [`<option>`](option), [`<output>`](output),
    [`<progress>`](progress), [`<select>`](select),
    [`<textarea>`](textarea).
- Getting a list of the elements in the form:
    [`HTMLFormElement.elements`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements)
- [ARIA: Form
    role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/form_role)
- [ARIA: Search
    role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/search_role)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form>>
