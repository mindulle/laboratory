:disabled
=========

The `:disabled` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents any disabled element. An
element is disabled if it can\'t be activated (selected, clicked on,
typed into, etc.) or accept focus. The element also has an enabled
state, in which it can be activated or accept focus.

Try it
------

Syntax
------

[css]

```css
:disabled {
  /* ... */
}
```

Examples
--------

This example shows a basic shipping form. It uses the
[JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[`change`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event)
event to let the user enable/disable the billing fields.

### HTML

[html]

```html
<form action="#">
  <fieldset id="shipping">
    <legend>Shipping address</legend>
    <input type="text" placeholder="Name" />
    <input type="text" placeholder="Address" />
    <input type="text" placeholder="Zip Code" />
  </fieldset>
  <br />
  <fieldset id="billing">
    <legend>Billing address</legend>
    <label for="billing-checkbox">Same as shipping address:</label>
    <input type="checkbox" id="billing-checkbox" checked />
    <br />
    <input type="text" placeholder="Name" disabled />
    <input type="text" placeholder="Address" disabled />
    <input type="text" placeholder="Zip Code" disabled />
  </fieldset>
</form>
```

### CSS

[css]

```css
input[type="text"]:disabled {
  background: #ccc;
}
```

### JavaScript

[js]

```js
// Wait for the page to finish loading
document.addEventListener(
  "DOMContentLoaded",
  () => {
    // Attach `change` event listener to checkbox
    document.getElementById("billing-checkbox").onchange = toggleBilling;
  },
  false,
);

function toggleBilling() {
  // Select the billing text fields
  const billingItems = document.querySelectorAll('#billing input[type="text"]');

  // Toggle the billing text fields
  billingItems.forEach((item) => {
    item.disabled = !item.disabled;
  });
}
```

### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-disabled]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-disabled)

[Selectors Level 4\
  [\# enableddisabled]](https://drafts.csswg.org/selectors/#enableddisabled)
  ------------------------------------------------------------------------------------------------------------

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

`:disabled`

1

12Edge does not recognize `:disabled` on the
[`<fieldset>`](https://developer.mozilla.org/docs/Web/HTML/Element/fieldset)
element.

1

9Internet Explorer does not recognize `:disabled` on the
[`<fieldset>`](https://developer.mozilla.org/docs/Web/HTML/Element/fieldset)
element.

9

3.1

2

18

4

10.1

2

1.0

See also
--------

- [`:enabled`](:enabled)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled>
