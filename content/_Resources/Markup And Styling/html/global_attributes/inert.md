inert
=====

The `inert` [global attribute](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) is a Boolean
attribute indicating that the browser will ignore the element. With the
`inert` attribute, all of the element\'s flat tree descendants (such as
modal [`<dialog>`](../element/dialog)s) that don\'t otherwise escape
inertness are ignored. The `inert` attribute also makes the browser
ignore input events sent by the user, including focus-related events and
events from assistive technologies.

Specifically, `inert` does the following:

- Prevents the
    [`click`](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event)
    event from being fired when the user clicks on the element.
- Prevents the
    [`focus`](https://developer.mozilla.org/en-US/docs/Web/API/Element/focus_event)
    event from being raised by preventing the element from gaining
    focus.
- Hides the element and its content from assistive technologies by
    excluding them from the accessibility tree.

[html]

```html
<body inert>
  <!-- content -->
</body>
```

The `inert` attribute can be added to sections of content that should
not be interactive. When an element is inert, it along with all of the
element\'s descendants, including normally interactive elements such as
links, buttons, and form controls are disabled because they cannot
receive focus or be clicked.

The `inert` attribute can also be added to elements that should be
offscreen or hidden. An inert element, along with its descendants, gets
removed from the tab order and accessibility tree.

**Note:** While `inert` is a global attribute and can be applied to any
element, it is generally used for sections of content. To make
individual controls \"inert\", consider using the
[`disabled`](../attributes/disabled) attribute, along with CSS
[`:disabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled)
styles, instead.

Accessibility concerns
----------------------

Use careful consideration for accessibility when applying the `inert`
attribute. By default, there is no visual way to tell whether or not an
element or its subtree is inert. As a web developer, it is your
responsibility to clearly indicate the content parts that are active and
those that are inert.

While providing visual and non-visual cues about content inertness, also
remember that the visual viewport may contain only sections of content.
Users may be zoomed in to a small section of content, or users may not
be able to view the content at all. Inert sections not being obviously
inert can lead to frustration and bad user experience.

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-inert-attribute]](https://html.spec.whatwg.org/multipage/interaction.html#the-inert-attribute)

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

`inert`

102

102

112

No

88

15.5

102

102

112

70

15.5

19.0

See also
--------

- HTML [`<dialog>`](../element/dialog) element
- [`HTMLElement.inert`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/inert)
    HTML DOM property
- [Introducing inert](https://developer.chrome.com/articles/inert/)
- [The \"inert\" attribute is finally coming to the
    web](https://www.stefanjudis.com/blog/the-inert-attribute-is-finally-coming-to-the-web/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/inert>>
