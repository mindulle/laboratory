:target-within
==============

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `:target-within`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents an element that is a target
element or *contains* an element that is a target. A target element is a
unique element with an
[`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#id)
matching the URL\'s fragment. In other words, it represents an element
that is itself matched by the [`:target`](:target) pseudo-class or has a
descendant that is matched by `:target`. (This includes descendants in
[shadow
trees](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_shadow_DOM).)

[css]

```css
/* Selects a <div> when one of its descendants is a target */
div:target-within {
  background: cyan;
}
```

Syntax
------

[css]

```css
:target-within {
  /* ... */
}
```

Examples
--------

### Highlighting an article

The `:target-within` pseudo-class can be used to highlight the article
if anything inside it has been directly linked to. The `:target`
pseudo-class is also being used to show which item has been targeted.

#### HTML

[html]

```html
<h3>Table of Contents</h3>
<ol>
  <li><a href="#p1">Jump to the first paragraph!</a></li>
  <li><a href="#p2">Jump to the second paragraph!</a></li>
</ol>

<article>
  <h3>My Fun Article</h3>
  <p id="p1">
    You can target <i>this paragraph</i> using a URL fragment. Click on the link
    above to try out!
  </p>
  <p id="p2">
    This is <i>another paragraph</i>, also accessible from the links above.
    Isn't that delightful?
  </p>
</article>
```

#### CSS

[css]

```css
article:target-within {
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

  --------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  the-target-within-pseudo]](https://drafts.csswg.org/selectors/#the-target-within-pseudo)

  --------------------------------------------------------------------------------------------------

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

`:target-within`

No

No

No

No

No

No

No

No

No

No

No

No

See also
--------

- [`:target`](:target)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:target-within>
