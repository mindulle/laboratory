\<progress\>: The Progress Indicator element
============================================

The `<progress>` [HTML](../index) element displays an indicator showing
the completion progress of a task, typically displayed as a progress
bar.

Try it
------

  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), labelable content, [palpable content](../content_categories#palpable_content).
  Permitted content                             [Phrasing content](../content_categories#phrasing_content), but there must be no `<progress>` element among its descendants.
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            [`progressbar`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/progressbar_role)
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLProgressElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLProgressElement)
  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`max`](#max)

:   This attribute describes how much work the task indicated by the
    `progress` element requires. The `max` attribute, if present, must
    have a value greater than `0` and be a valid floating point number.
    The default value is `1`.

[`value`](#value)

:   This attribute specifies how much of the task that has been
    completed. It must be a valid floating point number between `0` and
    `max`, or between `0` and `1` if `max` is omitted. If there is no
    `value` attribute, the progress bar is indeterminate; this indicates
    that an activity is ongoing with no indication of how long it is
    expected to take.

**Note:** Unlike the [`<meter>`](meter) element, the minimum value is
always 0, and the `min` attribute is not allowed for the `<progress>`
element.

**Note:** The
[`:indeterminate`](https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate)
pseudo-class can be used to match against indeterminate progress bars.
To change the progress bar to indeterminate after giving it a value you
must remove the value attribute with
[`element.removeAttribute('value')`](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttribute).

Examples
--------

[html]

```html
<progress value="70" max="100">70 %</progress>
```

### Result

Accessibility Concerns
----------------------

### Labelling

In most cases you should provide an accessible label when using
`<progress>`. While you can use the standard ARIA labelling attributes
[`aria-labelledby`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-labelledby)
or
[`aria-label`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label)
as you would for any element with `role="progressbar"`, when using
`<progress>` you can alternatively use the [`<label>`](label) element.

**Note:** Text placed between the element\'s tags is not an accessible
label, it is only recommended as a fallback for old browsers that do not
support this element.

#### Examples

[html]

```html
<label>
  Uploading Document: <progress value="70" max="100">70 %</progress>
</label>

<!-- OR -->
<br />

<label for="progress-bar">Uploading Document</label>
<progress id="progress-bar" value="70" max="100">70 %</progress>
```

#### Result

### Describing a particular region

If the `<progress>` element is describing the loading progress of a
section of a page, use
[`aria-describedby`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-describedby)
to point to the status, and set
[`aria-busy="true"`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-busy)
on the section that is being updated, removing the `aria-busy` attribute
when it has finished loading.

#### Examples

[html]

```html
<div aria-busy="true" aria-describedby="progress-bar">
  <!-- content is for this region is loading -->
</div>

<!-- ... -->

<progress id="progress-bar" aria-label="Content loading…"></progress>
```

##### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-progress-element]](https://html.spec.whatwg.org/multipage/form-elements.html#the-progress-element)

  ----------------------------------------------------------------------------------------------------------------

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

`progress`

6

12

6\[\"Before Firefox 14, the `<progress>` element was incorrectly
classified as a form element, and therefore had a `form` attribute. This
has been fixed.\", \"Firefox provides the `::-moz-progress-bar`
pseudo-element, which lets you style the part of the interior of the
progress bar representing the amount of work completed so far.\"\]

10

11

6

4.4

18

6\[\"Before Firefox 14, the `<progress>` element was incorrectly
classified as a form element, and therefore had a `form` attribute. This
has been fixed.\", \"Firefox provides the `::-moz-progress-bar`
pseudo-element, which lets you style the part of the interior of the
progress bar representing the amount of work completed so far.\"\]

11

7Safari on iOS does not support indeterminate progress bars (they are
rendered like 0%-completed progress bars).

1.0

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

`value`

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

See also
--------

- [`<meter>`](meter)
- [`:indeterminate`](https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate)
- [`-moz-orient`](https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-orient)
- [`::-moz-progress-bar`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-moz-progress-bar)
- [`::-webkit-progress-bar`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-webkit-progress-bar)
- [`::-webkit-progress-value`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-webkit-progress-value)
- [`::-webkit-progress-inner-element`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-webkit-progress-inner-element)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress>>
