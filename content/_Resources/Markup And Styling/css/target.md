:target
=======

The `:target` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents a unique element (the *target
element*) with an
[`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#id)
matching the URL\'s fragment.

[css]

```css
/* Selects an element with an ID matching the current URL's fragment */
:target {
  border: 2px solid black;
}
```

For example, the following URL has a fragment (denoted by the *\#* sign)
that points to an element called `section2`:

[url]

```
http://www.example.com/index.html#section2
```

The following element would be selected by a `:target` selector when the
current URL is equal to the above:

[html]

```html
<section id="section2">Example</section>
```

Syntax
------

[css]

```css
:target {
  /* ... */
}
```

**Note:** Due to [a possible bug in the CSS
specification](https://discourse.wicg.io/t/target-css-does-not-work-because-shadowroot-does-not-set-a-target-element/2070),
`:target` doesn\'t work within a [web
component](https://developer.mozilla.org/en-US/docs/Web/API/Web_components)
because the [shadow
root](https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot)
doesn\'t pass the target element down to the shadow tree.

Examples
--------

### A table of contents

The `:target` pseudo-class can be used to highlight the portion of a
page that has been linked to from a table of contents.

#### HTML

[html]

```html
<h3>Table of Contents</h3>
<ol>
  <li><a href="#p1">Jump to the first paragraph!</a></li>
  <li><a href="#p2">Jump to the second paragraph!</a></li>
  <li>
    <a href="#nowhere">
      This link goes nowhere, because the target doesn't exist.
    </a>
  </li>
</ol>

<h3>My Fun Article</h3>
<p id="p1">
  You can target <i>this paragraph</i> using a URL fragment. Click on the link
  above to try out!
</p>
<p id="p2">
  This is <i>another paragraph</i>, also accessible from the links above. Isn't
  that delightful?
</p>
```

#### CSS

[css]

```css
p:target {
  background-color: gold;
}

/* Add a pseudo-element inside the target element */
p:target::before {
  font: 70% sans-serif;
  content: "►";
  color: limegreen;
  margin-right: 0.25em;
}

/* Style italic elements within the target element */
p:target i {
  color: red;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-target]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-target)

[Selectors Level 4\
  [\# the-target-pseudo]](https://drafts.csswg.org/selectors/#the-target-pseudo)
  --------------------------------------------------------------------------------------------------------

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

`:target`

1

12

1

9

9.5

1.3

2

18

4

10.1

2

1.0

See also
--------

- [Using the :target pseudo-class in
    selectors](css_selectors/using_the_:target_pseudo-class_in_selectors)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:target>
