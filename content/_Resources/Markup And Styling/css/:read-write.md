:read-write
===========

The `:read-write`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents an element (such as `input` or
`textarea`) that is editable by the user.

Try it
------

Syntax
------

[css]

```css
:read-write {
  /* ... */
}
```

Examples
--------

### Confirming form information in read-only/read-write controls

One use of `readonly` form controls is to allow the user to check and
verify information that they may have entered in an earlier form (for
example, shipping details), while still being able to submit the
information along with the rest of the form. We do just this in the
example below.

The `:read-only` pseudo-class is used to remove all the styling that
makes the inputs look like clickable fields, making them look more like
read-only paragraphs. The `:read-write` pseudo-class on the other hand
is used to provide some nicer styling to the editable `<textarea>`.

[css]

```css
input:-moz-read-only,
textarea:-moz-read-only,
input:read-only,
textarea:read-only {
  border: 0;
  box-shadow: none;
  background-color: white;
}

textarea:-moz-read-write,
textarea:read-write {
  box-shadow: inset 1px 1px 3px #ccc;
  border-radius: 5px;
}
```

You can find the full source code at
[readonly-confirmation.html](https://github.com/mdn/learning-area/blob/main/html/forms/pseudo-classes/readonly-confirmation.html);
this renders like so:

### Styling read-write non-form controls

This selector doesn\'t just select
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)/[`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)
elements --- it will select *any* element that can be edited by the
user, such as a
[`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)
element with
[`contenteditable`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#contenteditable)
set on it.

[html]

```html
<p contenteditable>This paragraph is editable; it is read-write.</p>

<p>This paragraph is not editable; it is read-only.</p>
```

[css]

```css
p {
  font-size: 150%;
  padding: 5px;
  border-radius: 5px;
}

p:read-only {
  background-color: red;
  color: white;
}

p:read-write {
  background-color: lime;
}
```

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-read-write]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-read-write)

[Selectors Level 4\
  [\# rw-pseudos]](https://drafts.csswg.org/selectors/#rw-pseudos)
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

`:read-write`

1

13

781.5

No

9

4

≤37

18

4

10.1

3.2

1.0

See also
--------

- [`:read-only`](:read-only)
- HTML
    [`contenteditable`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#contenteditable)
    attribute

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:read-write>
