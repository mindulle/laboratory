is
==

The `is` [global attribute](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) allows you to specify
that a standard HTML element should behave like a defined custom
built-in element (see [Using custom
elements](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_custom_elements)
for more details).

This attribute can only be used if the specified custom element name has
been successfully
[defined](https://developer.mozilla.org/en-US/docs/Web/API/CustomElementRegistry/define)
in the current document, and extends the element type it is being
applied to.

Examples
--------

The following code is taken from our
[word-count-web-component](https://github.com/mdn/web-components-examples/tree/main/word-count-web-component)
example ([see it live
also](https://mdn.github.io/web-components-examples/word-count-web-component/)).

[js]

```js
// Create a class for the element
class WordCount extends HTMLParagraphElement {
  constructor() {
    // Always call super first in constructor
    super();

    // Constructor contents omitted for brevity
    // …
  }
}

// Define the new element
customElements.define("word-count", WordCount, { extends: "p" });
```

[html]

```html
<p is="word-count"></p>
```

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  attr-is]](https://html.spec.whatwg.org/multipage/custom-elements.html#attr-is)

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

`is`

67

79

63

No

54

No

67

67

63

48

No

9.0

See also
--------

- All [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/is>>
