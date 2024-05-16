:placeholder-shown
==================

The `:placeholder-shown`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents any
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
or
[`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)
element that is currently displaying [placeholder
text](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#placeholder).

Try it
------

Syntax
------

[css]

```css
:placeholder-shown {
  /* ... */
}
```

Examples
--------

### Basic example

This example applies special font and border styles when the placeholder
is shown.

#### HTML

[html]

```html
<input placeholder="Type something here!" />
```

#### CSS

[css]

```css
input {
  border: 1px solid black;
  padding: 3px;
}

input:placeholder-shown {
  border-color: teal;
  color: purple;
  font-style: italic;
}
```

#### Result

### Overflowing text

When form fields are too small, placeholder text can get cropped in an
undesirable way. You can use the [`text-overflow`](text-overflow.md)
property to alter the way overflowing text is displayed.

#### HTML

[html]

```html
<input id="input1" placeholder="Name, Rank, and Serial Number" /> <br /><br />
<input id="input2" placeholder="Name, Rank, and Serial Number" />
```

#### CSS

[css]

```css
#input2:placeholder-shown {
  text-overflow: ellipsis;
}
```

#### Result

### Customized input field

The following example highlights the Student ID field with a custom
style.

#### HTML

[html]

```html
<form id="test">
  <p>
    <label for="name">Enter Student Name:</label>
    <input id="name" placeholder="Student Name" />
  </p>
  <p>
    <label for="branch">Enter Student Branch:</label>
    <input id="branch" placeholder="Student Branch" />
  </p>
  <p>
    <label for="sid">Enter Student ID:</label>
    <input
      type="number"
      pattern="[0-9]"
      title="8 digit ID"
      id="sid"
      class="studentid"
      placeholder="8 digit id" />
  </p>
  <input type="submit" />
</form>
```

#### CSS

[css]

```css
input {
  background-color: #e8e8e8;
  color: black;
}

input.studentid:placeholder-shown {
  background-color: yellow;
  color: red;
  font-style: italic;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  placeholder]](https://drafts.csswg.org/selectors/#placeholder)

  ------------------------------------------------------------------------

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

`:placeholder-shown`

47

79

514--51

10

34

9

47

47

514--51

34

9

5.0

`non_text_types`

47

79

59

No

34

9

47

47

59

34

9

5.0

See also
--------

- The [`::placeholder`](::placeholder) pseudo-element styles the
    placeholder *itself*.
- Related HTML elements:
    [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input),
    [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)
- [HTML forms](https://developer.mozilla.org/en-US/docs/Learn/Forms)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:placeholder-shown>
