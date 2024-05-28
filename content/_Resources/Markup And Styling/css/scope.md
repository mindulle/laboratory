:scope
======

The `:scope` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents elements that are a reference
point, or scope, for selectors to match against.

[css]

```css
/* Selects a scoped element */
:scope {
  background-color: lime;
}
```

When used in a stylesheet, `:scope` is the same as [`:root`](:root), as
there is currently no way to explicitly establish a scoped element. When
used from a DOM API, such as
[`querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector),
[`querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelectorAll),
[`matches()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/matches),
or
[`Element.closest()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/closest),
`:scope` matches the element on which the method was called.

Syntax
------

[css]

```css
:scope {
  /* ... */
}
```

Examples
--------

### Identity match

This example demonstrates using the `:scope` pseudo-class with the
[`Element.matches()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/matches)
method to match the element on which it\'s called. In this example, if
`:scope` is supported, and the paragraph is within the `:root`\'s scope,
text is displayed in the placeholder \"output\" paragraph.

#### JavaScript

[js]

```js
const paragraph = document.getElementById("para");
const output = document.getElementById("output");

if (paragraph.matches(":scope")) {
  output.textContent = "The first paragraph is its own scope, as expected!";
}
```

#### HTML

[html]

```html
<p id="para">
  This is a paragraph. It is not an interesting paragraph. Sorry about that.
</p>
<p id="output"></p>
```

#### Result

### Direct children

A situation where the `:scope` pseudo-class proves to be useful is when
you need to get a direct descendant of an already retrieved
[`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element).

#### JavaScript

[js]

```js
const context = document.getElementById("context");
const selected = context.querySelectorAll(":scope > div");

document.getElementById("results").innerHTML = Array.prototype.map
  .call(selected, (element) => `#$`)
  .join(", ");
```

#### HTML

[html]

```html
<div id="context">
  <div id="element-1">
    <div id="element-1.1"></div>
    <div id="element-1.2"></div>
  </div>
  <div id="element-2">
    <div id="element-2.1"></div>
  </div>
</div>
<p>
  Selected elements ids :
  <span id="results"></span>
</p>
```

#### Result

The scope of `context` is the element with the
[`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#id)
of `context`. The selected elements are the `div` elements that are
direct children of that context, `element-1` and `element-2`, but not
their descendants.

Specifications
--------------

  ----------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  the-scope-pseudo]](https://drafts.csswg.org/selectors/#the-scope-pseudo)

  ----------------------------------------------------------------------------------

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

`:scope`

27

79

32Firefox 55 removes support for `<style scoped>` but not for the
`:scope` pseudo-class, which is still supported. `<style scoped>` made
it possible to explicitly set up element scopes, but ongoing discussions
about the design of this feature as well as lack of other
implementations resulted in the decision to remove it.

No

15

7

4.4

27

32Firefox 55 removes support for `<style scoped>` but not for the
`:scope` pseudo-class, which is still supported. `<style scoped>` made
it possible to explicitly set up element scopes, but ongoing discussions
about the design of this feature as well as lack of other
implementations resulted in the decision to remove it.

15

7

1.5

`dom_api`

27

79

32

No

15

7

4.4

27

32

15

7

1.5

See also
--------

- The [`:root`](:root) [pseudo-class](pseudo-classes.md)
- [Locating DOM elements using
    selectors](https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model/Locating_DOM_elements_using_selectors)
- [`Element.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector)
    and
    [`Element.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelectorAll)
- [`Document.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)
    and
    [`Document.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)
- [`DocumentFragment.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/querySelector)
    and
    [`DocumentFragment.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/querySelectorAll)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:scope>
