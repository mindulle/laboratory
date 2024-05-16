:out-of-range
=============

The `:out-of-range`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents an
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
element whose current value is outside the range limits specified by the
[`min`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#min)
and
[`max`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#max)
attributes.

Try it
------

This pseudo-class is useful for giving the user a visual indication that
a field\'s current value is outside the permitted limits.

**Note:** This pseudo-class only applies to elements that have (and can
take) a range limitation. In the absence of such a limitation, the
element can neither be \"in-range\" nor \"out-of-range.\"

Syntax
------

[css]

```css
:out-of-range {
  /* ... */
}
```

Examples
--------

### HTML

[html]

```html
<form action="" id="form1">
  <p>Values between 1 and 10 are valid.</p>
  <ul>
    <li>
      <input
        id="value1"
        name="value1"
        type="number"
        placeholder="1 to 10"
        min="1"
        max="10"
        value="12" />
      <label for="value1">Your value is </label>
    </li>
  </ul>
</form>
```

### CSS

[css]

```css
li {
  list-style: none;
  margin-bottom: 1em;
}

input {
  border: 1px solid black;
}

input:in-range {
  background-color: rgba(0, 255, 0, 0.25);
}

input:out-of-range {
  background-color: rgba(255, 0, 0, 0.25);
  border: 2px solid red;
}

input:in-range + label::after {
  content: "okay.";
}

input:out-of-range + label::after {
  content: "out of range!";
}
```

### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-out-of-range]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-out-of-range)

[Selectors Level 4\
  [\# out-of-range-pseudo]](https://drafts.csswg.org/selectors/#out-of-range-pseudo)
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

`:out-of-range`

10

13

29

No

11

5.1

2.2

18

16

11

5

1.0

See also
--------

- [`:in-range`](:in-range)
- [Form data
    validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range>
