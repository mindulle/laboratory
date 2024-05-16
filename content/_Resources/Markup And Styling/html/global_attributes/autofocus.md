autofocus
=========

The `autofocus` [global attribute](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) is a Boolean
attribute indicating that an element should be focused on page load, or
when the [`<dialog>`](../element/dialog) that it is part of is
displayed.

[html]

```html
<input name="q" autofocus />
```

No more than one element in the document or dialog may have the
autofocus attribute. If applied to multiple elements the first one will
receive focus.

**Note:** The `autofocus` attribute applies to all elements, not just
form controls. For example, it might be used on a
[contenteditable](contenteditable) area.

Accessibility considerations
----------------------------

Automatically focusing a form control can confuse visually-impaired
people using screen-reading technology and people with cognitive
impairments. When `autofocus` is assigned, screen-readers \"teleport\"
their user to the form control without warning them beforehand.

Use careful consideration for accessibility when applying the
`autofocus` attribute. Automatically focusing on a control can cause the
page to scroll on load. The focus can also cause dynamic keyboards to
display on some touch devices. While a screen reader will announce the
label of the form control receiving focus, the screen reader will not
announce anything before the label, and the sighted user on a small
device will equally miss the context created by the preceding content.

Specifications
--------------

  ------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  dom-fe-autofocus]](https://html.spec.whatwg.org/multipage/interaction.html#dom-fe-autofocus)

  ------------------------------------------------------------------------------------------------------

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

`autofocus`

79

1--79Supported for the `<button>`, `<input>`, `<select>`, and
`<textarea>` elements.

79

12--79Supported for the `<button>`, `<input>`, `<select>`, and
`<textarea>` elements.

1Supported for the `<button>`, `<input>`, `<select>`, and `<textarea>`
elements.

10Supported for the `<button>`, `<input>`, `<select>`, and `<textarea>`
elements.

66

≤12.1--66Supported for the `<button>`, `<input>`, `<select>`, and
`<textarea>` elements.

4Supported for the `<button>`, `<input>`, `<select>`, and `<textarea>`
elements.

79

≤37--79Supported for the `<button>`, `<input>`, `<select>`, and
`<textarea>` elements.

79

18--79Supported for the `<button>`, `<input>`, `<select>`, and
`<textarea>` elements.

4Supported for the `<button>`, `<input>`, `<select>`, and `<textarea>`
elements.

57

≤12.1--57Supported for the `<button>`, `<input>`, `<select>`, and
`<textarea>` elements.

3.2Supported for the `<button>`, `<input>`, `<select>`, and `<textarea>`
elements.

12.0

1.0--12.0Supported for the `<button>`, `<input>`, `<select>`, and
`<textarea>` elements.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/autofocus>>
