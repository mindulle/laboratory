::selection
===========

The `::selection` CSS [pseudo-element](pseudo-elements.md) applies styles
to the part of a document that has been highlighted by the user (such as
clicking and dragging the mouse across text).

Try it
------

Allowable properties
--------------------

Only certain CSS properties can be used with `::selection`:

- [`color`](_Resources/Markup%20And%20Styling/css/color.md)
- [`background-color`](background-color.md)
- [`text-decoration`](text-decoration.md) and its associated properties
- [`text-shadow`](text-shadow.md)
- [`-webkit-text-stroke-color`](-webkit-text-stroke-color.md),
    [`-webkit-text-fill-color`](-webkit-text-fill-color.md) and
    [`-webkit-text-stroke-width`](-webkit-text-stroke-width.md)

In particular, [`background-image`](background-image.md) is ignored.

Syntax
------

[css]

```css
::selection {
  /* ... */
}
```

Examples
--------

### HTML

[html]

```html
This text has special styles when you highlight it.
<p>Also try selecting text in this paragraph.</p>
```

### CSS

[css]

```css
/* Make selected text gold on a red background */
::selection {
  color: gold;
  background-color: red;
}

/* Make selected text in a paragraph white on a blue background */
p::selection {
  color: white;
  background-color: blue;
}
```

### Result

Accessibility concerns
----------------------

**Don\'t override selected text styles for purely aesthetic reasons**
--- users can customize them to suit their needs. For people
experiencing cognitive concerns or who are less technologically
literate, unexpected changes to selection styles may hurt their
understanding of the functionality.

If overridden, it is important to ensure that the **contrast ratio**
between the text and background colors of the selection is high enough
that people experiencing low vision conditions can read it.

Color contrast ratio is found by comparing the luminosity of the
selected text and the selected text background colors. To meet current
[Web Content Accessibility Guidelines
(WCAG)](https://www.w3.org/WAI/standards-guidelines/wcag/), text content
must have a contrast ratio of **4.5:1**, or 3:1 for larger text such as
headings. (WCAG defines large text as between `18.66px` and `24px` and
[bold](_Resources/Markup%20And%20Styling/css/font-weight.md), or `24px` or larger.)

- [WebAIM: Color Contrast
    Checker](https://webaim.org/resources/contrastchecker/)
- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.3 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

Specifications
--------------

  ---------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------

  [CSS Pseudo-Elements Module Level 4\
  [\#
  selectordef-selection]](https://drafts.csswg.org/css-pseudo/#selectordef-selection)

  ---------------------------------------------------------------------------------------------

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

`::selection`

1

12

621

9

9.5

1.1

37

18

624

14

No

1.0

See also
--------

- [`pointer-events`](pointer-events.md) - control which events are active
    on the element

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/::selection>
