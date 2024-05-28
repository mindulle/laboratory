:autofill
=========

The `:autofill` CSS [pseudo-class](pseudo-classes.md) matches when an
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
element has its value autofilled by the browser. The class stops
matching if the user edits the field.

Try it
------

**Note:** The user agent style sheets of many browsers use `!important`
in their `:-webkit-autofill` style declarations, making them
non-overridable by webpages without resorting to JavaScript hacks. For
example Chrome has the following in its internal stylesheet:

[css]

```css
background-color: rgb(232, 240, 254) !important;
background-image: none !important;
color: -internal-light-dark(black, white) !important;
```

This means that you cannot set the
[`background-color`](background-color.md),
[`background-image`](background-image.md), or [`color`](_Resources/Markup%20And%20Styling/css/color.md) in your own
rules.

Syntax
------

[css]

```css
:autofill {
  /* ... */
}
```

Examples
--------

The following example demonstrates the use of the `:autofill`
pseudo-class to change the border of a text field that has been
autocompleted by the browser. For the best browser compatibility use
both `:-webkit-autofill` and `:autofill`.

[css]

```css
input {
  border: 3px solid grey;
  border-radius: 3px;
}

input:-webkit-autofill {
  border: 3px solid blue;
}
input:autofill {
  border: 3px solid blue;
}
```

[html]

```html
<form method="post" action="">
  <label for="email">Email</label>
  <input type="email" name="email" id="email" autocomplete="email" />
</form>
```

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-autofill]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-autofill)

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

`:autofill`

1

79

8686

No

15

153

4.4

18

8686

14

151

1.0

See also
--------

- [Chromium issue 46543: Auto-filled input text box yellow background
    highlight cannot be turned off](https://crbug.com/46543)
- [WebKit bug 66032: Allow site authors to override autofilled
    fields\' colors.](https://webkit.org/b/66032)
- [Mozilla bug 740979: implement `:-moz-autofill` pseudo-class on
    input elements with an autofilled value](https://bugzil.la/740979)
- [User Interface Module Level 4: more
    selectors](https://wiki.csswg.org/spec/css4-ui#more-selectors)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:autofill>
