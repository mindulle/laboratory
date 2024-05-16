\<p\>: The Paragraph element
============================

The `<p>` [HTML](../index) element represents a paragraph. Paragraphs
are usually represented in visual media as blocks of text separated from
adjacent blocks by blank lines and/or first-line indentation, but HTML
paragraphs can be any structural grouping of related content, such as
images or form fields.

Paragraphs are [block-level
elements](https://developer.mozilla.org/en-US/docs/Glossary/Block-level_content),
and notably will automatically close if another block-level element is
parsed before the closing `</p>` tag. See \"Tag omission\" below.

Try it
------

  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  The start tag is required. The end tag may be omitted if the [`<p>`](p) element is immediately followed by an [`<address>`](address), [`<article>`](article), [`<aside>`](aside), [`<blockquote>`](blockquote), [`<details>`](details), [`<div>`](div), [`<dl>`](dl), [`<fieldset>`](fieldset), [`<figcaption>`](figcaption), [`<figure>`](figure), [`<footer>`](footer), [`<form>`](form), [h1](heading_elements), [h2](heading_elements), [h3](heading_elements), [h4](heading_elements), [h5](heading_elements), [h6](heading_elements), [`<header>`](header), [`<hgroup>`](hgroup), [`<hr>`](hr), [`<main>`](main), [`<menu>`](menu), [`<nav>`](nav), [`<ol>`](ol), [`<pre>`](pre), [`<search>`](search), [`<section>`](section), [`<table>`](table), [`<ul>`](ul) or another [`<p>`](p) element, or if there is no more content in the parent element and the parent element is not an [`<a>`](a), [`<audio>`](audio), [`<del>`](del), [`<ins>`](ins), [`<map>`](map), [`<noscript>`](noscript) or [`<video>`](video) element, or an autonomous custom element.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content).
  Implicit ARIA role                            [paragraph](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/structural_roles)
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLParagraphElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParagraphElement)
  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

**Note:** The `align` attribute on `<p>` tags is obsolete and shouldn\'t
be used.

Examples
--------

### HTML

[html]

```html
<p>
  This is the first paragraph of text. This is the first paragraph of text. This
  is the first paragraph of text. This is the first paragraph of text.
</p>
<p>
  This is the second paragraph. This is the second paragraph. This is the second
  paragraph. This is the second paragraph.
</p>
```

### Result

Styling paragraphs
------------------

By default, browsers separate paragraphs with a single blank line.
Alternate separation methods, such as first-line indentation, can be
achieved with
[CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS):

### HTML

[html]

```html
<p>
  Separating paragraphs with blank lines is easiest for readers to scan, but
  they can also be separated by indenting their first lines. This is often used
  to take up less space, such as to save paper in print.
</p>

<p>
  Writing that is intended to be edited, such as school papers and rough drafts,
  uses both blank lines and indentation for separation. In finished works,
  combining both is considered redundant and amateurish.
</p>

<p>
  In very old writing, paragraphs were separated with a special character: ¶,
  the <i>pilcrow</i>. Nowadays, this is considered claustrophobic and hard to
  read.
</p>

<p>
  How hard to read? See for yourself:
  <button data-toggle-text="Oh no! Switch back!">
    Use pilcrow for paragraphs
  </button>
</p>
```

### CSS

[css]

```css
p {
  margin: 0;
  text-indent: 3ch;
}

p.pilcrow {
  text-indent: 0;
  display: inline;
}
p.pilcrow + p.pilcrow::before {
  content: " ¶ ";
}

```

### JavaScript

[js]

```js
document.querySelector("button").addEventListener("click", (event) => {
  document.querySelectorAll("p").forEach((paragraph) => {
    paragraph.classList.toggle("pilcrow");
  });

  [event.target.innerText, event.target.dataset.toggleText] = [
    event.target.dataset.toggleText,
    event.target.innerText,
  ];
});
```

### Result

Accessibility concerns
----------------------

Breaking up content into paragraphs helps make a page more accessible.
Screen-readers and other assistive technology provide shortcuts to let
their users skip to the next or previous paragraph, letting them skim
content like how white space lets visual users skip around.

Using empty `<p>` elements to add space between paragraphs is
problematic for people who navigate with screen-reading technology.
Screen readers may announce the paragraph\'s presence, but not any
content contained within it --- because there is none. This can confuse
and frustrate the person using the screen reader.

If extra space is desired, use
[CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS) properties
like [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)
to create the effect:

[css]

```css
p {
  margin-bottom: 2em; /*increase white space after a paragraph*/
}

```

Specifications
--------------

  -----------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-p-element]](https://html.spec.whatwg.org/multipage/grouping-content.html#the-p-element)

  -----------------------------------------------------------------------------------------------------

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

`p`

1

12

1

Yes

15

1

4.4

18

4

14

1

1.0

See also
--------

- [`<hr>`](hr)
- [`<br>`](br)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p>
