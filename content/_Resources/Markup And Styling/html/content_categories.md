Content categories
==================

Most [HTML](index) elements are a member of one or more **content
categories** --- these categories group elements that share common
characteristics. This is a loose grouping (it doesn\'t actually create a
relationship among elements of these categories), but they help define
and describe the categories\' shared behavior and their associated
rules, especially when you come upon their intricate details. It\'s also
possible for elements to not be a member of *any* of these categories.

There are three types of content categories:

- Main content categories, which describe common rules shared by many
    elements.
- Form-related content categories, which describe rules common to
    form-related elements.
- Specific content categories, which describe rare categories shared
    only by a few elements, sometimes only in a specific context.

**Note:** A more detailed discussion of these content categories and
their comparative functionalities is beyond the scope of this article;
for that, you may wish to read the [relevant portions of the HTML
specification](https://html.spec.whatwg.org/multipage/dom.html#kinds-of-content).

[](https://developer.mozilla.org/en-US/docs/Web/HTML/Content_categories/content_categories_venn.png)

Main content categories
-----------------------

### Metadata content

Elements belonging to the *metadata content* category modify the
presentation or the behavior of the rest of the document, set up links
to other documents, or convey other *out-of-band* information.

Elements belonging to this category are [`<base>`](element/base),
[`<link>`](element/link), [`<meta>`](element/meta),
[`<noscript>`](element/noscript), [`<script>`](element/script),
[`<style>`](element/style) and [`<title>`](element/title).

### Flow content

Flow content is a broad category that encompasses most elements that can
go inside the [`<body>`](element/body) element, including heading
elements, sectioning elements, phrasing elements, embedding elements,
interactive elements, and form-related elements. It also includes text
nodes (but not those that only consist of white space characters).

The flow elements are:

- [`<a>`](element/a)
- [`<abbr>`](element/abbr)
- [`<address>`](element/address)
- [`<article>`](element/article)
- [`<aside>`](element/aside)
- [`<audio>`](element/audio)
- [`<b>`](element/b)
- [`<bdo>`](element/bdo)
- [`<bdi>`](element/bdi)
- [`<blockquote>`](element/blockquote)
- [`<br>`](element/br)
- [`<button>`](element/button)
- [`<canvas>`](element/canvas)
- [`<cite>`](element/cite)
- [`<code>`](element/code)
- [`<data>`](element/data)
- [`<datalist>`](element/datalist)
- [`<del>`](element/del)
- [`<details>`](element/details)
- [`<dfn>`](element/dfn)
- [`<dialog>`](element/dialog)
- [`<div>`](element/div)
- [`<dl>`](element/dl)
- [`<em>`](element/em)
- [`<embed>`](element/embed)
- [`<fieldset>`](element/fieldset)
- [`<figure>`](element/figure)
- [`<footer>`](element/footer)
- [`<form>`](element/form)
- [h1](element/heading_elements)
- [h2](element/heading_elements)
- [h3](element/heading_elements)
- [h4](element/heading_elements)
- [h5](element/heading_elements)
- [h6](element/heading_elements)
- [`<header>`](element/header)
- [`<hgroup>`](element/hgroup)
- [`<hr>`](element/hr)
- [`<i>`](element/i)
- [`<iframe>`](element/iframe)
- [`<img>`](element/img)
- [`<input>`](element/input)
- [`<ins>`](element/ins)
- [`<kbd>`](element/kbd)
- [`<label>`](element/label)
- [`<main>`](element/main)
- [`<map>`](element/map)
- [`<mark>`](element/mark)
- `<math>`
- [`<menu>`](element/menu)
- [`<meter>`](element/meter)
- [`<nav>`](element/nav)
- [`<noscript>`](element/noscript)
- [`<object>`](element/object)
- [`<ol>`](element/ol)
- [`<output>`](element/output)
- [`<p>`](element/p)
- [`<picture>`](element/picture)
- [`<pre>`](element/pre)
- [`<progress>`](element/progress)
- [`<q>`](element/q)
- [`<ruby>`](element/ruby)
- [`<s>`](element/s)
- [`<samp>`](element/samp)
- [`<search>`](element/search)
- [`<script>`](element/script)
- [`<section>`](element/section)
- [`<select>`](element/select)
- [`<slot>`](element/slot)
- [`<small>`](element/small)
- [`<span>`](element/span)
- [`<strong>`](element/strong)
- [`<sub>`](element/sub)
- [`<sup>`](element/sup)
- [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg)
- [`<table>`](element/table)
- [`<template>`](element/template)
- [`<textarea>`](element/textarea)
- [`<time>`](element/time)
- [`<u>`](element/u)
- [`<ul>`](element/ul)
- [`<var>`](element/var)
- [`<video>`](element/video)
- [`<wbr>`](element/wbr)
- Plain text

A few other elements belong to this category, but only if a specific
condition is fulfilled:

- [`<area>`](element/area), if it is a descendant of a
    [`<map>`](element/map) element
- [`<link>`](element/link), if the
    [itemprop](global_attributes/itemprop) attribute is present
- [`<meta>`](element/meta), if the
    [itemprop](global_attributes/itemprop) attribute is present
- [`<style>`](element/style), if the `scoped`
    [Deprecated] attribute is present

### Sectioning content

Sectioning content is a subset of flow content, and can be used
everywhere flow content is expected. Elements belonging to the
sectioning content model create a [section in the current
outline](element/heading_elements) that defines the scope of
[`<header>`](element/header) elements, [`<footer>`](element/footer)
elements, and [heading content](#heading_content).

Elements belonging to this category are [`<article>`](element/article),
[`<aside>`](element/aside), [`<nav>`](element/nav), and
[`<section>`](element/section).

### Heading content

Heading content is a subset of flow content, which defines the title of
a section, whether marked by an explicit [sectioning
content](#sectioning_content) element, or implicitly defined by the
heading content itself. Heading content can be used everywhere flow
content is expected.

Elements belonging to this category are [h1](element/heading_elements),
[h2](element/heading_elements), [h3](element/heading_elements),
[h4](element/heading_elements), [h5](element/heading_elements),
[h6](element/heading_elements) and [`<hgroup>`](element/hgroup).

**Note:** Though likely to contain heading content, the
[`<header>`](element/header) is not heading content itself.

**Note:** The [`<hgroup>`](element/hgroup) element is not recommended as
it does not work properly with assistive technologies. It was removed
from the W3C HTML specification prior to HTML 5 being finalized, but is
still part of the WHATWG specification and is at least partially
supported by most browsers.

### Phrasing content

Phrasing content is a subset of flow content that defines the text and
the markup it contains, and can be used everywhere flow content is
expected. Runs of phrasing content make up paragraphs.

Elements belonging to this category are:

- [`<abbr>`](element/abbr)
- [`<audio>`](element/audio)
- [`<b>`](element/b)
- [`<bdi>`](element/bdi)
- [`<bdo>`](element/bdo)
- [`<br>`](element/br)
- [`<button>`](element/button)
- [`<canvas>`](element/canvas)
- [`<cite>`](element/cite)
- [`<code>`](element/code)
- [`<data>`](element/data)
- [`<datalist>`](element/datalist)
- [`<dfn>`](element/dfn)
- [`<em>`](element/em)
- [`<embed>`](element/embed)
- [`<i>`](element/i)
- [`<iframe>`](element/iframe)
- [`<img>`](element/img)
- [`<input>`](element/input)
- [`<kbd>`](element/kbd)
- [`<label>`](element/label)
- [`<mark>`](element/mark)
- `<math>`
- [`<meter>`](element/meter)
- [`<noscript>`](element/noscript)
- [`<object>`](element/object)
- [`<output>`](element/output)
- [`<picture>`](element/picture)
- [`<progress>`](element/progress)
- [`<q>`](element/q)
- [`<ruby>`](element/ruby)
- [`<s>`](element/s)
- [`<samp>`](element/samp)
- [`<script>`](element/script)
- [`<select>`](element/select)
- [`<slot>`](element/slot)
- [`<small>`](element/small)
- [`<span>`](element/span)
- [`<strong>`](element/strong)
- [`<sub>`](element/sub)
- [`<sup>`](element/sup)
- [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg)
- [`<template>`](element/template)
- [`<textarea>`](element/textarea)
- [`<time>`](element/time)
- [`<u>`](element/u)
- [`<var>`](element/var)
- [`<video>`](element/video)
- [`<wbr>`](element/wbr) and plain text (not only consisting of white
    spaces characters).

A few other elements belong to this category, but only if a specific
condition is fulfilled:

- [`<a>`](element/a), if it contains only phrasing content
- [`<area>`](element/area), if it is a descendant of a [`<map>`](element/map) element
- [`<del>`](element/del), if it contains only phrasing content
- [`<ins>`](element/ins), if it contains only phrasing content
- [`<link>`](element/link), if the [itemprop](global_attributes/itemprop) attribute is present
- [`<map>`](element/map), if it contains only phrasing content
- [`<meta>`](element/meta), if the [itemprop](global_attributes/itemprop) attribute is present

### Embedded content

Embedded content is a subset of flow content that imports another
resource or inserts content from another markup language or namespace
into the document, and can be used everywhere flow content is expected.
Elements that belong to this category include:

- [`<audio>`](element/audio)
- [`<canvas>`](element/canvas)
- [`<embed>`](element/embed)
- [`<iframe>`](element/iframe)
- [`<img>`](element/img)
- `<math>`
- [`<object>`](element/object)
- [`<picture>`](element/picture)
- [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg)
- [`<video>`](element/video).

### Interactive content

Interactive content is a subset of flow content that includes elements
that are specifically designed for user interaction, and can be used
everywhere flow content is expected. Elements that belong to this
category include:

- [`<button>`](element/button)
- [`<details>`](element/details)
- [`<embed>`](element/embed)
- [`<iframe>`](element/iframe)
- [`<label>`](element/label)
- [`<select>`](element/select), and [`<textarea>`](element/textarea).

Some elements belong to this category only under specific conditions:

- [`<a>`](element/a), if the [`href`](element/a#href) attribute is
    present
- [`<audio>`](element/audio), if the
    [`controls`](element/audio#controls) attribute is present
- [`<img>`](element/img), if the [`usemap`](element/img#usemap)
    attribute is present
- [`<input>`](element/input), if the [type](element/input#type)
    attribute is not in the hidden state
- [`<object>`](element/object), if the
    [`usemap`](element/object#usemap) attribute is present
- [`<video>`](element/video), if the
    [`controls`](element/video#controls) attribute is present

### Palpable content

Content is palpable when it\'s neither empty nor hidden; it is content
that is rendered and is substantive. Elements whose model is flow
content should have at least one node which is palpable.

### Form-associated content

Form-associated content is a subset of flow content comprising elements
that have a form owner, exposed by a **form** attribute, and can be used
everywhere flow content is expected. A form owner is either the
containing [`<form>`](element/form) element or the element whose id is
specified in the **form** attribute.

- [`<button>`](element/button)
- [`<fieldset>`](element/fieldset)
- [`<input>`](element/input)
- [`<label>`](element/label)
- [`<meter>`](element/meter)
- [`<object>`](element/object)
- [`<output>`](element/output)
- [`<progress>`](element/progress)
- [`<select>`](element/select)
- [`<textarea>`](element/textarea)

This category contains several sub-categories:

[listed](#listed)

:   Elements that are listed in the
    [`form.elements`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements)
    and `fieldset.elements` collections. Contains
    [`<button>`](element/button), [`<fieldset>`](element/fieldset),
    [`<input>`](element/input), [`<object>`](element/object),
    [`<output>`](element/output), [`<select>`](element/select), and
    [`<textarea>`](element/textarea).

[labelable](#labelable)

:   Elements that can be associated with [`<label>`](element/label)
    elements. Contains [`<button>`](element/button),
    [`<input>`](element/input), [`<meter>`](element/meter),
    [`<output>`](element/output), [`<progress>`](element/progress),
    [`<select>`](element/select), and [`<textarea>`](element/textarea).

[submittable](#submittable)

:   Elements that can be used for constructing the form data set when
    the form is submitted. Contains [`<button>`](element/button),
    [`<input>`](element/input), [`<object>`](element/object),
    [`<select>`](element/select), and [`<textarea>`](element/textarea).

[resettable](#resettable)

:   Elements that can be affected when a form is reset. Contains
    [`<input>`](element/input), [`<output>`](element/output),
    [`<select>`](element/select), and [`<textarea>`](element/textarea).

Secondary categories
--------------------

There are some secondary classifications of elements that can be useful
to be aware of as well.

### Script-supporting elements

**Script-supporting elements** are elements which don\'t directly
contribute to the rendered output of a document. Instead, they serve to
support scripts, either by containing or specifying script code
directly, or by specifying data that will be used by scripts.

The script-supporting elements are:

- [`<script>`](element/script)
- [`<template>`](element/template)

Transparent content model
-------------------------

If an element has a transparent content model, then its contents must be
structured such that they would be valid HTML 5, even if the transparent
element were removed and replaced by the child elements.

For example, the [`<del>`](element/del) and [`<ins>`](element/ins)
elements are transparent:

[html]

```html
<p>
  We hold these truths to be <del><em>sacred &amp; undeniable</em></del>
  <ins>self-evident</ins>.
</p>
```

If those elements were removed, this fragment would still be valid HTML
(if not correct English).

[html]

```html
<p>We hold these truths to be <em>sacred &amp; undeniable</em> self-evident.</p>
```

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Content_categories>>
