::slotted()
===========

The `::slotted()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-element](pseudo-elements.md) represents any element that has been
placed into a slot inside an HTML template (see [Using templates and
slots](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_templates_and_slots)
for more information).

This only works when used inside CSS placed within a [shadow
DOM](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_shadow_DOM).
Note that this selector won\'t select a text node placed into a slot; it
only targets actual elements.

Try it
------

[css]

```css
/* Selects any element placed inside a slot */
::slotted(*) {
  font-weight: bold;
}

/* Selects any <span> placed inside a slot */
::slotted(span) {
  font-weight: bold;
}
```

Syntax
------

[css]

```css
::slotted(<compound-selector>) {
  /* ... */
}
```

Examples
--------

### Highlighting slotted elements

In this example, we use a template with three slots:

[html]

```html
<template id="person-template">
  <div>
    <h2>Personal ID Card</h2>
    <slot name="person-name">NAME MISSING</slot>
    <ul>
      <li><slot name="person-age">AGE MISSING</slot></li>
      <li><slot name="person-occupation">OCCUPATION MISSING</slot></li>
    </ul>
  </div>
</template>
```

We define the `<person-details>` custom element. In this case, we add
styles with JavaScript, though we could have added them in a
[`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style)
block within the
[`<template>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template)
with the same effect:

[js]

```js
customElements.define(
  "person-details",
  class extends HTMLElement {
    constructor() {
      super();
      let template = document.getElementById("person-template");
      let templateContent = template.content;

      const shadowRoot = this.attachShadow();

      let style = document.createElement("style");
      style.textContent =
        "div " +
        "h2 " +
        "ul " +
        "p " +
        "::slotted(*)  " +
        "::slotted(span)  ";

      shadowRoot.appendChild(style);
      shadowRoot.appendChild(templateContent.cloneNode(true));
    }
  },
);
```

When filling the `style` element with content, you\'ll see that we
select all slotted elements (`::slotted(*)`) and give them a different
font and color. This differentiates them from the slots that haven\'t
been filled. We styled all the slotted
[`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span)s
(`::slotted(span)`) to differentiate the `<span>`s from the
[`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)s.

Our markup includes three custom elements, including a custom element
with an invalid slot name in a source order that differs from the
`<template>`:

[html]

```html
<person-details>
  <p slot="person-name">Wonder Woman</p>
  <span slot="person-age">Immortal</span>
  <span slot="person-occupation">Superhero</span>
</person-details>

<person-details>
  <p slot="person-name">Malala Yousafzai</p>
  <span slot="person-age">17</span>
  <span slot="person-occupation">Activist</span>
</person-details>

<person-details>
  <span slot="person-age">44</span>
  <span slot="not-a-slot-name">Time traveller</span>
  <p slot="person-name">Dr. Who</p>
</person-details>
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------

  [CSS Scoping Module Level 1\
  [\#
  slotted-pseudo]](https://drafts.csswg.org/css-scoping/#slotted-pseudo)

  --------------------------------------------------------------------------------

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

`::slotted`

50

79

63

No

37

10

50

50

63

37

10

5.0

See also
--------

- [`:host`](:host)
- [`:host()`](:host_function)
- [`:host-context()`](:host-context)
- [CSS scoping](css_scoping.md) module
- HTML
    [`slot`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/slot)
    attribute
- HTML
    [`<slot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/slot)
    element
- HTML
    [`<template>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template)
    element
- [Web
    components](https://developer.mozilla.org/en-US/docs/Web/API/Web_components)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/::slotted>
