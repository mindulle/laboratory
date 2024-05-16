popover
=======

The `popover` [global attribute](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) is used to
designate an element as a popover element.

Popover elements are hidden via `display: none` until opened via an
invoking/control element (i.e. a `<button>` or `<input type="button">`
with a [`popovertarget`](../element/button#popovertarget) attribute) or
a
[`HTMLElement.showPopover()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/showPopover)
call.

When open, popover elements will appear above all other elements in the
[top
layer](https://developer.mozilla.org/en-US/docs/Glossary/Top_layer), and
won\'t be influenced by parent elements\'
[`position`](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
or
[`overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)
styling.

A popover attribute can have values
[`"auto"`](https://developer.mozilla.org/en-US/docs/Web/API/Popover_API/Using#auto_state_and_light_dismiss)
(default) or
[`"manual"`](https://developer.mozilla.org/en-US/docs/Web/API/Popover_API/Using#using_manual_popover_state).
Popovers that have the `auto` state can be \"light dismissed\" by
selecting outside the popover area, and generally only allow one popover
to be displayed on-screen at a time. By contrast, `manual` popovers must
always be explicitly hidden, but allow for use cases such as nested
popovers in menus.

For detailed information on usage, see the [Popover
API](https://developer.mozilla.org/en-US/docs/Web/API/Popover_API)
landing page.

Examples
--------

The following will render a button which will open a popover element.

[html]

```html
<button popovertarget="my-popover">Open Popover</button>

<div popover id="my-popover">Greetings, one and all!</div>
```

**Note:** See our [Popover API examples landing
page](https://mdn.github.io/dom-examples/popover-api/) to access the
full collection of MDN popover examples.

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-popover-attribute]](https://html.spec.whatwg.org/multipage/popover.html#the-popover-attribute)

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

`popover`

114

114

114

No

100

17

114

114

No

No

17

No

See also
--------

- [Popover
    API](https://developer.mozilla.org/en-US/docs/Web/API/Popover_API)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/popover>>
