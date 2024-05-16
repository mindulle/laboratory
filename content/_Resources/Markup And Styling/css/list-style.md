list-style
==========

The `list-style` CSS [shorthand property](shorthand_properties.md) allows
you to set all the list style properties at once.

Try it
------

The values of this property are applied to list items, including
[`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li)
elements and elements with `display`: list-item;. Because this property
is inherited, it can be set on a parent element (normally
[`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol)
or
[`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul))
to make the same list styling apply to all the nested items.

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`list-style-image`](list-style-image.md)
- [`list-style-position`](list-style-position.md)
- [`list-style-type`](list-style-type.md)

Syntax
------

[css]

```css
/* type */
list-style: square;

/* image */
list-style: url("../img/shape.png");

/* position */
list-style: inside;

/* two values */
list-style: georgian outside;
list-style: url("img/pip.svg") inside;

/* three values */
list-style: lower-roman url("img/shape.png") outside;

/* Keyword value */
list-style: none;

/* Global values */
list-style: inherit;
list-style: initial;
list-style: revert;
list-style: revert-layer;
list-style: unset;
```

The `list-style` property is specified as one, two, or three values in
any order. If [`list-style-type`](list-style-type.md) and
[`list-style-image`](list-style-image.md) are both set, the
`list-style-type` is used as a fallback if the image is unavailable.

### Values

[`list-style-type`](list-style-type.md)

:   A `<counter-style>`, [`<string>`](string.md), or `none`. If omitted in
    the shorthand, the default `disc` value is used. See
    [`list-style-type`](list-style-type.md).

[`list-style-image`](list-style-image.md)

:   An [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) or `none`. If omitted, the default `none`
    value is used. See [`list-style-image`](list-style-image.md).

[`list-style-position`](list-style-position.md)

:   Either `inside` or `outside`. If omitted, the default `outside`
    value is used. See [`list-style-position`](list-style-position.md).

[`none`](#none)

:   No list style is used.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](list-style-type.md): |
|                                   |     `disc`                        |
|                                   | -   [](list-style-position.md): |
|                                   |     `outside`                     |
|                                   | -   [](list-style-image.md): |
|                                   |     `none`                        |
+-----------------------------------+-----------------------------------+
| Applies to                        | list items                        |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | yes                               |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](list-style-image.md): |
|                                   |     The keyword `none` or the     |
|                                   |     computed \<image\>            |
|                                   | -   [](list-style-position.md): |
|                                   |     as specified                  |
|                                   | -   [](list-style-type.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](list-style-image.md): |
|                                   |     discrete                      |
|                                   | -   [](list-style-position.md): |
|                                   |     discrete                      |
|                                   | -   [](list-style-type.md): |
|                                   |     discrete                      |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
list-style = 
  <'list-style-position'>  ||
  <'list-style-image'>     ||
  <'list-style-type'>      
```

Examples
--------

### Setting list style type and position

#### HTML

[html]

```html
List 1
<ul class="one">
  <li>List Item1</li>
  <li>List Item2</li>
  <li>List Item3</li>
</ul>
List 2
<ul class="two">
  <li>List Item A</li>
  <li>List Item B</li>
  <li>List Item C</li>
</ul>
```

#### CSS

[css]

```css
.one {
  list-style: circle;
}

.two {
  list-style: square inside;
}
```

#### Result

Accessibility concerns
----------------------

Safari does not recognize ordered or unordered lists as lists in the
accessibility tree if they have a `list-style` value of `none`, unless
the list is nested within the
[`<nav>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav)
navigation element. This [behavior is
intentional](https://webkit.org/b/170179#c1) and is not considered a
bug.

To ensure lists are announced as lists, include
[`role="list"`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/list_role)
to
[`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol)
and
[`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)
elements, especially if the list is not nested in a `<nav>`. This
restores list semantics without affecting the design:

[html]

```html
<ul role="list">
  <li>An item</li>
  <li>Another item</li>
</ul>
```

If an ARIA `role` is not an option for your code, CSS can be used
instead. Adding non-empty [pseudo-content](content.md) such as text or
images before each list item can restore list semantics, but impacts the
visual appearance. Safari determines if the added pseudo-content
suffices as accessible content, restoring list semantics if so.
Generally, Safari considers text and images as sufficient, which is why
the `content: "+ ";` shown below works (but requires additional styling
to not affect the design).

[css]

```css
ul {
  list-style: none;
}

ul li::before {
  content: "+ ";
}
```

A declaration of `content: "";` (an empty string) is ignored, as are
`content` values that contain only spaces, such as `content: " ";`.

These CSS workarounds should only be used when an HTML solution is
unavailable, and only after testing to ensure that they don\'t result in
unexpected behaviors that may negatively impact user experience.

- [\'Fixing\'
    Lists](https://www.scottohara.me/blog/2019/01/12/lists-and-safari.html) (2023)
- [VoiceOver and list-style-type:
    none](https://gerardkcohen.me/writing/2017/voiceover-list-style-type.html) (2017)
- [Understanding WCAG: Create content that can be presented in
    different ways](#)
- [Understanding success criterion 1.3.1: Info and relationships \|
    WCAG
    2.1](https://www.w3.org/WAI/WCAG21/Understanding/info-and-relationships.html)

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [CSS Lists and Counters Module Level 3\
  [\#
  list-style-property]](https://drafts.csswg.org/css-lists/#list-style-property)

  ----------------------------------------------------------------------------------------

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

`list-style`

1

12

1

4

7

1

4.4

18

4

10.1

1

1.0

`symbols`

91

91

35

No

77

No

91

91

35

64

No

16.0

See also
--------

- [`list-style-type`](list-style-type.md),
    [`list-style-image`](list-style-image.md), and
    [`list-style-position`](list-style-position.md) properties
- [`::marker`](::marker) pseudo-element
- [CSS lists](css_lists.md) module
- [CSS counter styles](css_counter_styles.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/list-style>
