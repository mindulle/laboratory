::placeholder
=============

The `::placeholder`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-element](pseudo-elements.md) represents the [placeholder
text](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#placeholder)
in an
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
or
[`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)
element.

Try it
------

Only the subset of CSS properties that apply to the
[`::first-line`](::first-line) pseudo-element can be used in a rule
using `::placeholder` in its selector.

**Note:** In most browsers, the appearance of placeholder text is a
translucent or light gray color by default.

Syntax
------

[css]

```css
::placeholder {
  /* ... */
}
```

Accessibility concerns
----------------------

### Color contrast

#### Contrast Ratio

Placeholder text typically has a lighter color treatment to indicate
that it is a suggestion for what kind of input will be valid, and is not
actual input of any kind.

It is important to ensure that the contrast ratio between the color of
the placeholder text and the background of the input is high enough that
people experiencing low vision conditions will be able to read it while
also making sure there is enough of a difference between the placeholder
text and input text color that users do not mistake the placeholder for
inputted data.

Color contrast ratio is determined by comparing the luminosity of the
placeholder text and the input background color values. In order to meet
current [Web Content Accessibility Guidelines
(WCAG)](https://www.w3.org/WAI/standards-guidelines/wcag/), a ratio of
4.5:1 is required for text content and 3:1 for larger text such as
headings. Large text is defined as 18.66px and bold or larger, or 24px
or larger.

- [WebAIM: Color Contrast
    Checker](https://webaim.org/resources/contrastchecker/)
- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.3 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

#### Usability

Placeholder text with sufficient color contrast may be interpreted as
entered input. Placeholder text will also disappear when a person enters
content into an
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
element. Both of these circumstances can interfere with successful form
completion, especially for people with cognitive concerns.

An alternate approach to providing placeholder information is to include
it outside of the input in close visual proximity, then use
[`aria-describedby`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-describedby)
to programmatically associate the
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
with its hint.

With this implementation, the hint content is available even if
information is entered into the input field, and the input appears free
of preexisting input when the page is loaded. Most screen reading
technology will use `aria-describedby` to read the hint after the
input\'s label text is announced, and the person using the screen reader
can mute it if they find the extra information unnecessary.

[html]

```html
<label for="user-email">Your email address</label>
<span id="user-email-hint" class="input-hint">Example: jane@sample.com</span>
<input
  id="user-email"
  aria-describedby="user-email-hint"
  name="email"
  type="email" />
```

- [Placeholders in Form Fields Are Harmful --- Nielsen Norman
    Group](https://www.nngroup.com/articles/form-design-placeholders/)

### Windows High Contrast Mode

Placeholder text will appear with the same styling as user-entered text
content when rendered in [Windows High Contrast
Mode](https://www.smashingmagazine.com/2022/06/guide-windows-high-contrast-mode/)).
This will make it difficult for some people to determine which content
has been entered, and which content is placeholder text.

### Labels

Placeholders are not a replacement for the
[`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)
element. Without a label that has been programmatically associated with
an input using a combination of the
[`for`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label#for)
and
[`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#id)
attributes, assistive technology such as screen readers cannot parse
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
elements.

- [Placeholders in Form Fields Are Harmful --- Nielsen Norman
    Group](https://www.nngroup.com/articles/form-design-placeholders/)

Examples
--------

### Change placeholder appearance

This example shows some of the adjustments that you can make to the
styles of placeholder text.

#### HTML

[html]

```html
<input placeholder="Type here" />
```

#### CSS

[css]

```css
input::placeholder {
  color: red;
  font-size: 1.2em;
  font-style: italic;
}
```

#### Result

### Opaque text

Some browsers (such as Firefox) set the default [`opacity`](_Resources/Markup%20And%20Styling/css/opacity.md) of
placeholders to something less than 100%. If you want fully opaque
placeholder text, set `opacity` to `1`.

#### HTML

[html]

```html
<input placeholder="Default opacity" />
<input placeholder="Full opacity" class="force-opaque" />
```

#### CSS

[css]

```css
::placeholder {
  color: green;
}

.force-opaque::placeholder {
  opacity: 1;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------

  [CSS Pseudo-Elements Module Level 4\
  [\#
  placeholder-pseudo]](https://drafts.csswg.org/css-pseudo/#placeholder-pseudo)

  ---------------------------------------------------------------------------------------

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

`::placeholder`

576

791212--79

5119

No

4415

10.15

572

5718

5119

4314

10.34.2

7.01.0

See also
--------

- The [`:placeholder-shown`](:placeholder-shown) pseudo-class styles
    an element that *has* an active placeholder.
- Related HTML elements:
    [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input),
    [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)
- [HTML forms](https://developer.mozilla.org/en-US/docs/Learn/Forms)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/::placeholder>
