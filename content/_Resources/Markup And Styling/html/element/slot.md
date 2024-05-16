\<slot\>: The Web Component Slot element
========================================

The `<slot>` [HTML](../index) element---part of the [Web
Components](https://developer.mozilla.org/en-US/docs/Web/API/Web_components)
technology suite---is a placeholder inside a web component that you can
fill with your own markup, which lets you create separate DOM trees and
present them together.

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`name`](#name)

:   The slot\'s name.

    A ***named slot*** is a `<slot>` element with a `name` attribute.

Examples
--------

[html]

```html
<template id="element-details-template">
  <style>
    details {
      font-family: "Open Sans Light", Helvetica, Arial, sans-serif;
    }
    .name {
      font-weight: bold;
      color: #217ac0;
      font-size: 120%;
    }
    h4 {
      margin: 10px 0 -8px 0;
      background: #217ac0;
      color: white;
      padding: 2px 6px;
      border: 1px solid #cee9f9;
      border-radius: 4px;
    }
    .attributes {
      margin-left: 22px;
      font-size: 90%;
    }
    .attributes p {
      margin-left: 16px;
      font-style: italic;
    }
  </style>
  <details>
    <summary>
      <code class="name">
        &lt;<slot name="element-name">NEED NAME</slot>&gt;
      </code>
      <span class="desc"><slot name="description">NEED DESCRIPTION</slot></span>
    </summary>
    <div class="attributes">
      <h4>Attributes</h4>
      <slot name="attributes"><p>None</p></slot>
    </div>
  </details>
  <hr />
</template>
```

**Note:** You can see this complete example in action at
[element-details](https://github.com/mdn/web-components-examples/tree/main/element-details)
(see it [running
live](https://mdn.github.io/web-components-examples/element-details/)).
In addition, you can find an explanation at [Using templates and
slots](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_templates_and_slots).

Technical summary
-----------------

  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content)
  Permitted content                             [Transparent](../content_categories#transparent_content_model)
  Events                                        [`slotchange`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSlotElement/slotchange_event)
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content)
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLSlotElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSlotElement)
  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-slot-element]](https://html.spec.whatwg.org/multipage/scripting.html#the-slot-element)

[DOM Standard\
  [\# shadow-tree-slots]](https://dom.spec.whatwg.org/#shadow-tree-slots)
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

`slot`

53

79

63

No

40

10

53

53

63

41

10

6.0

`name`

53

79

63

No

40

10

53

53

63

41

10

6.0

See also
--------

- HTML [`<template>`](template) element
- HTML [`slot`](../global_attributes/slot) attribute
- CSS
    [`::slotted`](https://developer.mozilla.org/en-US/docs/Web/CSS/::slotted)
    pseudo-element
- [CSS
    scoping](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scoping)
    module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/slot>>
