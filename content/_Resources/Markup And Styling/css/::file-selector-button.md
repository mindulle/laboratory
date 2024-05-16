::file-selector-button
======================

The `::file-selector-button`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-element](pseudo-elements.md) represents the button of an
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
of
[`type="file"`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/file).

Try it
------

Syntax
------

[css]

```css
selector::file-selector-button
```

Examples
--------

### Basic example

#### HTML

[html]

```html
<form>
  <label for="fileUpload">Upload file</label>
  <input type="file" id="fileUpload" />
</form>
```

#### CSS

[css]

```css
input[type="file"]::file-selector-button {
  border: 2px solid #6c5ce7;
  padding: 0.2em 0.4em;
  border-radius: 0.2em;
  background-color: #a29bfe;
  transition: 1s;
}

input[type="file"]::file-selector-button:hover {
  background-color: #81ecec;
  border: 2px solid #00cec9;
}
```

#### Result

Note that `::file-selector-button` is a whole element, and as such
matches the rules from the UA stylesheet. In particular, fonts and
colors won\'t necessarily inherit from the `input` element.

### Fallback example

#### HTML

[html]

```html
<form>
  <label for="fileUpload">Upload file</label>
  <input type="file" id="fileUpload" />
</form>
```

#### CSS

[css]

```css
input[type="file"]::file-selector-button {
  border: 2px solid #6c5ce7;
  padding: 0.2em 0.4em;
  border-radius: 0.2em;
  background-color: #a29bfe;
  transition: 1s;
}

input[type="file"]::-ms-browse:hover {
  background-color: #81ecec;
  border: 2px solid #00cec9;
}

input[type="file"]::-webkit-file-upload-button:hover {
  background-color: #81ecec;
  border: 2px solid #00cec9;
}

input[type="file"]::file-selector-button:hover {
  background-color: #81ecec;
  border: 2px solid #00cec9;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [CSS Pseudo-Elements Module Level 4\
  [\#
  file-selector-button-pseudo]](https://drafts.csswg.org/css-pseudo/#file-selector-button-pseudo)

  ---------------------------------------------------------------------------------------------------------

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

`::file-selector-button`

891

897912--79

82

10

7515

14.13

894.4

8918

82

6314

14.51

15.01.0

See also
--------

- [WebKit CSS
    extensions](https://developer.mozilla.org/en-US/docs/Web/CSS/WebKit_Extensions)
- [File and Directory Entries
    API](https://developer.mozilla.org/en-US/docs/Web/API/File_and_Directory_Entries_API)
- [File and Directory Entries API support in
    Firefox](https://developer.mozilla.org/en-US/docs/Web/API/File_and_Directory_Entries_API/Firefox_support)
- [`<input type="file">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/file)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/::file-selector-button>
