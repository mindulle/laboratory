title
=====

The `title` [global attribute](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) contains text
representing advisory information related to the element it belongs to.

Try it
------

The main use of the `title` attribute is to label
[`<iframe>`](../element/iframe) elements for assistive technology.

The `title` attribute may also be used to label controls in [data
tables](../element/table).

The `title` attribute, when added to
[`<link rel="stylesheet">`](../element/link), creates an alternate
stylesheet. When defining an alternative style sheet with
`<link rel="alternate">` the attribute is required and must be set to a
non-empty string.

If included on the [`<abbr>`](../element/abbr) opening tag, the `title`
must be a full expansion of the abbreviation or acronym. Instead of
using `title`, when possible, provide an expansion of the abbreviation
or acronym in plain text on first use, using the `<abbr>` to mark up the
abbreviation. This enables all users know what name or term the
abbreviation or acronym shortens while providing a hint to user agents
on how to announce the content.

While `title` can be used to provide a programmatically associated label
for an [`<input>`](../element/input) element, this is not good practice.
Use a [`<label>`](../element/label) instead.

Multiline titles
----------------

The `title` attribute may contain several lines. Each `U+000A LINE FEED`
(`LF`) character represents a line break. Some caution must be taken, as
this means the following renders across two lines:

### HTML

[html]

```html
<p>
  Newlines in <code>title</code> should be taken into account. This
  <span
    title="This is a
multiline title">
    example span
  </span>
  has a title a attribute with a newline.
</p>
<hr />
<pre id="output"></pre>
```

### JavaScript

We can query the `title` attribute and display it in the empty `<pre>`
element as follows:

[js]

```js
const span = document.querySelector("span");
const output = document.querySelector("#output");
output.textContent = span.title;
```

### Result

Title attribute inheritance
---------------------------

If an element has no `title` attribute, then it inherits it from its
parent node, which in turn may inherit it from its parent, and so on.

If this attribute is set to the empty string, it means its ancestors\'
`title`s are irrelevant and shouldn\'t be used in the tooltip for this
element.

### HTML

[html]

```html
<div title="CoolTip">
  <p>Hovering here will show "CoolTip".</p>
  <p title="">Hovering here will show nothing.</p>
</div>
```

### Result

Accessibility concerns
----------------------

Use of the `title` attribute is highly problematic for:

- People using touch-only devices
- People navigating with keyboards
- People navigating with assistive technology such as screen readers
    or magnifiers
- People experiencing fine motor control impairment
- People with cognitive concerns

This is due to inconsistent browser support, compounded by the
additional assistive technology parsing of the browser-rendered page. If
a tooltip effect is desired, it is better to [use a more accessible
technique](https://inclusive-components.design/tooltips-toggletips/)
that can be accessed with the above browsing methods.

- [3.2.5.1. The title attribute \| W3C HTML 5.2: 3. Semantics,
    structure, and APIs of HTML
    documents](https://html.spec.whatwg.org/multipage/dom.html#the-title-attribute)
- [Using the HTML title attribute -- updated \| The Paciello
    Group](https://www.tpgi.com/using-the-html-title-attribute-updated/)
- [Tooltips & Toggletips - Inclusive
    Components](https://inclusive-components.design/tooltips-toggletips/)
- [The Trials and Tribulations of the Title Attribute - 24
    Accessibility](https://www.24a11y.com/2017/the-trials-and-tribulations-of-the-title-attribute/)

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-title-attribute]](https://html.spec.whatwg.org/multipage/dom.html#the-title-attribute)

  ----------------------------------------------------------------------------------------------------

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

`title`

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

`multi-line-support`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

No

No

Yes

See also
--------

- All [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).
- [`HTMLElement.title`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/title)
    that reflects this attribute.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/title>>
