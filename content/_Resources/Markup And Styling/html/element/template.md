\<template\>: The Content Template element
==========================================

The `<template>` [HTML](../index) element is a mechanism for holding
[HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML) that is
not to be rendered immediately when a page is loaded but may be
instantiated subsequently during runtime using JavaScript.

Think of a template as a content fragment that is being stored for
subsequent use in the document. While the parser does process the
contents of the `<template>` element while loading the page, it does so
only to ensure that those contents are valid; the element\'s contents
are not rendered, however.

Attributes
----------

The only standard attributes that the `<template>` element supports are
the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

In Chromium-based browsers, the `<template>` element also supports a
non-standard [`shadowrootmode`
attribute](https://github.com/mfreed7/declarative-shadow-dom/blob/master/README.md#syntax),
as part of an experimental [\"Declarative Shadow
DOM\"](https://developer.chrome.com/articles/declarative-shadow-dom/)
proposal. In supporting browsers, a `<template>` element with the
`shadowrootmode` attribute is detected by the HTML parser and
immediately applied as the shadow root of its parent element.
`shadowrootmode` can take a value of `open` or `closed`; these are
equivalent to the `open` and `closed` values of the
[`Element.attachShadow()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/attachShadow)
`mode` option.

Also, the corresponding
[`HTMLTemplateElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTemplateElement)
interface includes a standard
[`content`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTemplateElement/content)
property (without an equivalent content/markup attribute). This
`content` property is read-only and holds a
[`DocumentFragment`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment)
that contains the DOM subtree represented by the template. Be careful
when using the `content` property because the returned
`DocumentFragment` can exhibit unexpected behavior. For more details,
see the [Avoiding DocumentFragment
pitfalls](#avoiding_documentfragment_pitfalls) section below.

Examples
--------

First we start with the HTML portion of the example.

[html]

```html
<table id="producttable">
  <thead>
    <tr>
      <td>UPC_Code</td>
      <td>Product_Name</td>
    </tr>
  </thead>
  <tbody>
    <!-- existing data could optionally be included here -->
  </tbody>
</table>

<template id="productrow">
  <tr>
    <td class="record"></td>
    <td></td>
  </tr>
</template>
```

First, we have a table into which we will later insert content using
JavaScript code. Then comes the template, which describes the structure
of an HTML fragment representing a single table row.

Now that the table has been created and the template defined, we use
JavaScript to insert rows into the table, with each row being
constructed using the template as its basis.

[js]

```js
// Test to see if the browser supports the HTML template element by checking
// for the presence of the template element's content attribute.
if ("content" in document.createElement("template")) {
  // Instantiate the table with the existing HTML tbody
  // and the row with the template
  const tbody = document.querySelector("tbody");
  const template = document.querySelector("#productrow");

  // Clone the new row and insert it into the table
  const clone = template.content.cloneNode(true);
  let td = clone.querySelectorAll("td");
  td[0].textContent = "1235646565";
  td[1].textContent = "Stuff";

  tbody.appendChild(clone);

  // Clone the new row and insert it into the table
  const clone2 = template.content.cloneNode(true);
  td = clone2.querySelectorAll("td");
  td[0].textContent = "0384928528";
  td[1].textContent = "Acme Kidney Beans 2";

  tbody.appendChild(clone2);
} else {
  // Find another way to add the rows to the table because
  // the HTML template element is not supported.
}
```

The result is the original HTML table, with two new rows appended to it
via JavaScript:

Avoiding DocumentFragment pitfalls
----------------------------------

When a
[`DocumentFragment`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment)
value is passed,
[`Node.appendChild`](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild)
and similar methods move only the *child nodes* of that value into the
target node. Therefore, it is usually preferable to attach event
handlers to the children of a `DocumentFragment`, rather than to the
`DocumentFragment` itself.

Consider the following HTML and JavaScript:

### HTML

[html]

```html
<div id="container"></div>

<template id="template">
  <div>Click me</div>
</template>
```

### JavaScript

[js]

```js
const container = document.getElementById("container");
const template = document.getElementById("template");

function clickHandler(event) {
  event.target.append(" — Clicked this div");
}

const firstClone = template.content.cloneNode(true);
firstClone.addEventListener("click", clickHandler);
container.appendChild(firstClone);

const secondClone = template.content.cloneNode(true);
secondClone.children[0].addEventListener("click", clickHandler);
container.appendChild(secondClone);
```

### Result

Since `firstClone` is a `DocumentFragment`, only its children are added
to `container` when `appendChild` is called; the event handlers of
`firstClone` are not copied. In contrast, because an event handler is
added to the first *child node* of `secondClone`, the event handler is
copied when `appendChild` is called, and clicking on it works as one
would expect.

Technical summary
-----------------

  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Metadata content](../content_categories#metadata_content), [flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), [script-supporting element](../content_categories#script-supporting_elements)
  Permitted content                             No restrictions
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [metadata content](../content_categories#metadata_content), [phrasing content](../content_categories#phrasing_content), or [script-supporting elements](../content_categories#script-supporting_elements). Also allowed as a child of a [`<colgroup>`](colgroup) element that does *not* have a [`span`](colgroup#span) attribute.
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLTemplateElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTemplateElement)
  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-template-element]](https://html.spec.whatwg.org/multipage/scripting.html#the-template-element)

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

`template`

26

13

22

No

15

8

Yes

26

22

14

8

1.5

`shadowrootmode`

11190--111

11190--111

No

No

9776--97

16.4

11190--111

11190--111

No

64

16.4

22.015.0--22.0

See also
--------

- Web components: [`<slot>`](slot) (and historical: `<shadow>`)
- [Using templates and
    slots](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_templates_and_slots)
- [CSS
    scoping](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scoping)
    module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template>>
