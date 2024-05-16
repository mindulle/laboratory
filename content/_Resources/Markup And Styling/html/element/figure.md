\<figure\>: The Figure with Optional Caption element
====================================================

The `<figure>` [HTML](../index) element represents self-contained
content, potentially with an optional caption, which is specified using
the [`<figcaption>`](figcaption) element. The figure, its caption, and
its contents are referenced as a single unit.

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

- Usually a `<figure>` is an image, illustration, diagram, code
    snippet, etc., that is referenced in the main flow of a document,
    but that can be moved to another part of the document or to an
    appendix without affecting the main flow.
- A caption can be associated with the `<figure>` element by inserting
    a [`<figcaption>`](figcaption) inside it (as the first or the last
    child). The first `<figcaption>` element found in the figure is
    presented as the figure\'s caption.

Examples
--------

### Images

[html]

```html
<!-- Just an image -->
<figure>
  <img src="favicon-192x192.png" alt="The beautiful MDN logo." />
</figure>

<!-- Image with a caption -->
<figure>
  <img src="favicon-192x192.png" alt="The beautiful MDN logo." />
  <figcaption>MDN Logo</figcaption>
</figure>
```

#### Result

### Code snippets

[html]

```html
<figure>
  <figcaption>Get browser details using <code>navigator</code>.</figcaption>
  <pre>
function NavigatorExample() {
  var txt;
  txt = "Browser CodeName: " + navigator.appCodeName + "; ";
  txt+= "Browser Name: " + navigator.appName + "; ";
  txt+= "Browser Version: " + navigator.appVersion  + "; ";
  txt+= "Cookies Enabled: " + navigator.cookieEnabled  + "; ";
  txt+= "Platform: " + navigator.platform  + "; ";
  txt+= "User-agent header: " + navigator.userAgent  + "; ";
  console.log("NavigatorExample", txt);
}
  </pre>
</figure>
```

#### Result

### Quotations

[html]

```html
<figure>
  <figcaption><b>Edsger Dijkstra:</b></figcaption>
  <blockquote>
    If debugging is the process of removing software bugs, then programming must
    be the process of putting them in.
  </blockquote>
</figure>
```

#### Result

### Poems

[html]

```html
<figure>
  <p style="white-space:pre">
    Bid me discourse, I will enchant thine ear, Or like a fairy trip upon the
    green, Or, like a nymph, with long dishevelled hair, Dance on the sands, and
    yet no footing seen: Love is a spirit all compact of fire, Not gross to
    sink, but light, and will aspire.
  </p>
  <figcaption><cite>Venus and Adonis</cite>, by William Shakespeare</figcaption>
</figure>
```

#### Result

Technical summary
-----------------

  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [palpable content](../content_categories#palpable_content).
  Permitted content                             A [`<figcaption>`](figcaption) element, followed by [flow content](../content_categories#flow_content); or flow content followed by a [`<figcaption>`](figcaption) element; or flow content.
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [Flow content](../content_categories#flow_content).
  Implicit ARIA role                            [figure](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/figure_role)
  Permitted ARIA roles                          With no [figcaption](figcaption) descendant: [any](https://www.w3.org/TR/html-aria/#dfn-any-role), otherwise no permitted roles
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-figure-element]](https://html.spec.whatwg.org/multipage/grouping-content.html#the-figure-element)

  ---------------------------------------------------------------------------------------------------------------

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

`figure`

8

12

4

9

11

5.1

4.4

18

4

11

5

1.0

See also
--------

- The [`<figcaption>`](figcaption) element.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure>>
