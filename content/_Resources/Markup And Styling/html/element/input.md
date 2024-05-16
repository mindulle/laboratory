\<input\>: The Input (Form Input) element
=========================================

The `<input>` [HTML](../index) element is used to create interactive
controls for web-based forms in order to accept data from the user; a
wide variety of types of input data and control widgets are available,
depending on the device and [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).
The `<input>` element is one of the most powerful and complex in all of
HTML due to the sheer number of combinations of input types and
attributes.

Try it
------

\<input\> types
---------------

How an `<input>` works varies considerably depending on the value of its
[`type`](#type) attribute, hence the different types are covered in
their own separate reference pages. If this attribute is not specified,
the default type adopted is `text`.

The available types are as follows:

Type

Description

Basic Examples

[button](input/button)

A push button with no default behavior displaying the value of the
[`value`](#value) attribute, empty by default.

[checkbox](input/checkbox)

A check box allowing single values to be selected/deselected.

[color](input/color)

A control for specifying a color; opening a color picker when active in
supporting browsers.

[date](input/date)

A control for entering a date (year, month, and day, with no time).
Opens a date picker or numeric wheels for year, month, day when active
in supporting browsers.

[datetime-local](input/datetime-local)

A control for entering a date and time, with no time zone. Opens a date
picker or numeric wheels for date- and time-components when active in
supporting browsers.

[email](input/email)

A field for editing an email address. Looks like a `text` input, but has
validation parameters and relevant keyboard in supporting browsers and
devices with dynamic keyboards.

[file](input/file)

A control that lets the user select a file. Use the [`accept`](#accept)
attribute to define the types of files that the control can select.

[hidden](input/hidden)

A control that is not displayed but whose value is submitted to the
server. There is an example in the next column, but it\'s hidden!

[image](input/image)

A graphical `submit` button. Displays an image defined by the `src`
attribute. The [`alt`](#alt) attribute displays if the image
[`src`](#src) is missing.

[month](input/month)

A control for entering a month and year, with no time zone.

[number](input/number)

A control for entering a number. Displays a spinner and adds default
validation. Displays a numeric keypad in some devices with dynamic
keypads.

[password](input/password)

A single-line text field whose value is obscured. Will alert user if
site is not secure.

[radio](input/radio)

A radio button, allowing a single value to be selected out of multiple
choices with the same [`name`](#name) value.

[range](input/range)

A control for entering a number whose exact value is not important.
Displays as a range widget defaulting to the middle value. Used in
conjunction [`min`](#min) and [`max`](#max) to define the range of
acceptable values.

[reset](input/reset)

A button that resets the contents of the form to default values. Not
recommended.

[search](input/search)

A single-line text field for entering search strings. Line-breaks are
automatically removed from the input value. May include a delete icon in
supporting browsers that can be used to clear the field. Displays a
search icon instead of enter key on some devices with dynamic keypads.

[submit](input/submit)

A button that submits the form.

[tel](input/tel)

A control for entering a telephone number. Displays a telephone keypad
in some devices with dynamic keypads.

[text](input/text)

The default value. A single-line text field. Line-breaks are
automatically removed from the input value.

[time](input/time)

A control for entering a time value with no time zone.

[url](input/url)

A field for entering a URL. Looks like a `text` input, but has
validation parameters and relevant keyboard in supporting browsers and
devices with dynamic keyboards.

[week](input/week)

A control for entering a date consisting of a week-year number and a
week number with no time zone.

Obsolete values

`datetime` [Deprecated]

A control for entering a date and time (hour, minute, second, and
fraction of a second) based on UTC time zone.

Attributes
----------

The `<input>` element is so powerful because of its attributes; the
[`type`](#type) attribute, described with examples above, being the most
important. Since every `<input>` element, regardless of type, is based
on the
[`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
interface, they technically share the exact same set of attributes.
However, in reality, most attributes have an effect on only a specific
subset of input types. In addition, the way some attributes impact an
input depends on the input type, impacting different input types in
different ways.

This section provides a table listing all the attributes with a brief
description. This table is followed by a list describing each attribute
in greater detail, along with which input types they are associated
with. Those that are common to most or all input types are defined in
greater detail below. Attributes that are unique to particular input
types---or attributes which are common to all input types but have
special behaviors when used on a given input type---are instead
documented on those types\' pages.

Attributes for the `<input>` element include the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) and additionally:

  Attribute                                       Type or Types                                                             Description
  ----------------------------------------------- ------------------------------------------------------------------------- ----------------------------------------------------------------------------------------
  [`accept`](#accept)                             `file`                                                                    Hint for expected file type in file upload controls
  [`alt`](#alt)                                   `image`                                                                   alt attribute for the image type. Required for accessibility
  [`autocomplete`](#autocomplete)                 all except `checkbox`, `radio`, and buttons                               Hint for form autofill feature
  [`capture`](#capture)                           `file`                                                                    Media capture input method in file upload controls
  [`checked`](#checked)                           `checkbox`, `radio`                                                       Whether the command or control is checked
  [`dirname`](#dirname)                           `hidden`, `text`, `search`, `url`, `tel`, `email`                         Name of form field to use for sending the element\'s directionality in form submission
  [`disabled`](#disabled)                         all                                                                       Whether the form control is disabled
  [`form`](#form)                                 all                                                                       Associates the control with a form element
  [`formaction`](#formaction)                     `image`, `submit`                                                         URL to use for form submission
  [`formenctype`](#formenctype)                   `image`, `submit`                                                         Form data set encoding type to use for form submission
  [`formmethod`](#formmethod)                     `image`, `submit`                                                         HTTP method to use for form submission
  [`formnovalidate`](#formnovalidate)             `image`, `submit`                                                         Bypass form control validation for form submission
  [`formtarget`](#formtarget)                     `image`, `submit`                                                         Browsing context for form submission
  [`height`](#height)                             `image`                                                                   Same as height attribute for [`<img>`](img); vertical dimension
  [`list`](#list)                                 all except `hidden`, `password`, `checkbox`, `radio`, and buttons         Value of the id attribute of the [`<datalist>`](datalist) of autocomplete options
  [`max`](#max)                                   `date`, `month`, `week`, `time`, `datetime-local`, `number`, `range`      Maximum value
  [`maxlength`](#maxlength)                       `text`, `search`, `url`, `tel`, `email`, `password`                       Maximum length (number of characters) of `value`
  [`min`](#min)                                   `date`, `month`, `week`, `time`, `datetime-local`, `number`, `range`      Minimum value
  [`minlength`](#minlength)                       `text`, `search`, `url`, `tel`, `email`, `password`                       Minimum length (number of characters) of `value`
  [`multiple`](#multiple)                         `email`, `file`                                                           Boolean. Whether to allow multiple values
  [`name`](#name)                                 all                                                                       Name of the form control. Submitted with the form as part of a name/value pair
  [`pattern`](#pattern)                           `text`, `search`, `url`, `tel`, `email`, `password`                       Pattern the `value` must match to be valid
  [`placeholder`](#placeholder)                   `text`, `search`, `url`, `tel`, `email`, `password`, `number`             Text that appears in the form control when it has no value set
  [`popovertarget`](#popovertarget)               `button`                                                                  Designates an `<input type="button">` as a control for a popover element
  [`popovertargetaction`](#popovertargetaction)   `button`                                                                  Specifies the action that a popover control should perform
  [`readonly`](#readonly)                         all except `hidden`, `range`, `color`, `checkbox`, `radio`, and buttons   Boolean. The value is not editable
  [`required`](#required)                         all except `hidden`, `range`, `color`, and buttons                        Boolean. A value is required or must be checked for the form to be submittable
  [`size`](#size)                                 `text`, `search`, `url`, `tel`, `email`, `password`                       Size of the control
  [`src`](#src)                                   `image`                                                                   Same as `src` attribute for [`<img>`](img); address of image resource
  [`step`](#step)                                 `date`, `month`, `week`, `time`, `datetime-local`, `number`, `range`      Incremental values that are valid
  [`type`](#type)                                 all                                                                       Type of form control
  [`value`](#value)                               all except `image`                                                        The initial value of the control
  [`width`](#width)                               `image`                                                                   Same as `width` attribute for [`<img>`](img)

A few additional non-standard attributes are listed following the
descriptions of the standard attributes.

### Individual attributes

[`accept`](#accept)

:   Valid for the `file` input type only, the `accept` attribute defines
    which file types are selectable in a `file` upload control. See the
    [file](input/file) input type.

[`alt`](#alt)

:   Valid for the `image` button only, the `alt` attribute provides
    alternative text for the image, displaying the value of the
    attribute if the image [`src`](#src) is missing or otherwise fails
    to load. See the [image](input/image) input type.

[`autocomplete`](../attributes/autocomplete)

:   (**Not** a Boolean attribute!) The
    [`autocomplete`](../attributes/autocomplete) attribute takes as its
    value a space-separated string that describes what, if any, type of
    autocomplete functionality the input should provide. A typical
    implementation of autocomplete recalls previous values entered in
    the same input field, but more complex forms of autocomplete can
    exist. For instance, a browser could integrate with a device\'s
    contacts list to autocomplete `email` addresses in an email input
    field. See [`autocomplete`](../attributes/autocomplete#values) for
    permitted values.

    The `autocomplete` attribute is valid on `hidden`, `text`, `search`,
    `url`, `tel`, `email`, `date`, `month`, `week`, `time`,
    `datetime-local`, `number`, `range`, `color`, and `password`. This
    attribute has no effect on input types that do not return numeric or
    text data, being valid for all input types except `checkbox`,
    `radio`, `file`, or any of the button types.

    See the [`autocomplete` attribute](../attributes/autocomplete) for
    additional information, including information on password security
    and how `autocomplete` is slightly different for `hidden` than for
    other input types.

[`autofocus`](#autofocus)

:   A Boolean attribute which, if present, indicates that the input
    should automatically have focus when the page has finished loading
    (or when the [`<dialog>`](dialog) containing the element has been
    displayed).

    **Note:** An element with the `autofocus` attribute may gain focus
    before the
    [`DOMContentLoaded`](https://developer.mozilla.org/en-US/docs/Web/API/Document/DOMContentLoaded_event)
    event is fired.
    

    No more than one element in the document may have the `autofocus`
    attribute. If put on more than one element, the first one with the
    attribute receives focus.

    The `autofocus` attribute cannot be used on inputs of type `hidden`,
    since hidden inputs cannot be focused.

     
    **Warning:** Automatically focusing a form control can confuse
    visually-impaired people using screen-reading technology and people
    with cognitive impairments. When `autofocus` is assigned,
    screen-readers \"teleport\" their user to the form control without
    warning them beforehand.
    

    Use careful consideration for accessibility when applying the
    `autofocus` attribute. Automatically focusing on a control can cause
    the page to scroll on load. The focus can also cause dynamic
    keyboards to display on some touch devices. While a screen reader
    will announce the label of the form control receiving focus, the
    screen reader will not announce anything before the label, and the
    sighted user on a small device will equally miss the context created
    by the preceding content.

[`capture`](#capture)

:   Introduced in the HTML Media Capture specification and valid for the
    `file` input type only, the `capture` attribute defines which
    media---microphone, video, or camera---should be used to capture a
    new file for upload with `file` upload control in supporting
    scenarios. See the [file](input/file) input type.

[`checked`](#checked)

:   Valid for both `radio` and `checkbox` types, `checked` is a Boolean
    attribute. If present on a `radio` type, it indicates that the radio
    button is the currently selected one in the group of same-named
    radio buttons. If present on a `checkbox` type, it indicates that
    the checkbox is checked by default (when the page loads). It does
    *not* indicate whether this checkbox is currently checked: if the
    checkbox\'s state is changed, this content attribute does not
    reflect the change. (Only the [`HTMLInputElement`\'s `checked` IDL
    attribute](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
    is updated.)

    **Note:** Unlike other input controls, a checkboxes and radio
    buttons value are only included in the submitted data if they are
    currently `checked`. If they are, the name and the value(s) of the
    checked controls are submitted.

    For example, if a checkbox whose `name` is `fruit` has a `value` of
    `cherry`, and the checkbox is checked, the form data submitted will
    include `fruit=cherry`. If the checkbox isn\'t active, it isn\'t
    listed in the form data at all. The default `value` for checkboxes
    and radio buttons is `on`.

[`dirname`](#dirname)

:   Valid for `hidden`, `text`, `search`, `url`, `tel`, and `email`
    input types, the `dirname` attribute enables the submission of the
    directionality of the element. When included, the form control will
    submit with two name/value pairs: the first being the
    [`name`](#name) and [`value`](#value), and the second being the
    value of the `dirname` attribute as the name, with a value of `ltr`
    or `rtl` as set by the browser.

    [html]

    ```html
    <form action="page.html" method="post">
      <label>
        Fruit:
        <input type="text" name="fruit" dirname="fruit-dir" value="cherry" />
      </label>
      <input type="submit" />
    </form>
    <!-- page.html?fruit=cherry&fruit-dir=ltr -->
    ```
    

    When the form above is submitted, the input cause both the `name` /
    `value` pair of `fruit=cherry` and the `dirname` / direction pair of
    `fruit-dir=ltr` to be sent. For more information, see the [`dirname`
    attribute](../attributes/dirname).

[`disabled`](#disabled)

:   A Boolean attribute which, if present, indicates that the user
    should not be able to interact with the input. Disabled inputs are
    typically rendered with a dimmer color or using some other form of
    indication that the field is not available for use.

    Specifically, disabled inputs do not receive the
    [`click`](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event)
    event, and disabled inputs are not submitted with the form.

     
    **Note:** Although not required by the specification, Firefox will
    by default [persist the dynamic disabled
    state](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing)
    of an `<input>` across page loads. Use the
    [`autocomplete`](#autocomplete) attribute to control this feature.

[`form`](#form)

:   A string specifying the [`<form>`](form) element with which the
    input is associated (that is, its **form owner**). This string\'s
    value, if present, must match the [`id`](#id) of a `<form>` element
    in the same document. If this attribute isn\'t specified, the
    `<input>` element is associated with the nearest containing form, if
    any.

    The `form` attribute lets you place an input anywhere in the
    document but have it included with a form elsewhere in the document.

     
    **Note:** An input can only be associated with one form.

[`formaction`](#formaction)

:   Valid for the `image` and `submit` input types only. See the
    [submit](input/submit) input type for more information.

[`formenctype`](#formenctype)

:   Valid for the `image` and `submit` input types only. See the
    [submit](input/submit) input type for more information.

[`formmethod`](#formmethod)

:   Valid for the `image` and `submit` input types only. See the
    [submit](input/submit) input type for more information.

[`formnovalidate`](#formnovalidate)

:   Valid for the `image` and `submit` input types only. See the
    [submit](input/submit) input type for more information.

[`formtarget`](#formtarget)

:   Valid for the `image` and `submit` input types only. See the
    [submit](input/submit) input type for more information.

[`height`](#height)

:   Valid for the `image` input button only, the `height` is the height
    of the image file to display to represent the graphical submit
    button. See the [image](input/image) input type.

[`id`](#id)

:   Global attribute valid for all elements, including all the input
    types, it defines a unique identifier (ID) which must be unique in
    the whole document. Its purpose is to identify the element when
    linking. The value is used as the value of the [`<label>`](label)\'s
    `for` attribute to link the label with the form control. See
    [`<label>`](label).

[`inputmode`](#inputmode)

:   Global value valid for all elements, it provides a hint to browsers
    as to the type of virtual keyboard configuration to use when editing
    this element or its contents. Values include `none`, `text`, `tel`,
    `url`, `email`, `numeric`, `decimal`, and `search`.

[`list`](#list)

:   The value given to the `list` attribute should be the
    [`id`](https://developer.mozilla.org/en-US/docs/Web/API/Element/id)
    of a [`<datalist>`](datalist) element located in the same document.
    The `<datalist>` provides a list of predefined values to suggest to
    the user for this input. Any values in the list that are not
    compatible with the [`type`](#type) are not included in the
    suggested options. The values provided are suggestions, not
    requirements: users can select from this predefined list or provide
    a different value.

    It is valid on `text`, `search`, `url`, `tel`, `email`, `date`,
    `month`, `week`, `time`, `datetime-local`, `number`, `range`, and
    `color`.

    Per the specifications, the `list` attribute is not supported by the
    `hidden`, `password`, `checkbox`, `radio`, `file`, or any of the
    button types.

    Depending on the browser, the user may see a custom color palette
    suggested, tic marks along a range, or even an input that opens like
    a [`<select>`](select) but allows for non-listed values. Check out
    the [browser compatibility table](datalist#browser_compatibility)
    for the other input types.

    See the [`<datalist>`](datalist) element.

[`max`](#max)

:   Valid for `date`, `month`, `week`, `time`, `datetime-local`,
    `number`, and `range`, it defines the greatest value in the range of
    permitted values. If the [`value`](#value) entered into the element
    exceeds this, the element fails [constraint
    validation](../constraint_validation). If the value of the `max`
    attribute isn\'t a number, then the element has no maximum value.

    There is a special case: if the data type is periodic (such as for
    dates or times), the value of `max` may be lower than the value of
    `min`, which indicates that the range may wrap around; for example,
    this allows you to specify a time range from 10 PM to 4 AM.

[`maxlength`](#maxlength)

:   Valid for `text`, `search`, `url`, `tel`, `email`, and `password`,
    it defines the maximum string length (measured in UTF-16 code units)
    that the user can enter into the field. This must be an integer
    value of 0 or higher. If no `maxlength` is specified, or an invalid
    value is specified, the field has no maximum length. This value must
    also be greater than or equal to the value of `minlength`.

    The input will fail [constraint
    validation](../constraint_validation) if the length of the text
    entered into the field is greater than `maxlength` UTF-16 code units
    long. By default, browsers prevent users from entering more
    characters than allowed by the `maxlength` attribute. See
    [Client-side validation](#client-side_validation) for more
    information.

[`min`](#min)

:   Valid for `date`, `month`, `week`, `time`, `datetime-local`,
    `number`, and `range`, it defines the most negative value in the
    range of permitted values. If the [`value`](#value) entered into the
    element is less than this, the element fails [constraint
    validation](../constraint_validation). If the value of the `min`
    attribute isn\'t a number, then the element has no minimum value.

    This value must be less than or equal to the value of the `max`
    attribute. If the `min` attribute is present but is not specified or
    is invalid, no `min` value is applied. If the `min` attribute is
    valid and a non-empty value is less than the minimum allowed by the
    `min` attribute, constraint validation will prevent form submission.
    See [Client-side validation](#client-side_validation) for more
    information.

    There is a special case: if the data type is periodic (such as for
    dates or times), the value of `max` may be lower than the value of
    `min`, which indicates that the range may wrap around; for example,
    this allows you to specify a time range from 10 PM to 4 AM.

[`minlength`](#minlength)

:   Valid for `text`, `search`, `url`, `tel`, `email`, and `password`,
    it defines the minimum string length (measured in UTF-16 code units)
    that the user can enter into the entry field. This must be a
    non-negative integer value smaller than or equal to the value
    specified by `maxlength`. If no `minlength` is specified, or an
    invalid value is specified, the input has no minimum length.

    The input will fail [constraint
    validation](../constraint_validation) if the length of the text
    entered into the field is fewer than `minlength` UTF-16 code units
    long, preventing form submission. See [Client-side
    validation](#client-side_validation) for more information.

[`multiple`](#multiple)

:   The Boolean `multiple` attribute, if set, means the user can enter
    comma separated email addresses in the email widget or can choose
    more than one file with the `file` input. See the
    [email](input/email) and [file](input/file) input type.

[`name`](#name)

:   A string specifying a name for the input control. This name is
    submitted along with the control\'s value when the form data is
    submitted.

    Consider the `name` a required attribute (even though it\'s not). If
    an input has no `name` specified, or `name` is empty, the input\'s
    value is not submitted with the form! (Disabled controls, unchecked
    radio buttons, unchecked checkboxes, and reset buttons are also not
    sent.)

    There are two special cases:

    1.  `_charset_` : If used as the name of an `<input>` element of
        type [hidden](input/hidden), the input\'s `value` is
        automatically set by the [user
        agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
        to the character encoding being used to submit the form.
    2.  `isindex`: For historical reasons, the name
        [`isindex`](https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#attr-fe-name)
        is not allowed.

    The [`name`](#name) attribute creates a unique behavior for radio
    buttons.

    Only one radio button in a same-named group of radio buttons can be
    checked at a time. Selecting any radio button in that group
    automatically deselects any currently-selected radio button in the
    same group. The value of that one checked radio button is sent along
    with the name if the form is submitted,

    When tabbing into a series of same-named group of radio buttons, if
    one is checked, that one will receive focus. If they aren\'t grouped
    together in source order, if one of the group is checked, tabbing
    into the group starts when the first one in the group is
    encountered, skipping all those that aren\'t checked. In other
    words, if one is checked, tabbing skips the unchecked radio buttons
    in the group. If none are checked, the radio button group receives
    focus when the first button in the same name group is reached.

    Once one of the radio buttons in a group has focus, using the arrow
    keys will navigate through all the radio buttons of the same name,
    even if the radio buttons are not grouped together in the source
    order.

    When an input element is given a `name`, that name becomes a
    property of the owning form element\'s
    [`HTMLFormElement.elements`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements)
    property. If you have an input whose `name` is set to `guest` and
    another whose `name` is `hat-size`, the following code can be used:

     
    [js]

    ```js
    let form = document.querySelector("form");

    let guestName = form.elements.guest;
    let hatSize = form.elements["hat-size"];
    ```
    

    When this code has run, `guestName` will be the
    [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
    for the `guest` field, and `hatSize` the object for the `hat-size`
    field.

     
    **Warning:** Avoid giving form elements a `name` that corresponds to
    a built-in property of the form, since you would then override the
    predefined property or method with this reference to the
    corresponding input.

[`pattern`](#pattern)

:   Valid for `text`, `search`, `url`, `tel`, `email`, and `password`,
    the `pattern` attribute defines a regular expression that the
    input\'s [`value`](#value) must match in order for the value to pass
    [constraint validation](../constraint_validation). It must be a
    valid JavaScript regular expression, as used by the
    [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp)
    type, and as documented in our [guide on regular
    expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions);
    the `'u'` flag is specified when compiling the regular expression,
    so that the pattern is treated as a sequence of Unicode code points,
    instead of as
    [ASCII](https://developer.mozilla.org/en-US/docs/Glossary/ASCII). No
    forward slashes should be specified around the pattern text.

    If the `pattern` attribute is present but is not specified or is
    invalid, no regular expression is applied and this attribute is
    ignored completely. If the pattern attribute is valid and a
    non-empty value does not match the pattern, constraint validation
    will prevent form submission.

     
    **Note:** If using the `pattern` attribute, inform the user about
    the expected format by including explanatory text nearby. You can
    also include a [`title`](#title) attribute to explain what the
    requirements are to match the pattern; most browsers will display
    this title as a tooltip. The visible explanation is required for
    accessibility. The tooltip is an enhancement.
    

    See [Client-side validation](#client-side_validation) for more
    information.

[`placeholder`](#placeholder)

:   Valid for `text`, `search`, `url`, `tel`, `email`, `password`, and
    `number`, the `placeholder` attribute provides a brief hint to the
    user as to what kind of information is expected in the field. It
    should be a word or short phrase that provides a hint as to the
    expected type of data, rather than an explanation or prompt. The
    text *must not* include carriage returns or line feeds. So for
    example if a field is expected to capture a user\'s first name, and
    its label is \"First Name\", a suitable placeholder might be \"e.g.
    Mustafa\".

    **Note:** The `placeholder` attribute is not as semantically useful
    as other ways to explain your form, and can cause unexpected
    technical issues with your content. See [Labels](#labels) for more
    information.

[`popovertarget`](#popovertarget)

:   Turns an `<input type="button">` element into a popover control
    button; takes the ID of the popover element to control as its value.
    See the [Popover
    API](https://developer.mozilla.org/en-US/docs/Web/API/Popover_API)
    landing page for more details.

[`popovertargetaction`](#popovertargetaction)

:   Specifies the action to be performed on a popover element being
    controlled by a control `<input type="button">`. Possible values
    are:

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

[`readonly`](#readonly)

:   A Boolean attribute which, if present, indicates that the user
    should not be able to edit the value of the input. The `readonly`
    attribute is supported by the `text`, `search`, `url`, `tel`,
    `email`, `date`, `month`, `week`, `time`, `datetime-local`,
    `number`, and `password` input types.

    See the [HTML attribute: `readonly`](../attributes/readonly) for
    more information.

[`required`](#required)

:   `required` is a Boolean attribute which, if present, indicates that
    the user must specify a value for the input before the owning form
    can be submitted. The `required` attribute is supported by `text`,
    `search`, `url`, `tel`, `email`, `date`, `month`, `week`, `time`,
    `datetime-local`, `number`, `password`, `checkbox`, `radio`, and
    `file` inputs.

    See [Client-side validation](#client-side_validation) and the [HTML
    attribute: `required`](../attributes/required) for more information.

[`size`](#size)

:   Valid for `email`, `password`, `tel`, `url`, and `text`, the `size`
    attribute specifies how much of the input is shown. Basically
    creates same result as setting CSS
    [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width)
    property with a few specialities. The actual unit of the value
    depends on the input type. For `password` and `text`, it is a number
    of characters (or `em` units) with a default value of `20`, and for
    others, it is pixels (or `px` units). CSS `width` takes precedence
    over the `size` attribute.

[`src`](#src)

:   Valid for the `image` input button only, the `src` is string
    specifying the URL of the image file to display to represent the
    graphical submit button. See the [image](input/image) input type.

[`step`](#step)

:   Valid for `date`, `month`, `week`, `time`, `datetime-local`,
    `number`, and `range`, the [`step`](../attributes/step) attribute is
    a number that specifies the granularity that the value must adhere
    to.

    If not explicitly included:

    -   `step` defaults to 1 for `number` and `range`.
    -   Each date/time input type has a default `step` value appropriate
        for the type; see the individual input pages:
        [`date`](input/date#step),
        [`datetime-local`](input/datetime-local#step),
        [`month`](input/month#step), [`time`](input/time#step), and
        [`week`](input/week#step).

    The value must be a positive number---integer or float---or the
    special value `any`, which means no stepping is implied, and any
    value is allowed (barring other constraints, such as [`min`](#min)
    and [`max`](#max)).

    If `any` is not explicitly set, valid values for the `number`,
    date/time input types, and `range` input types are equal to the
    basis for stepping --- the [`min`](#min) value and increments of the
    step value, up to the [`max`](#max) value, if specified.

    For example, if you have `<input type="number" min="10" step="2">`,
    then any even integer, `10` or greater, is valid. If omitted,
    `<input type="number">`, any integer is valid, but floats (like
    `4.2`) are not valid, because `step` defaults to `1`. For `4.2` to
    be valid, `step` would have had to be set to `any`, 0.1, 0.2, or any
    the `min` value would have had to be a number ending in `.2`, such
    as `<input type="number" min="-5.2">`

     
    **Note:** When the data entered by the user doesn\'t adhere to the
    stepping configuration, the value is considered invalid in
    constraint validation and will match the `:invalid` pseudoclass.
    

    See [Client-side validation](#client-side_validation) for more
    information.

[`tabindex`](#tabindex)

:   Global attribute valid for all elements, including all the input
    types, an integer attribute indicating if the element can take input
    focus (is focusable), if it should participate to sequential
    keyboard navigation. As all input types except for input of type
    hidden are focusable, this attribute should not be used on form
    controls, because doing so would require the management of the focus
    order for all elements within the document with the risk of harming
    usability and accessibility if done incorrectly.

[`title`](#title)

:   Global attribute valid for all elements, including all input types,
    containing a text representing advisory information related to the
    element it belongs to. Such information can typically, but not
    necessarily, be presented to the user as a tooltip. The title should
    NOT be used as the primary explanation of the purpose of the form
    control. Instead, use the [`<label>`](label) element with a `for`
    attribute set to the form control\'s [`id`](#id) attribute. See
    [Labels](#labels) below.

[`type`](#type)

:   A string specifying the type of control to render. For example, to
    create a checkbox, a value of `checkbox` is used. If omitted (or an
    unknown value is specified), the input type `text` is used, creating
    a plaintext input field.

    Permitted values are listed in [Input types](#input_types) above.

[`value`](#value)

:   The input control\'s value. When specified in the HTML, this is the
    initial value, and from then on it can be altered or retrieved at
    any time using JavaScript to access the respective
    [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
    object\'s `value` property. The `value` attribute is always
    optional, though should be considered mandatory for `checkbox`,
    `radio`, and `hidden`.

[`width`](#width)

:   Valid for the `image` input button only, the `width` is the width of
    the image file to display to represent the graphical submit button.
    See the [image](input/image) input type.

### Non-standard attributes

The following non-standard attributes are also available on some
browsers. As a general rule, you should avoid using them unless it
can\'t be helped.

  Attribute                                        Description
  ------------------------------------------------ ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [`autocapitalize`](#autocapitalize)              A string indicating how auto-capitalization should be applied to the content of text elements. **Safari only.**
  [`autocorrect`](#autocorrect)                    A string indicating whether autocorrect is `on` or `off`. **Safari only.**
  [`incremental`](#incremental)                    Whether or not to send repeated [`search`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/search_event) events to allow updating live search results while the user is still editing the value of the field. **WebKit and Blink only (Safari, Chrome, Opera, etc.).**
  `mozactionhint` [Deprecated] key while editing the field; this is used to determine an appropriate label for that key on a virtual keyboard. **Since this attribute is deprecated, use [`enterkeyhint`](../global_attributes/enterkeyhint) instead.**
  [`orient`](#orient)                              Sets the orientation of the range slider. **Firefox only**.
  [`results`](#results)                            The maximum number of items that should be displayed in the drop-down list of previous search queries. **Safari only.**
  [`webkitdirectory`](#webkitdirectory)            A Boolean indicating whether to only allow the user to choose a directory (or directories, if [`multiple`](#multiple) is also present)

[`autocapitalize`](#autocapitalize) [Non-standard]

:   (Safari only). A string which indicates how auto-capitalization
    should be applied while the user is editing this field. Permitted
    values are:

    [`none`](#none)

    :   Do not automatically capitalize any text

    [`sentences`](#sentences)

    :   Automatically capitalize the first character of each sentence.

    [`words`](#words)

    :   Automatically capitalize the first character of each word.

    [`characters`](#characters)

    :   Automatically capitalize every character.

[`autocorrect`](#autocorrect) [Non-standard]

:   (Safari only). A string which indicates whether to activate
    automatic correction while the user is editing this field. Permitted
    values are:

    [`on`](#on)

    :   Enable automatic correction of typos, as well as processing of
        text substitutions if any are configured.

    [`off`](#off)

    :   Disable automatic correction and text substitutions.

[`incremental`](#incremental) [Non-standard]

:   The Boolean attribute `incremental` is a WebKit and Blink extension
    (so supported by Safari, Opera, Chrome, etc.) which, if present,
    tells the [user
    agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
    to process the input as a live search. As the user edits the value
    of the field, the user agent sends
    [`search`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/search_event)
    events to the
    [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
    object representing the search box. This allows your code to update
    the search results in real time as the user edits the search.

    If `incremental` is not specified, the
    [`search`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/search_event)
    event is only sent when the user explicitly initiates a search (such
    as by pressing the [Enter] key while editing
    the field).

    The `search` event is rate-limited so that it is not sent more
    frequently than an implementation-defined interval.

[`orient`](#orient) [Non-standard]

:   Similar to the -moz-orient non-standard CSS property impacting the
    [`<progress>`](progress) and [`<meter>`](meter) elements, the
    `orient` attribute defines the orientation of the range slider.
    Values include `horizontal`, meaning the range is rendered
    horizontally, and `vertical`, where the range is rendered
    vertically.

[`results`](#results) [Non-standard]

:   The `results` attribute---supported only by Safari---is a numeric
    value that lets you override the maximum number of entries to be
    displayed in the [`<input>`](input) element\'s natively-provided
    drop-down menu of previous search queries.

    The value must be a non-negative decimal number. If not provided, or
    an invalid value is given, the browser\'s default maximum number of
    entries is used.

[`webkitdirectory`](#webkitdirectory) [Non-standard]

:   The Boolean `webkitdirectory` attribute, if present, indicates that
    only directories should be available to be selected by the user in
    the file picker interface. See
    [`HTMLInputElement.webkitdirectory`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/webkitdirectory)
    for additional details and examples.

    Though originally implemented only for WebKit-based browsers,
    `webkitdirectory` is also usable in Microsoft Edge as well as
    Firefox 50 and later. However, even though it has relatively broad
    support, it is still not standard and should not be used unless you
    have no alternative.

Methods
-------

The following methods are provided by the
[`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
interface which represents `<input>` elements in the DOM. Also available
are those methods specified by the parent interfaces,
[`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement),
[`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element),
[`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node), and
[`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget).

[`checkValidity()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/checkValidity)

:   Returns `true` if the element\'s value passes validity checks;
    otherwise, returns `false` and fires an
    [`invalid`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/invalid_event)
    event at the element.

[`reportValidity()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/reportValidity)

:   Returns `true` if the element\'s value passes validity checks;
    otherwise, returns `false`, fires an
    [`invalid`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/invalid_event)
    event at the element, and (if the event isn\'t canceled) reports the
    problem to the user.

[`select()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select)

:   Selects the entire content of the `<input>` element, if the
    element\'s content is selectable. For elements with no selectable
    text content (such as a visual color picker or calendar date input),
    this method does nothing.

[`setCustomValidity()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setCustomValidity)

:   Sets a custom message to display if the input element\'s value
    isn\'t valid.

[`setRangeText()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setRangeText)

:   Sets the contents of the specified range of characters in the input
    element to a given string. A `selectMode` parameter is available to
    allow controlling how the existing content is affected.

[`setSelectionRange()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setSelectionRange)

:   Selects the specified range of characters within a textual input
    element. Does nothing for inputs which aren\'t presented as text
    input fields.

[`showPicker()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/showPicker)

:   Displays the browser picker for the input element that would
    normally be displayed when the element is selected, but triggered
    from a button press or other user interaction.

[`stepDown()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepDown)

:   Decrements the value of a numeric input by one, by default, or by
    the specified number of units.

[`stepUp()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepUp)

:   Increments the value of a numeric input by one or by the specified
    number of units.

CSS
---

Inputs, being replaced elements, have a few features not applicable to
non form elements. There are CSS selectors that can specifically target
form controls based on their UI features, also known as UI
pseudo-classes. The input element can also be targeted by type with
attribute selectors. There are some properties that are especially
useful as well.

### UI pseudo-classes

  Pseudo-class                                                                                  Description
  --------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [`:enabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:enabled)                       Any currently enabled element that can be activated (selected, clicked on, typed into, etc.) or accept focus and also has a disabled state, in which it can\'t be activated or accept focus.
  [`:disabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled)                     Any currently disabled element that has an enabled state, meaning it otherwise could be activated (selected, clicked on, typed into, etc.) or accept focus were it not disabled.
  [`:read-only`](https://developer.mozilla.org/en-US/docs/Web/CSS/:read-only)                   Element not editable by the user
  [`:read-write`](https://developer.mozilla.org/en-US/docs/Web/CSS/:read-write)                 Element that is editable by the user.
  [`:placeholder-shown`](https://developer.mozilla.org/en-US/docs/Web/CSS/:placeholder-shown)   Element that is currently displaying [`placeholder` text](#placeholder), including `<input>` and [`<textarea>`](textarea) elements with the [`placeholder`](#placeholder) attribute present that has, as yet, no value.
  [`:default`](https://developer.mozilla.org/en-US/docs/Web/CSS/:default)                       Form elements that are the default in a group of related elements. Matches [checkbox](input/checkbox) and [radio](input/radio) input types that were checked on page load or render.
  [`:checked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:checked)                       Matches [checkbox](input/checkbox) and [radio](input/radio) input types that are currently checked (and the ([`<option>`](option) in a [`<select>`](select) that is currently selected).
  [`:indeterminate`](https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate)           [checkbox](input/checkbox) elements whose indeterminate property is set to true by JavaScript, [radio](input/radio) elements, when all radio buttons with the same name value in the form are unchecked, and [`<progress>`](progress) elements in an indeterminate state
  [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid)                           Form controls that can have constraint validation applied and are currently valid.
  [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)                       Form controls that have constraint validation applied and are currently not valid. Matches a form control whose value doesn\'t match the constraints set on it by its attributes, such as [`required`](#required), [`pattern`](#pattern), [`step`](#step) and [`max`](#max).
  [`:in-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:in-range)                     A non-empty input whose current value is within the range limits specified by the [`min`](#min) and [`max`](#max) attributes and the [`step`](#step).
  [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)             A non-empty input whose current value is NOT within the range limits specified by the [`min`](#min) and [`max`](#max) attributes or does not adhere to the [`step`](#step) constraint.
  [`:required`](https://developer.mozilla.org/en-US/docs/Web/CSS/:required)                     `<input>`, [`<select>`](select), or [`<textarea>`](textarea) element that has the [`required`](#required) attribute set on it. Only matches elements that can be required. The attribute included on a non-requirable element will not make for a match.
  [`:optional`](https://developer.mozilla.org/en-US/docs/Web/CSS/:optional)                     `<input>`, [`<select>`](select), or [`<textarea>`](textarea) element that does NOT have the [`required`](#required) attribute set on it. Does not match elements that can\'t be required.
  [`:blank`](https://developer.mozilla.org/en-US/docs/Web/CSS/:blank)                           `<input>` and [`<textarea>`](textarea) elements that currently have no value.
  [`:user-invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:user-invalid)             Similar to `:invalid`, but is activated on blur. Matches invalid input but only after the user interaction, such as by focusing on the control, leaving the control, or attempting to submit the form containing the invalid control.

  :  Captions super relevant to the `<input>` element:

#### Pseudo-classes example

We can style a checkbox label based on whether the checkbox is checked
or not. In this example, we are styling the
[`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) and
[`font-weight`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight)
of the [`<label>`](label) that comes immediately after a checked input.
We haven\'t applied any styles if the `input` is not checked.

[css]

```css
input:checked + label {
  color: red;
  font-weight: bold;
}

```

### Attribute selectors

It is possible to target different types of form controls based on their
[`type`](#type) using [attribute
selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Attribute_selectors).
CSS attribute selectors match elements based on either just the presence
of an attribute or the value of a given attribute.

[css]

```css
/*matches a password input*/
input[type="password"] {
}

/*matches a form control whose valid values are limited to a range of values*/
input[min][max] {
}

/*matches a form control with a pattern attribute*/
input[pattern] {
}

```

### ::placeholder

By default, the appearance of placeholder text is a translucent or light
gray. The
[`::placeholder`](https://developer.mozilla.org/en-US/docs/Web/CSS/::placeholder)
pseudo-element is the input\'s [`placeholder` text](#placeholder). It
can be styled with a limited subset of CSS properties.

[css]

```css
::placeholder {
  color: blue;
}

```

Only the subset of CSS properties that apply to the
[`::first-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-line)
pseudo-element can be used in a rule using `::placeholder` in its
selector.

### appearance

The
[`appearance`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance)
property enables the displaying of (almost) any element as a
platform-native style based on the operating system\'s theme as well as
the removal of any platform-native styling with the `none` value.

You could make a `<div>` look like a radio button with
`div {appearance: radio;}` or a radio look like a checkbox with
`[type="radio"] {appearance: checkbox;}`, but don\'t.

Setting `appearance: none` removes platform native borders, but not
functionality.

### caret-color

A property specific to text entry-related elements is the CSS
[`caret-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color)
property, which lets you set the color used to draw the text input
caret:

#### HTML

[html]

```html
<label for="textInput">Note the red caret:</label>
<input id="textInput" class="custom" size="32" />
```

#### CSS

[css]

```css
input.custom {
  caret-color: red;
  font:
    16px "Helvetica",
    "Arial",
    "sans-serif";
}

```

#### Result

### object-position and object-fit

In certain cases (typically involving non-textual inputs and specialized
interfaces), the `<input>` element is a [replaced
element](https://developer.mozilla.org/en-US/docs/Web/CSS/Replaced_element).
When it is, the position and size of the element\'s size and positioning
within its frame can be adjusted using the CSS
[`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position)
and
[`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit)
properties

### Styling

For more information about adding color to elements in HTML, see:

- [Applying color to HTML elements using
    CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors/Applying_color).

Also see:

- [Styling HTML
    forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Styling_web_forms)
- [Advanced styling for HTML
    forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling)
    and
- the [compatibility table of CSS
    properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls).

Additional features
-------------------

### Labels

Labels are needed to associate assistive text with an `<input>`. The
[`<label>`](label) element provides explanatory information about a form
field that is *always* appropriate (aside from any layout concerns you
have). It\'s never a bad idea to use a `<label>` to explain what should
be entered into an `<input>` or [`<textarea>`](textarea).

#### Associated labels

The semantic pairing of `<input>` and `<label>` elements is useful for
assistive technologies such as screen readers. By pairing them using the
`<label>`\'s [`for`](label#for) attribute, you bond the label to the
input in a way that lets screen readers describe inputs to users more
precisely.

It does not suffice to have plain text adjacent to the `<input>`
element. Rather, usability and accessibility requires the inclusion of
either implicit or explicit [`<label>`](label):

[html]

```html
<!-- inaccessible -->
<p>Enter your name: <input id="name" type="text" size="30" /></p>

<!-- implicit label -->
<p>
  <label>Enter your name: <input id="name" type="text" size="30" /></label>
</p>

<!-- explicit label -->
<p>
  <label for="name">Enter your name: </label>
  <input id="name" type="text" size="30" />
</p>
```

The first example is inaccessible: no relationship exists between the
prompt and the `<input>` element.

In addition to an accessible name, the label provides a larger \'hit\'
area for mouse and touch screen users to click on or touch. By pairing a
`<label>` with an `<input>`, clicking on either one will focus the
`<input>`. If you use plain text to \"label\" your input, this won\'t
happen. Having the prompt part of the activation area for the input is
helpful for people with motor control conditions.

As web developers, it\'s important that we never assume that people will
know all the things that we know. The diversity of people using the
web---and by extension your website---practically guarantees that some
of your site\'s visitors will have some variation in thought processes
and/or circumstances that leads them to interpret your forms very
differently from you without clear and properly-presented labels.

#### Placeholders are not accessible

The [`placeholder`](#placeholder) attribute lets you specify text that
appears within the `<input>` element\'s content area itself when it is
empty. The placeholder should never be required to understand your
forms. It is not a label, and should not be used as a substitute,
because it isn\'t. The placeholder is used to provide a hint as to what
an inputted value should look like, not an explanation or prompt.

Not only is the placeholder not accessible to screen readers, but once
the user enters any text into the form control, or if the form control
already has a value, the placeholder disappears. Browsers with automatic
page translation features may skip over attributes when translating,
meaning the `placeholder` may not get translated.

**Note:** Don\'t use the [`placeholder`](#placeholder) attribute if you
can avoid it. If you need to label an `<input>` element, use the
[`<label>`](label) element.

### Client-side validation

**Warning:** Client-side validation is useful, but it does *not*
guarantee that the server will receive valid data. If the data must be
in a specific format, *always* verify it also on the server-side, and
return a [`400` HTTP
response](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/400)
if the format is invalid.

In addition to using CSS to style inputs based on the
[`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid) or
[`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)
UI states based on the current state of each input, as noted in the [UI
pseudo-classes](#ui_pseudo-classes) section above, the browser provides
for client-side validation on (attempted) form submission. On form
submission, if there is a form control that fails constraint validation,
supporting browsers will display an error message on the first invalid
form control; displaying a default message based on the error type, or a
message set by you.

Some input types and other attributes place limits on what values are
valid for a given input. For example,
`<input type="number" min="2" max="10" step="2">` means only the number
2, 4, 6, 8, or 10 are valid. Several errors could occur, including a
`rangeUnderflow` error if the value is less than 2, `rangeOverflow` if
greater than 10, `stepMismatch` if the value is a number between 2 and
10, but not an even integer (does not match the requirements of the
`step` attribute), or `typeMismatch` if the value is not a number.

For the input types whose domain of possible values is periodic (that
is, at the highest possible value, the values wrap back around to the
beginning rather than ending), it\'s possible for the values of the
[`max`](#max) and [`min`](#min) properties to be reversed, which
indicates that the range of permitted values starts at `min`, wraps
around to the lowest possible value, then continues on until `max` is
reached. This is particularly useful for dates and times, such as when
you want to allow the range to be from 8 PM to 8 AM:

[html]

```html
<input type="time" min="20:00" max="08:00" name="overnight" />
```

Specific attributes and their values can lead to a specific error
[`ValidityState`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState):

  Attribute                   Relevant property                                                                                                   Description
  --------------------------- ------------------------------------------------------------------------------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [`max`](#max)               [`validityState.rangeOverflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeOverflow)       Occurs when the value is greater than the maximum value as defined by the `max` attribute
  [`maxlength`](#maxlength)   [`validityState.tooLong`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooLong)                   Occurs when the number of characters is greater than the number allowed by the `maxlength` property
  [`min`](#min)               [`validityState.rangeUnderflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeUnderflow)     Occurs when the value is less than the minimum value as defined by the `min` attribute
  [`minlength`](#minlength)   [`validityState.tooShort`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooShort)                 Occurs when the number of characters is less than the number required by the `minlength` property
  [`pattern`](#pattern)       [`validityState.patternMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/patternMismatch)   Occurs when a pattern attribute is included with a valid regular expression and the `value` does not match it.
  [`required`](#required)     [`validityState.valueMissing`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/valueMissing)         Occurs when the `required` attribute is present but the value is `null` or radio or checkbox is not checked.
  [`step`](#step)             [`validityState.stepMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/stepMismatch)         The value doesn\'t match the step increment. Increment default is `1`, so only integers are valid on`type="number"` is step is not included. `step="any"` will never throw this error.
  [`type`](#type)             [`validityState.typeMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/typeMismatch)         Occurs when the value is not of the correct type, for example an email does not contain an `@` or a url doesn\'t contain a protocol.

  :  Validity object errors depend on the [`<input>`](input) attributes
  and their values:

If a form control doesn\'t have the `required` attribute, no value, or
an empty string, is not invalid. Even if the above attributes are
present, with the exception of `required`, an empty string will not lead
to an error.

We can set limits on what values we accept, and supporting browsers will
natively validate these form values and alert the user if there is a
mistake when the form is submitted.

In addition to the errors described in the table above, the
`validityState` interface contains the `badInput`, `valid`, and
`customError` boolean readonly properties. The validity object includes:

- [`validityState.valueMissing`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/valueMissing)
- [`validityState.typeMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/typeMismatch)
- [`validityState.patternMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/patternMismatch)
- [`validityState.tooLong`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooLong)
- [`validityState.tooShort`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooShort)
- [`validityState.rangeUnderflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeUnderflow)
- [`validityState.rangeOverflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeOverflow)
- [`validityState.stepMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/stepMismatch)
- [`validityState.badInput`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/badInput)
- [`validityState.valid`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState)
- [`validityState.customError`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState)

For each of these Boolean properties, a value of `true` indicates that
the specified reason validation may have failed is true, with the
exception of the `valid` property, which is `true` if the element\'s
value obeys all constraints.

If there is an error, supporting browsers will both alert the user and
prevent the form from being submitted. A word of caution: if a custom
error is set to a truthy value (anything other than the empty string or
`null`), the form will be prevented from being submitted. If there is no
custom error message, and none of the other properties return true,
`valid` will be true, and the form can be submitted.

[js]

```js
function validate(input) {
  let validityState_object = input.validity;
  if (validityState_object.valueMissing) {
    input.setCustomValidity("A value is required");
  } else if (validityState_object.rangeUnderflow) {
    input.setCustomValidity("Your value is too low");
  } else if (validityState_object.rangeOverflow) {
    input.setCustomValidity("Your value is too high");
  } else {
    input.setCustomValidity("");
  }
}
```

The last line, setting the custom validity message to the empty string
is vital. If the user makes an error, and the validity is set, it will
fail to submit, even if all the values are valid, until the message is
`null`.

#### Custom validation error example

If you want to present a custom error message when a field fails to
validate, you need to use the [Constraint Validation
API](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#validating_forms_using_javascript)
available on `<input>` (and related) elements. Take the following form:

[html]

```html
<form>
  <label for="name">Enter username (upper and lowercase letters): </label>
  <input type="text" name="name" id="name" required pattern="[A-Za-z]+" />
  <button>Submit</button>
</form>
```

The basic HTML form validation features will cause this to produce a
default error message if you try to submit the form with either no valid
filled in, or a value that does not match the `pattern`.

If you wanted to instead display custom error messages, you could use
JavaScript like the following:

[js]

```js
const nameInput = document.querySelector("input");

nameInput.addEventListener("input", () => {
  nameInput.setCustomValidity("");
  nameInput.checkValidity();
});

nameInput.addEventListener("invalid", () => {
  if (nameInput.value === "") {
    nameInput.setCustomValidity("Enter your username!");
  } else {
    nameInput.setCustomValidity(
      "Usernames can only contain upper and lowercase letters. Try again!",
    );
  }
});
```

The example renders like so:

In brief:

- We check the valid state of the input element every time its value
    is changed by running the `checkValidity()` method via the `input`
    event handler.
- If the value is invalid, an `invalid` event is raised, and the
    `invalid` event handler function is run. Inside this function we
    work out whether the value is invalid because it is empty, or
    because it doesn\'t match the pattern, using an `if ()` block, and
    set a custom validity error message.
- As a result, if the input value is invalid when the submit button is
    pressed, one of the custom error messages will be shown.
- If it is valid, it will submit as you\'d expect. For this to happen,
    the custom validity has to be cancelled, by invoking
    `setCustomValidity()` with an empty string value. We therefore do
    this every time the `input` event is raised. If you don\'t do this,
    and a custom validity was previously set, the input will register as
    invalid, even if it currently contains a valid value on submission.

**Note:** Always validate input constraints both client side and server
side. Constraint validation doesn\'t remove the need for validation on
the *server side*. Invalid values can still be sent by older browsers or
by bad actors.

**Note:** Firefox supported a proprietary error attribute ---
`x-moz-errormessage` --- for many versions, which allowed you set custom
error messages in a similar way. This has been removed as of version 66
(see [Firefox bug 1513890](https://bugzil.la/1513890)).

### Localization

The allowed inputs for certain `<input>` types depend on the locale. In
some locales, 1,000.00 is a valid number, while in other locales the
valid way to enter this number is 1.000,00.

Firefox uses the following heuristics to determine the locale to
validate the user\'s input (at least for `type="number"`):

- Try the language specified by a `lang`/`xml:lang` attribute on the
    element or any of its parents.
- Try the language specified by any `Content-Language` HTTP header.
    Or,
- If none specified, use the browser\'s locale.

### Technical summary

+-----------------------------------+-----------------------------------+
| [Content                          | [Flow                             |
| c                                 | content](../                      |
| ategories](../content_categories) | content_categories#flow_content), |
|                                   | listed, submittable, resettable,  |
|                                   | form-associated element,          |
|                                   | [phrasing                         |
|                                   | content](../cont                  |
|                                   | ent_categories#phrasing_content). |
|                                   | If the [`type`](#type) is not     |
|                                   | `hidden`, then labelable element, |
|                                   | palpable content.                 |
+-----------------------------------+-----------------------------------+
| Permitted content                 | None; it is a [void               |
|                                   | element                           |
|                                   | ](https://developer.mozilla.org/e>> |
|                                   | n-US/docs/Glossary/Void_element). |
+-----------------------------------+-----------------------------------+
| Tag omission                      | Must have a start tag and must    |
|                                   | not have an end tag.              |
+-----------------------------------+-----------------------------------+
| Permitted parents                 | Any element that accepts          |
|                                   | [phrasing                         |
|                                   | content](../cont                  |
|                                   | ent_categories#phrasing_content). |
+-----------------------------------+-----------------------------------+
| Implicit ARIA role                | -   `type=button`: `button`       |
|                                   | -   `type=checkbox`: `checkbox`   |
|                                   | -   `type=email`                  |
|                                   |     -   with no `list` attribute: |
|                                   |         `textbox`                 |
|                                   |     -   with `list` attribute:    |
|                                   |                                   |
|                                   |   [`combobox`](https://developer>>. |
|                                   | mozilla.org/en-US/docs/Web/Access |
|                                   | ibility/ARIA/Roles/combobox_role) |
|                                   | -   `type=image`: `button`        |
|                                   | -   `type=number`:                |
|                                   |     [`|
|                                   | spinbutton`](https://developer.mo>> |
|                                   | zilla.org/en-US/docs/Web/Accessib |
|                                   | ility/ARIA/Roles/spinbutton_role) |
|                                   | -   `type=radio`:                 |
|                                   |     [`radio`](https://develop>>     |
|                                   | er.mozilla.org/en-US/docs/Web/Acc |
|                                   | essibility/ARIA/Roles/radio_role) |
|                                   | -   `type=range`:                 |
|                                   |     [`slider`](https://develope>>   |
|                                   | r.mozilla.org/en-US/docs/Web/Acce |
|                                   | ssibility/ARIA/Roles/slider_role) |
|                                   | -   `type=reset`: `button`        |
|                                   | -   `type=search`                 |
|                                   |     -   with no `list` attribute: |
|                                   |                                   |
|                                   | [`searchbox`](https://developer.m>> |
|                                   | ozilla.org/en-US/docs/Web/Accessi |
|                                   | bility/ARIA/Roles/searchbox_role) |
|                                   |     -   with `list`               |
|                                   |         attribut                  |
|                                   | e:[`combobox`](https://developer>>. |
|                                   | mozilla.org/en-US/docs/Web/Access |
|                                   | ibility/ARIA/Roles/combobox_role) |
|                                   | -   `type=submit`: `button`       |
|                                   | -   `type=tel`                    |
|                                   |     -   with no `list` attribute: |
|                                   |         `textbox`                 |
|                                   |     -   with `list` attribute:    |
|                                   |                                   |
|                                   |   [`combobox`](https://developer>>. |
|                                   | mozilla.org/en-US/docs/Web/Access |
|                                   | ibility/ARIA/Roles/combobox_role) |
|                                   | -   `type=text`                   |
|                                   |     -   with no `list` attribute: |
|                                   |         `textbox`                 |
|                                   |     -   with `list` attribute:    |
|                                   |                                   |
|                                   |   [`combobox`](https://developer>>. |
|                                   | mozilla.org/en-US/docs/Web/Access |
|                                   | ibility/ARIA/Roles/combobox_role) |
|                                   | -   `type=url`                    |
|                                   |     -   with no `list` attribute: |
|                                   |         `textbox`                 |
|                                   |     -   with `list` attribute:    |
|                                   |                                   |
|                                   |   [`combobox`](https://developer>>. |
|                                   | mozilla.org/en-US/docs/Web/Access |
|                                   | ibility/ARIA/Roles/combobox_role) |
|                                   | -   `typ                          |
|                                   | e=color|date|datetime-local|file| |
|                                   | hidden|month|password|time|week`: |
|                                   |     [no corresponding             |
|                                   |                                   |
|                                   |  role](https://www.w3.org/TR/html>> |
|                                   | -aria/#dfn-no-corresponding-role) |
+-----------------------------------+-----------------------------------+
| Permitted ARIA roles              | -   `type=button`:                |
|                                   |                                   |
|                                   |  [`checkbox`](https://developer.m>> |
|                                   | ozilla.org/en-US/docs/Web/Accessi |
|                                   | bility/ARIA/Roles/checkbox_role), |
|                                   |                                   |
|                                   |  [`combobox`](https://developer.m>> |
|                                   | ozilla.org/en-US/docs/Web/Accessi |
|                                   | bility/ARIA/Roles/combobox_role), |
|                                   |     [`link`](https://develop>>      |
|                                   | er.mozilla.org/en-US/docs/Web/Acc |
|                                   | essibility/ARIA/Roles/link_role), |
|                                   |                                   |
|                                   |  [`menuitem`](https://developer.m>> |
|                                   | ozilla.org/en-US/docs/Web/Accessi |
|                                   | bility/ARIA/Roles/menuitem_role), |
|                                   |     [`menuitemcheck               |
|                                   | box`](https://developer.mozilla.o>> |
|                                   | rg/en-US/docs/Web/Accessibility/A |
|                                   | RIA/Roles/menuitemcheckbox_role), |
|                                   |     [`menuite                     |
|                                   | mradio`](https://developer.mozill>> |
|                                   | a.org/en-US/docs/Web/Accessibilit |
|                                   | y/ARIA/Roles/menuitemradio_role), |
|                                   |     [`option`](https://developer>>  |
|                                   | .mozilla.org/en-US/docs/Web/Acces |
|                                   | sibility/ARIA/Roles/option_role), |
|                                   |     [`radio`](https://develope>>    |
|                                   | r.mozilla.org/en-US/docs/Web/Acce |
|                                   | ssibility/ARIA/Roles/radio_role), |
|                                   |     [`switch`](https://developer>>  |
|                                   | .mozilla.org/en-US/docs/Web/Acces |
|                                   | sibility/ARIA/Roles/switch_role), |
|                                   |     [`tab`](https://devel>>         |
|                                   | oper.mozilla.org/en-US/docs/Web/A |
|                                   | ccessibility/ARIA/Roles/tab_role) |
|                                   | -   `type=checkbox`:              |
|                                   |     [`button`](https://develope>>   |
|                                   | r.mozilla.org/en-US/docs/Web/Acce |
|                                   | ssibility/ARIA/Roles/button_role) |
|                                   |     when used with                |
|                                   |     `aria-pressed`,               |
|                                   |     [`menuitemcheck               |
|                                   | box`](https://developer.mozilla.o>> |
|                                   | rg/en-US/docs/Web/Accessibility/A |
|                                   | RIA/Roles/menuitemcheckbox_role), |
|                                   |     [`option`](https://developer>>  |
|                                   | .mozilla.org/en-US/docs/Web/Acces |
|                                   | sibility/ARIA/Roles/option_role), |
|                                   |     [`switch`](https://develope>>   |
|                                   | r.mozilla.org/en-US/docs/Web/Acce |
|                                   | ssibility/ARIA/Roles/switch_role) |
|                                   | -   `type=image`:                 |
|                                   |     [`link`](https://develop>>      |
|                                   | er.mozilla.org/en-US/docs/Web/Acc |
|                                   | essibility/ARIA/Roles/link_role), |
|                                   |                                   |
|                                   |  [`menuitem`](https://developer.m>> |
|                                   | ozilla.org/en-US/docs/Web/Accessi |
|                                   | bility/ARIA/Roles/menuitem_role), |
|                                   |     [`menuitemcheck               |
|                                   | box`](https://developer.mozilla.o>> |
|                                   | rg/en-US/docs/Web/Accessibility/A |
|                                   | RIA/Roles/menuitemcheckbox_role), |
|                                   |     [`menuite                     |
|                                   | mradio`](https://developer.mozill>> |
|                                   | a.org/en-US/docs/Web/Accessibilit |
|                                   | y/ARIA/Roles/menuitemradio_role), |
|                                   |     [`radio`](https://develope>>    |
|                                   | r.mozilla.org/en-US/docs/Web/Acce |
|                                   | ssibility/ARIA/Roles/radio_role), |
|                                   |     [`switch`](https://develope>>   |
|                                   | r.mozilla.org/en-US/docs/Web/Acce |
|                                   | ssibility/ARIA/Roles/switch_role) |
|                                   | -   `type=radio`:                 |
|                                   |     [`menuit                      |
|                                   | emradio`](https://developer.mozil>> |
|                                   | la.org/en-US/docs/Web/Accessibili |
|                                   | ty/ARIA/Roles/menuitemradio_role) |
|                                   | -   `type=text` with no `list`    |
|                                   |     attribute:                    |
|                                   |                                   |
|                                   |  [`combobox`](https://developer.m>> |
|                                   | ozilla.org/en-US/docs/Web/Accessi |
|                                   | bility/ARIA/Roles/combobox_role), |
|                                   |     [                             |
|                                   | `searchbox`](https://developer.mo>> |
|                                   | zilla.org/en-US/docs/Web/Accessib |
|                                   | ility/ARIA/Roles/searchbox_role), |
|                                   |     [`|
|                                   | spinbutton`](https://developer.mo>> |
|                                   | zilla.org/en-US/docs/Web/Accessib |
|                                   | ility/ARIA/Roles/spinbutton_role) |
|                                   | -   `type=color|date|d            |
|                                   | atetime-local|email|file|hidden|` |
|                                   |     `month|number|password|range| |
|                                   | reset|search|submit|tel|url|week` |
|                                   |     or `text` with `list`         |
|                                   |     attribute: no `role`          |
|                                   |     permitted                     |
+-----------------------------------+-----------------------------------+
| DOM interface                     | [`HTMLInputElement`](             |
|                                   | https://developer.mozilla.org/en->> |
|                                   | US/docs/Web/API/HTMLInputElement) |
+-----------------------------------+-----------------------------------+

Accessibility concerns
----------------------

### Labels

When including inputs, it is an accessibility requirement to add labels
alongside. This is needed so those who use assistive technologies can
tell what the input is for. Also, clicking or touching a label gives
focus to the label\'s associated form control. This improves the
accessibility and usability for sighted users, increases the area a user
can click or touch to activate the form control. This is especially
useful (and even needed) for radio buttons and checkboxes, which are
tiny. For more information about labels in general see [Labels](#labels)
.

The following is an example of how to associate the `<label>` with an
`<input>` element in the above style. You need to give the `<input>` an
`id` attribute. The `<label>` then needs a `for` attribute whose value
is the same as the input\'s `id`.

[html]

```html
<label for="peas">Do you like peas?</label>
<input type="checkbox" name="peas" id="peas" />
```

### Size

Interactive elements such as form input should provide an area large
enough that it is easy to activate them. This helps a variety of people,
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

Specifications
--------------

  --------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-input-element]](https://html.spec.whatwg.org/multipage/input.html#the-input-element)

  --------------------------------------------------------------------------------------------------

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

`input`

1

12

1Before Firefox 89, manipulating the content of `<input>` elements using
`Document.execCommand()` commands requires workarounds (see [bug
1220696](https://bugzil.la/1220696)).

Yes

≤12.1

1

1

18

4Before Firefox 89, manipulating the content of `<input>` elements using
`Document.execCommand()` commands requires workarounds (see [bug
1220696](https://bugzil.la/1220696)).

≤12.1

1

1.0

`accept`

1

12

1

6

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`align`

1

12

1

5.5

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`alt`

1

12

1

5.5

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`capture`

No

No

No

No

No

No

4.4

25

79

14

10

1.5

`checked`

1

12

1

5.5

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`dirname`

17

79

116

No

≤12.1

6

4.4

18

116

≤12.1

6

1.0

`disabled`

1

12

1

5.5

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`form`

1

12

1

5.5

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`formaction`

9

12

4

10

≤12.1

5

3

18

4

≤12.1

4.2

1.0

`formenctype`

9

12

4

10

≤12.1

5

3

18

4

≤12.1

4.2

1.0

`formmethod`

9

12

4

10

≤12.1

5

3

18

4

≤12.1

4.2

1.0

`formnovalidate`

4

12

4

10

≤12.1

5

≤37

18

4

≤12.1

4

1.0

`formtarget`

9

12

4

10

≤12.1

5

3

18

4

≤12.1

4.2

1.0

`list`

20

12

4

10

≤12.1

12.1

4.4.3

25

4

≤12.1

12.2

1.5

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

`maxlength`

1

12

1

5.5

≤12.1

1

4.4

18

4

≤12.1

1

1.0

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

`minlength`

40

17

51

No

27

10.1

40

40

51

27

10.3

4.0

`mozactionhint`

No

No

4--119

No

No

No

No

No

4--119

No

No

No

`multiple`

2

12

3.6

10

≤12.1

4

≤37

18

4

≤12.1

3.2

1.0

`name`

1

12

1

5.5

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`pattern`

4

12

4

10

≤12.1

5

≤37

18

4

≤12.1

4

1.0

`placeholder`

3

12

4

10

≤12.1

4

≤37

18

4

≤12.1

3.2

1.0

`readonly`

1

12

1

5.5

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`src`

1

12

1

5.5

≤12.1

1

4.4

18

4

≤12.1

1

1.0

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

`type_button`

1

12

1

Yes

15

1

4.4

18

4

14

1

1.0

`type_checkbox`

1

12

1

Yes

15

1

4.4

18

4

14

1

1.0

`type_color`

20

14

29

No

12

12.1

4.4

25

27Firefox for Android doesn\'t allow the user to choose a custom color,
only one of the predefined ones.

12

12.2

1.5

`type_date`

20

12

57

No

11

14.1

4.4

25

57

11

5

1.5

`type_datetime-local`

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

`type_email`

5

12

1

10

11

5

4.4

18

4

11

3\[\"Doesn\'t do validation, but instead offers a custom \'email\'
keyboard, which is designed to make entering email addresses easier.\",
\"The custom \'email\' keyboard does not provide a comma key, so users
cannot enter multiple email addresses.\", \"Automatically applies a
default style of `opacity: 0.4` to disable textual `<input>` elements,
including those of type \'email\'. Other major browsers don\'t currently
share this particular default style.\"\]

1.0

`type_file`

1

12

1You can set as well as get the value of `HTMLInputElement.files` in all
modern browsers; this was most recently added to Firefox, in version 57
(see [bug 1384030](https://bugzil.la/1384030)).

Yes

11

1

4.4

18

4

11

1

1.0

`type_hidden`

1

12

1

Yes

2

1

4.4

18

4

14

1

1.0

`type_image`

1

12

1

Yes

15

1

4.4

18

4

14

1

1.0

`type_month`

20

12

No

No

11

NoThe input type is recognized, but there is no month-specific control.
See [bug 200416](https://webkit.org/b/200416).

4.4

25

18

14

Yes

1.5

`type_number`

7

12

29

10

15

5.1

4.4

18

29

14

5

1.0

`type_password`

1

12

1

2

2

1

4.4

18

4

14

1

1.0

`type_radio`

1

12

1

Yes

15

1

4.4

18

4

14

1

1.0

`type_range`

4

12

23

10

11

3.1

4.4

2--4.4Pre-Chromium Android WebView recognizes the `range` type, but
doesn\'t implement a range-specific control.

57

52

11

5

7.0

`type_reset`

1

12

1Unlike other browsers, Firefox by default [persists the dynamic
disabled
state](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing)
of a `<button>` across page loads. Use the `autocomplete` attribute to
control this feature.

Yes

15

1

4.4

18

4Unlike other browsers, Firefox by default [persists the dynamic
disabled
state](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing)
of a `<button>` across page loads. Use the `autocomplete` attribute to
control this feature.

14

1

1.0

`type_search`

5

12

4

10

10.6

5

4.4

18

4

14

4.2

1.0

`type_submit`

1

12

1Unlike other browsers, Firefox by default [persists the dynamic
disabled
state](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing)
of a `<button>` across page loads. Use the `autocomplete` attribute to
control this feature.

Yes

15

1

4.4

18

4Unlike other browsers, Firefox by default [persists the dynamic
disabled
state](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing)
of a `<button>` across page loads. Use the `autocomplete` attribute to
control this feature.

14

1

1.0

`type_tel`

3The field type doesn\'t demonstrate any special behavior.

12

Yes

10

11

4The field type doesn\'t demonstrate any special behavior.

≤37

18

Yes

11

3

1.0

`type_text`

1

12

1

Yes

15

1

4.4

18

4

14

1

1.0

`type_time`

20

12

57

No

10

14.1

4.4

25

57

10.1

5

1.5

`type_url`

1

12

1

10

11

1

4.4

18

4

14

1

1.0

`type_week`

20

12

No

No

11

No

4.4

25

18

14

No

1.5

`usemap`

1

12

1

6

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`x-moz-errormessage`

No

No

Yes--66

No

No

No

No

No

Yes--66

No

No

No

See also
--------

- [Form constraint validation](../constraint_validation)
- [Your first HTML
    form](https://developer.mozilla.org/en-US/docs/Learn/Forms/Your_first_form)
- [How to structure an HTML
    form](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_structure_a_web_form)
- [The native form
    widgets](https://developer.mozilla.org/en-US/docs/Learn/Forms/Basic_native_form_controls)
- [Sending form
    data](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data)
- [Form data
    validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)
- [How to build custom form
    widgets](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls)
- [HTML forms in legacy
    browsers](https://developer.mozilla.org/en-US/docs/Learn/Forms/HTML_forms_in_legacy_browsers)
- [Styling HTML
    forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Styling_web_forms)
- [Advanced styling for HTML
    forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling)
- [CSS property compatibility
    table](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input>>
