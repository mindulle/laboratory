\<output\>: The Output element
==============================

The `<output>` [HTML](../index) element is a container element into
which a site or app can inject the results of a calculation or the
outcome of a user action.

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`for`](#for)

:   A space-separated list of other elements\'
    [`id`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#id)s, indicating that those elements
    contributed input values to (or otherwise affected) the calculation.

[`form`](#form)

:   The [`<form>`](form) element to associate the output with (its *form
    owner*). The value of this attribute must be the
    [`id`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#id) of a `<form>` in the same document.
    (If this attribute is not set, the `<output>` is associated with its
    ancestor `<form>` element, if any.)

    This attribute lets you associate `<output>` elements to `<form>`s
    anywhere in the document, not just inside a `<form>`. It can also
    override an ancestor `<form>` element.

[`name`](#name)

:   The element\'s name. Used in the
    [`form.elements`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements)
    API.

The `<output>` value, name, and contents are NOT submitted during form
submission.

Examples
--------

In the following example, the form provides a slider whose value can
range between `0` and `100`, and an [`<input>`](input) element into
which you can enter a second number. The two numbers are added together,
and the result is displayed in the `<output>` element each time the
value of any of the controls changes.

[html]

```html
<form oninput="result.value=parseInt(a.value)+parseInt(b.value)">
  <input type="range" id="b" name="b" value="50" /> +
  <input type="number" id="a" name="a" value="10" /> =
  <output name="result" for="a b">60</output>
</form>
```

### Result

Accessibility Concerns
----------------------

Many browsers implement this element as an
[`aria-live`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Live_Regions)
region. Assistive technology will thereby announce the results of UI
interactions posted inside it without requiring that focus is switched
away from the controls that produce those results.

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), [listed](../content_categories#form_listed), [labelable](../content_categories#form_labelable), [resettable](../content_categories#form_resettable) [form-associated element](../content_categories#form-associated_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            [`status`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/status_role)
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLOutputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOutputElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-output-element]](https://html.spec.whatwg.org/multipage/form-elements.html#the-output-element)

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

`output`

10

≤18

4

No

11

7

4.4

18

4

11

7

1.0

`for`

10

≤18

4

No

11

7

4.4

18

4

11

7

1.0

`form`

10

≤18

4

No

11

7

4.4

18

4

11

7

1.0

`name`

10

≤18

4

No

11

7

4.4

18

4

11

7

1.0

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/output>>
