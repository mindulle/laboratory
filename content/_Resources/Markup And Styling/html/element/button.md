\<button\>: The Button element
==============================

The `<button>` [HTML](../index) element is an interactive element
activated by a user with a mouse, keyboard, finger, voice command, or
other assistive technology. Once activated, it then performs an action,
such as submitting a
[form](https://developer.mozilla.org/en-US/docs/Learn/Forms) or opening
a dialog.

By default, HTML buttons are presented in a style resembling the
platform the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
runs on, but you can change buttons\' appearance with
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS).

Try it
------

Attributes
----------

This element\'s attributes include the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`autofocus`](#autofocus)

:   This Boolean attribute specifies that the button should have input
    [focus](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/focus)
    when the page loads. **Only one element in a document can have this
    attribute.**

[`autocomplete`](#autocomplete) [Non-standard]

:   This attribute on a [`<button>`](button) is nonstandard and
    Firefox-specific. Unlike other browsers, [Firefox persists the
    dynamic disabled
    state](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing)
    of a [`<button>`](button) across page loads. Setting
    `autocomplete="off"` on the button disables this feature; see
    [Firefox bug 654072](https://bugzil.la/654072).

[`disabled`](#disabled)

:   This Boolean attribute prevents the user from interacting with the
    button: it cannot be pressed or focused.

    Firefox, unlike other browsers, [persists the dynamic disabled
    state](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing)
    of a [`<button>`](button) across page loads. To control this
    feature, use the [`autocomplete`](#autocomplete) attribute.

[`form`](#form)

:   The [`<form>`](form) element to associate the button with (its *form
    owner*). The value of this attribute must be the `id` of a `<form>`
    in the same document. (If this attribute is not set, the `<button>`
    is associated with its ancestor `<form>` element, if any.)

    This attribute lets you associate `<button>` elements to `<form>`s
    anywhere in the document, not just inside a `<form>`. It can also
    override an ancestor `<form>` element.

[`formaction`](#formaction)

:   The URL that processes the information submitted by the button.
    Overrides the [`action`](form#action) attribute of the button\'s
    form owner. Does nothing if there is no form owner.

[`formenctype`](#formenctype)

:   If the button is a submit button (it\'s inside/associated with a
    `<form>` and doesn\'t have `type="button"`), specifies how to encode
    the form data that is submitted. Possible values:

    -   `application/x-www-form-urlencoded`: The default if the
        attribute is not used.
    -   `multipart/form-data`: Used to submit [`<input>`](input)
        elements with their [`type`](input#type) attributes set to
        `file`.
    -   `text/plain`: Specified as a debugging aid; shouldn\'t be used
        for real form submission.

    If this attribute is specified, it overrides the
    [`enctype`](form#enctype) attribute of the button\'s form owner.

[`formmethod`](#formmethod)

:   If the button is a submit button (it\'s inside/associated with a
    `<form>` and doesn\'t have `type="button"`), this attribute
    specifies the [HTTP
    method](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
    used to submit the form. Possible values:

    -   `post`: The data from the form are included in the body of the
        HTTP request when sent to the server. Use when the form contains
        information that shouldn\'t be public, like login credentials.
    -   `get`: The form data are appended to the form\'s `action` URL,
        with a `?` as a separator, and the resulting URL is sent to the
        server. Use this method when the form [has no side
        effects](https://developer.mozilla.org/en-US/docs/Glossary/Idempotent),
        like search forms.
    -   `dialog`: This method is used to indicate that the button closes
        the [dialog](dialog) with which it is associated, and does not
        transmit the form data at all.

    If specified, this attribute overrides the [`method`](form#method)
    attribute of the button\'s form owner.

[`formnovalidate`](#formnovalidate)

:   If the button is a submit button, this Boolean attribute specifies
    that the form is not to be
    [validated](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)
    when it is submitted. If this attribute is specified, it overrides
    the [`novalidate`](form#novalidate) attribute of the button\'s form
    owner.

    This attribute is also available on
    [`<input type="image">`](input/image) and
    [`<input type="submit">`](input/submit) elements.

[`formtarget`](#formtarget)

:   If the button is a submit button, this attribute is an
    author-defined name or standardized, underscore-prefixed keyword
    indicating where to display the response from submitting the form.
    This is the `name` of, or keyword for, a *browsing context* (a tab,
    window, or [`<iframe>`](iframe)). If this attribute is specified, it
    overrides the [`target`](form#target) attribute of the button\'s
    form owner. The following keywords have special meanings:

    -   `_self`: Load the response into the same browsing context as the
        current one. This is the default if the attribute is not
        specified.
    -   `_blank`: Load the response into a new unnamed browsing context
        --- usually a new tab or window, depending on the user\'s
        browser settings.
    -   `_parent`: Load the response into the parent browsing context of
        the current one. If there is no parent, this option behaves the
        same way as `_self`.
    -   `_top`: Load the response into the top-level browsing context
        (that is, the browsing context that is an ancestor of the
        current one, and has no parent). If there is no parent, this
        option behaves the same way as `_self`.

[`name`](#name)

:   The name of the button, submitted as a pair with the button\'s
    `value` as part of the form data, when that button is used to submit
    the form.

[`popovertarget`](#popovertarget)

:   Turns a `<button>` element into a popover control button; takes the
    ID of the popover element to control as its value. See the [Popover
    API](https://developer.mozilla.org/en-US/docs/Web/API/Popover_API)
    landing page for more details.

[`popovertargetaction`](#popovertargetaction)

:   Specifies the action to be performed on a popover element being
    controlled by a control `<button>`. Possible values are:

    [`"hide"`](#hide)

    :   The button will hide a shown popover. If you try to hide an
        already hidden popover, no action will be taken.

    [`"show"`](#show)

    :   The button will show a hidden popover. If you try to show an
        already showing popover, no action will be taken.

    [`"toggle"`](#toggle)

    :   The button will toggle a popover between showing and hidden. If
        the popover is hidden, it will be shown; if the popover is
        showing, it will be hidden. If `popovertargetaction` is omitted,
        `"toggle"` is the default action that will be performed by the
        control button.

[`type`](#type)

:   The default behavior of the button. Possible values are:

    -   `submit`: The button submits the form data to the server. This
        is the default if the attribute is not specified for buttons
        associated with a `<form>`, or if the attribute is an empty or
        invalid value.
    -   `reset`: The button resets all the controls to their initial
        values, like [\<input type=\"reset\"\>](input/reset). (This
        behavior tends to annoy users.)
    -   `button`: The button has no default behavior, and does nothing
        when pressed by default. It can have client-side scripts listen
        to the element\'s events, which are triggered when the events
        occur.

[`value`](#value)

:   Defines the value associated with the button\'s `name` when it\'s
    submitted with the form data. This value is passed to the server in
    params when the form is submitted using this button.

Notes
-----

A submit button with the attribute `formaction` set, but without an
associated form does nothing. You have to set a form owner, either by
wrapping it in a `<form>` or set the attribute `form` to the id of the
form.

`<button>` elements are much easier to style than [`<input>`](input)
elements. You can add inner HTML content (think `<i>`, `<br>`, or even
`<img>`), and use
[`::after`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after)
and
[`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before)
pseudo-elements for complex rendering.

If your buttons are not for submitting form data to a server, be sure to
set their `type` attribute to `button`. Otherwise they will try to
submit form data and to load the (nonexistent) response, possibly
destroying the current state of the document.

While `<button type="button">` has no default behavior, event handlers
can be scripted to trigger behaviors. An activated button can perform
programmable actions using
[JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript),
such as removing an item from a list.

Examples
--------

[html]

```html
<button name="button">Press me</button>
```

Accessibility concerns
----------------------

### Icon buttons

Buttons that only show an icon to represent do not have an *accessible
name*. Accessible names provide information for assistive technology,
such as screen readers, to access when they parse the document and
generate [an accessibility
tree](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#accessibility_apis).
Assistive technology then uses the accessibility tree to navigate and
manipulate page content.

To give an icon button an accessible name, put text in the `<button>`
element that concisely describes the button\'s functionality.

#### Examples

[html]

```html
<button name="favorite">
  <svg aria-hidden="true" viewBox="0 0 10 10">
    <path d="M7 9L5 8 3 9V6L1 4h3l1-3 1 3h3L7 6z" />
  </svg>
  Add to favorites
</button>
```

##### Result

If you want to visually hide the button\'s text, an accessible way to do
so is to use [a combination of CSS
properties](https://gomakethings.com/hidden-content-for-better-a11y/#hiding-the-link)
to remove it visually from the screen, but keep it parsable by assistive
technology.

However, it is worth noting that leaving the button text visually
apparent can aid people who may not be familiar with the icon\'s meaning
or understand the button\'s purpose. This is especially relevant for
people who are not technologically sophisticated, or who may have
different cultural interpretations for the icon the button uses.

- [What is an accessible name? \| The Paciello
    Group](https://www.tpgi.com/what-is-an-accessible-name/)
- [MDN Understanding WCAG, Guideline 4.1
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Robust#guideline_4.1_%E2%80%94_compatible_maximize_compatibility_with_current_and_future_user_agents_including_assistive_technologies)
- [Understanding Success Criterion 4.1.2 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/ensure-compat-rsv.html)

### Size and Proximity

#### Size

Interactive elements such as buttons should provide an area large enough
that it is easy to activate them. This helps a variety of people,
including people with motor control issues and people using non-precise
forms of input such as a stylus or fingers. A minimum interactive size
of 44×44 [CSS pixels](https://www.w3.org/TR/WCAG21/#dfn-css-pixels) is
recommended.

- [Understanding Success Criterion 2.5.5: Target Size \| W3C
    Understanding WCAG
    2.1](https://www.w3.org/WAI/WCAG21/Understanding/target-size.html)
- [Target Size and 2.5.5 \| Adrian
    Roselli](https://adrianroselli.com/2019/06/target-size-and-2-5-5.html)
- [Quick test: Large touch targets - The A11Y
    Project](https://www.a11yproject.com/posts/large-touch-targets/)

#### Proximity

Large amounts of interactive content --- including buttons --- placed in
close visual proximity to each other should have space separating them.
This spacing is beneficial for people who are experiencing motor control
issues, who may accidentally activate the wrong interactive content.

Spacing may be created using CSS properties such as
[`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin).

- [Hand tremors and the giant-button-problem - Axess
    Lab](https://axesslab.com/hand-tremors/)

### ARIA state information

To describe the state of a button the correct ARIA attribute to use is
[`aria-pressed`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-pressed)
and not
[`aria-checked`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-checked)
or
[`aria-selected`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-selected).
To find out more read the information about the [ARIA button
role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/button_role).

### Firefox

Firefox will add a small dotted border on a focused button. This border
is declared through CSS in the browser stylesheet, but you can override
it to add your own focused style using
[`button::-moz-focus-inner { }`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-moz-focus-inner).

If overridden, it is important to **ensure that the state change when
focus is moved to the button is high enough** that people experiencing
low vision conditions will be able to perceive it.

Color contrast ratio is determined by comparing the luminosity of the
button text and background color values compared to the background the
button is placed on. In order to meet current [Web Content Accessibility
Guidelines (WCAG)](https://www.w3.org/WAI/standards-guidelines/wcag/), a
ratio of 4.5:1 is required for text content and 3:1 for large text.
(Large text is defined as 18.66px and
[`bold`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight)
or larger, or 24px or larger.)

- [WebAIM: Color Contrast
    Checker](https://webaim.org/resources/contrastchecker/)
- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.3 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

### Clicking and focus

Whether clicking on a [`<button>`](button) or [`<input>`](input) button
types causes it to (by default) become focused varies by browser and OS.
Most browsers do give focus to a button being clicked, but [Safari does
not, by design](https://webkit.org/b/22261).

Technical summary
-----------------

  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), [Interactive content](../content_categories#interactive_content), [listed](../content_categories#form_listed), [labelable](../content_categories#form_labelable), and [submittable](../content_categories#form_submittable) [form-associated](../content_categories#form-associated_content) element, palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content) but there must be no [Interactive content](../content_categories#interactive_content)
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            `button`
  Permitted ARIA roles                          [`checkbox`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/checkbox_role), [`combobox`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/combobox_role), [`link`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/link_role), [`menuitem`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/menuitem_role), [`menuitemcheckbox`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/menuitemcheckbox_role), [`menuitemradio`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/menuitemradio_role), [`option`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/option_role), [`radio`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/radio_role), [`switch`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/switch_role), [`tab`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/tab_role)
  DOM interface                                 [`HTMLButtonElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLButtonElement)
  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-button-element]](https://html.spec.whatwg.org/multipage/form-elements.html#the-button-element)

  ------------------------------------------------------------------------------------------------------------

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

`button`

1

12

1

Yes

≤15

≤4

4.4

18

4

≤14

≤3.2

1.0

`autocomplete`

No

No

4

No

No

No

No

No

4

No

No

No

`disabled`

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

`form`

9

16

4

No

15

5.1

4.4

18

4

14

5

1.0

`formaction`

9

12

4

10

15

5.1

37

18

4

No

5

1.0

`formenctype`

9

12

4

10

10.6

5.1

37

18

4

11

5

1.0

`formmethod`

9

12

4

10

15

5.1

37

18

4

14

5

1.0

`formnovalidate`

9

12

4

Yes

15

5.1

4.4

18

4

14

5

1.0

`formtarget`

9

12

4

Yes

15

5.1

4.4

18

4

14

5

1.0

`name`

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

`type`

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

`value`

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

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button>>
