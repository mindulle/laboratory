HTML attribute: dirname
=======================

The `dirname` attribute can be used on
[`<textarea>`](../element/textarea) and [`<input>`](../element/input)
elements and describes the directionality of the element\'s text content
during form submission. The browser uses this attribute\'s value to
determine whether text the user has entered is left-to-right or
right-to-left oriented. When used, the element\'s text directionality
value is included in form submission data along with the `dirname`
attribute\'s value as the name of the field.

Usage notes
-----------

The `dirname` attribute can be used on any
[`<textarea>`](../element/textarea) element, or any
[`<input>`](../element/input) element with
[text](../element/input/text), [search](../element/input/search),
[tel](../element/input/tel), [url](../element/input/url), or
[email](../element/input/email) type.

The format of the submitted data is `{dirname_value}={direction}` where
`{dirname_value}` is the value of the `dirname` attribute and
`{direction}` is the directionality of the text. For example, if the
user enters \"Hello\" in an element with the attributes `name="comment"`
and `dirname="comment-direction"`, the URL-encoded form submission data
for `GET` requests will be `comment=Hello&comment-direction=ltr`. The
directionality is one of the following:

[`rtl`](#rtl)

:   The text entered by the user is in a right-to-left writing
    direction.

[`ltr`](#ltr)

:   The text entered by the user is in a left-to-right writing
    direction.

If no text directionality is specified, the user agent will use the
directionality of the parent element containing the form, and if that is
not specified, the default directionality of the user agent.

Examples
--------

### Textarea element directionality

In this example, the `dir="auto"` attribute on the textarea element
allows the text directionality to be determined automatically based on
the text entered by the user:

[html]

```html
<form method="get" action="https://www.example.com/submit">
  <textarea name="comment" dir="auto" dirname="comment-direction">سيب</textarea>
  <button type="submit">Send my greetings</button>
</form>
```

When the user submits the form, the user agent includes two fields, one
called `comment` with the value \"سيب\", and one called
`comment-direction` with the value \"rtl\". The URL-encoded submission
body looks like this:

[url]

```url
https://www.example.com/submit?comment=%D8%B3%D9%8A%D8%A8&comment-direction=rtl
```

### Input element directionality

In this example, the `dir="auto"` attribute on the input element allows
the text directionality to be determined automatically based on the text
entered by the user:

[html]

```html
<form method="get" action="https://www.example.com/submit">
  <input
    type="text"
    name="comment-input"
    dir="auto"
    dirname="comment-direction"
    value="Hello" />
  <button type="submit">Send my greetings</button>
</form>
```

When the user submits the form, the user agent includes two fields, one
called `comment-input` with the value \"Hello\", and one called
`comment-direction` with the value \"ltr\":

[url]

```url
https://www.example.com/submit?comment-input=Hello&comment-direction=ltr
```

### Inheriting directionality

The following `<input>` and `<textarea>` elements do not have a `dir`
attribute, so they inherit the explicit directionality of their parent
element, which is `rtl`:

[html]

```html
<div dir="rtl">
  <form method="get" action="https://www.example.com/submit">
    <input
      type="text"
      name="user"
      dirname="user-direction"
      value="LTR Username" />
    <textarea name="comment" dirname="comment-direction">LTR Comment</textarea>
    <button type="submit">Post Comment</button>
  </form>
</div>
```

The URL-encoded submission body looks like this:

[url]

```url
https://www.example.com/submit?user=LTR+Username&user-direction=rtl&comment=LTR+Comment&comment-direction=rtl
```

Specifications
--------------

  --------------------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  attr-fe-dirname]](https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#attr-fe-dirname)

  --------------------------------------------------------------------------------------------------------------------

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

`dirname`

17

79

116

No

≤12.1

6

≤37

18

116

≤12.1

6

1.0

### html.elements.textarea.dirname

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### html.elements.input.dirname

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

See also
--------

- [`dir` attribute](../global_attributes/dir)
- [`<input>`](../element/input)
- [`<textarea>`](../element/textarea)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/dirname>>
