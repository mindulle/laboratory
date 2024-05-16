\<dl\>: The Description List element
====================================

The `<dl>` [HTML](../index) element represents a description list. The
element encloses a list of groups of terms (specified using the
[`<dt>`](dt) element) and descriptions (provided by [`<dd>`](dd)
elements). Common uses for this element are to implement a glossary or
to display metadata (a list of key-value pairs).

Try it
------

+-----------------------------------+-----------------------------------+
| [Content                          | [Flow                             |
| c                                 | content](../                      |
| ategories](../content_categories) | content_categories#flow_content), |
|                                   | and if the `<dl>` element\'s      |
|                                   | children include one name-value   |
|                                   | group, palpable content.          |
+-----------------------------------+-----------------------------------+
| Permitted content                 | Either: Zero or more groups each  |
|                                   | consisting of one or more         |
|                                   | [`<dt>`](dt) elements followed by |
|                                   | one or more [`<dd>`](dd)          |
|                                   | elements, optionally intermixed   |
|                                   | with [`<script>`](script) and     |
|                                   | [`<template>`](template)          |
|                                   | elements.\                        |
|                                   | Or: (in                           |
|                                   | [WHATWG](https://developer.mozill>> |
|                                   | a.org/en-US/docs/Glossary/WHATWG) |
|                                   | HTML,                             |
|                                   | [W3C](https://developer.moz>>       |
|                                   | illa.org/en-US/docs/Glossary/W3C) |
|                                   | HTML 5.2 and later) One or more   |
|                                   | [`<div>`](div) elements,          |
|                                   | optionally intermixed with        |
|                                   | [`<script>`](script) and          |
|                                   | [`<template>`](template)          |
|                                   | elements.                         |
+-----------------------------------+-----------------------------------+
| Tag omission                      | None, both the starting and       |
|                                   | ending tag are mandatory.         |
+-----------------------------------+-----------------------------------+
| Permitted parents                 | Any element that accepts [flow    |
|                                   | content](../                      |
|                                   | content_categories#flow_content). |
+-----------------------------------+-----------------------------------+
| Implicit ARIA role                | [No corresponding                 |
|                                   | role](https://www.w3.org/TR/html>>  |
|                                   | -aria/#dfn-no-corresponding-role) |
+-----------------------------------+-----------------------------------+
| Permitted ARIA roles              | [`group`](https://develope>>        |
|                                   | r.mozilla.org/en-US/docs/Web/Acce |
|                                   | ssibility/ARIA/Roles/group_role), |
|                                   | `list`,                           |
|                                   | [`none`](https://develop>>          |
|                                   | er.mozilla.org/en-US/docs/Web/Acc |
|                                   | essibility/ARIA/Roles/none_role), |
|                                   | [`pres                            |
|                                   | entation`](https://developer.mozi>> |
|                                   | lla.org/en-US/docs/Web/Accessibil |
|                                   | ity/ARIA/Roles/presentation_role) |
+-----------------------------------+-----------------------------------+
| DOM interface                     | [`HTMLDListElement`](             |
|                                   | https://developer.mozilla.org/en->> |
|                                   | US/docs/Web/API/HTMLDListElement) |
+-----------------------------------+-----------------------------------+

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Examples
--------

### Single term and description

[html]

```html
<dl>
  <dt>Firefox</dt>
  <dd>
    A free, open source, cross-platform, graphical web browser developed by the
    Mozilla Corporation and hundreds of volunteers.
  </dd>

  <!-- Other terms and descriptions -->
</dl>
```

#### Result

### Multiple terms, single description

[html]

```html
<dl>
  <dt>Firefox</dt>
  <dt>Mozilla Firefox</dt>
  <dt>Fx</dt>
  <dd>
    A free, open source, cross-platform, graphical web browser developed by the
    Mozilla Corporation and hundreds of volunteers.
  </dd>

  <!-- Other terms and descriptions -->
</dl>
```

#### Result

### Single term, multiple descriptions

[html]

```html
<dl>
  <dt>Firefox</dt>
  <dd>
    A free, open source, cross-platform, graphical web browser developed by the
    Mozilla Corporation and hundreds of volunteers.
  </dd>
  <dd>
    The Red Panda also known as the Lesser Panda, Wah, Bear Cat or Firefox, is a
    mostly herbivorous mammal, slightly larger than a domestic cat (60 cm long).
  </dd>

  <!-- Other terms and descriptions -->
</dl>
```

#### Result

### Multiple terms and descriptions

It is also possible to define multiple terms with multiple corresponding
descriptions, by combining the examples above.

### Metadata

Description lists are useful for displaying metadata as a list of
key-value pairs.

[html]

```html
<dl>
  <dt>Name</dt>
  <dd>Godzilla</dd>
  <dt>Born</dt>
  <dd>1952</dd>
  <dt>Birthplace</dt>
  <dd>Japan</dd>
  <dt>Color</dt>
  <dd>Green</dd>
</dl>
```

#### Result

Tip: It can be handy to define a key-value separator in the CSS, such
as:

[css]

```css
dt::after {
  content: ": ";
}

```

### Wrapping name-value groups in `div` elements

[WHATWG](https://developer.mozilla.org/en-US/docs/Glossary/WHATWG) HTML
allows wrapping each name-value group in a [`<dl>`](dl) element in a
[`<div>`](div) element. This can be useful when using
[microdata](../microdata), or when [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) apply to a whole group, or for styling
purposes.

[html]

```html
<dl>
  <div>
    <dt>Name</dt>
    <dd>Godzilla</dd>
  </div>
  <div>
    <dt>Born</dt>
    <dd>1952</dd>
  </div>
  <div>
    <dt>Birthplace</dt>
    <dd>Japan</dd>
  </div>
  <div>
    <dt>Color</dt>
    <dd>Green</dd>
  </div>
</dl>
```

#### Result

Notes
-----

Do not use this element (nor [`<ul>`](ul) elements) to merely create
indentation on a page. Although it works, this is a bad practice and
obscures the meaning of description lists.

To change the indentation of a description term, use the
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)
property.

Accessibility concerns
----------------------

Each screen reader exposes `<dl>` content differently, including total
count, terms/definitions context, and navigation methods. These
differences are not necessarily bugs. As of iOS 14, VoiceOver will
announce that `<dl>` content is a list when navigating with the virtual
cursor (not via the read-all command). VoiceOver does not support list
navigation commands with `<dl>`. Be careful applying ARIA `term` and
`definition` roles to `<dl>` constructs as VoiceOver (macOS and iOS)
will adjust how they are announced.

- [VoiceOver on iOS 14 Supports Description
    Lists](https://adrianroselli.com/2020/09/voiceover-on-ios-14-supports-description-lists.html)
- [Brief Note on Description List
    Support](https://adrianroselli.com/2022/12/brief-note-on-description-list-support.html)

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-dl-element]](https://html.spec.whatwg.org/multipage/grouping-content.html#the-dl-element)

  -------------------------------------------------------------------------------------------------------

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

`dl`

1

12

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

See also
--------

- [`<dt>`](dt)
- [`<dd>`](dd)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl>>
