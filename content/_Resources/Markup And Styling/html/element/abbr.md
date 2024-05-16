\<abbr\>: The Abbreviation element
==================================

The `<abbr>` [HTML](../index) element represents an abbreviation or
acronym.

When including an abbreviation or acronym, provide a full expansion of
the term in plain text on first use, along with the `<abbr>` to mark up
the abbreviation. This informs the user what the abbreviation or acronym
means.

The optional [`title`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#title) attribute can provide
an expansion for the abbreviation or acronym when a full expansion is
not present. This provides a hint to user agents on how to
announce/display the content while informing all users what the
abbreviation means. If present, `title` must contain this full
description and nothing else.

Try it
------

Attributes
----------

This element only supports the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md). The
[`title`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#title) attribute has a specific semantic
meaning when used with the `<abbr>` element; it *must* contain a full
human-readable description or expansion of the abbreviation. This text
is often presented by browsers as a tooltip when the mouse cursor is
hovered over the element.

Each `<abbr>` element you use is independent of all others; providing a
`title` for one does not automatically attach the same expansion text to
others with the same content text.

Usage notes
-----------

### Typical use cases

It\'s certainly not required that all abbreviations be marked up using
`<abbr>`. There are, though, a few cases where it\'s helpful to do so:

- When an abbreviation is used and you want to provide an expansion or
    definition outside the flow of the document\'s content, use `<abbr>`
    with an appropriate [`title`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#title).
- To define an abbreviation which may be unfamiliar to the reader,
    present the term using `<abbr>` and inline text providing the
    definition. Include a `title` attribute only when the inline
    expansion or definition is not available.
- When an abbreviation\'s presence in the text needs to be
    semantically noted, the `<abbr>` element is useful. This can be
    used, in turn, for styling or scripting purposes.
- You can use `<abbr>` in concert with [`<dfn>`](dfn) to establish
    definitions for terms which are abbreviations or acronyms. See the
    example [Defining an abbreviation](#defining_an_abbreviation) below.

### Grammar considerations

In languages with [grammatical
number](https://en.wikipedia.org/wiki/Grammatical_number) (that is,
languages where the number of items affects the grammar of a sentence),
use the same grammatical number in your `title` attribute as inside your
`<abbr>` element. This is especially important in languages with more
than two numbers, such as Arabic, but is also relevant in English.

Default styling
---------------

The purpose of this element is purely for the convenience of the author
and all browsers display it inline
([`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)`: inline`)
by default, though its default styling varies from one browser to
another:

Some browsers add a dotted underline to the content of the element.
Others add a dotted underline while converting the contents to small
caps. Others may not style it differently than a [`<span>`](span)
element. To control this styling, use
[`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration)
and
[`font-variant`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant).

Examples
--------

### Marking up an abbreviation semantically

To mark up an abbreviation without providing an expansion or
description, use `<abbr>` without any attributes, as seen in this
example.

#### HTML

[html]

```html
<p>Using <abbr>HTML</abbr> is fun and easy!</p>
```

#### Result

### Styling abbreviations

You can use CSS to set a custom style to be used for abbreviations, as
seen in this simple example.

#### HTML

[html]

```html
<p>Using <abbr>CSS</abbr>, you can style your abbreviations!</p>
```

#### CSS

[css]

```css
abbr {
  font-variant: all-small-caps;
}

```



#### Result 

 



### Providing an expansion 

 
Adding a [`title`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#title) attribute lets you
provide an expansion or definition for the abbreviation or acronym.

#### HTML 

 
[html]

```html
<p>Ashok's joke made me <abbr title="Laugh Out Loud">LOL</abbr> big time.</p>
```

#### Result

### Defining an abbreviation

You can use `<abbr>` in tandem with [`<dfn>`](dfn) to more formally
define an abbreviation, as shown here.

#### HTML

[html]

```html
<p>
  <dfn id="html"><abbr title="HyperText Markup Language">HTML</abbr> </dfn> is a
  markup language used to create the semantics and structure of a web page.
</p>

<p>
  A <dfn id="spec">Specification</dfn> (<abbr>spec</abbr>) is a document that
  outlines in detail how a technology or API is intended to function and how it
  is accessed.
</p>
```

#### Result

### Accessibility concerns

Spelling out the acronym or abbreviation in full the first time it is
used on a page is beneficial for helping people understand it,
especially if the content is technical or industry jargon.

Only include a `title` if expanding the abbreviation or acronym in the
text is not possible. Having a difference between the announced word or
phrase and what is displayed on the screen, especially if it\'s
technical jargon the reader may not be familiar with, can be jarring.

#### HTML

[html]

```html
<p>
  JavaScript Object Notation (<abbr>JSON</abbr>) is a lightweight
  data-interchange format.
</p>
```

#### Result

This is especially helpful for people who are unfamiliar with the
terminology or concepts discussed in the content, people who are new to
the language, and people with cognitive concerns.

Technical summary
-----------------

  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content
  Permitted content                             [Phrasing content](../content_categories#phrasing_content)
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content)
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          Any
  DOM Interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-abbr-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-abbr-element)

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

`abbr`

2

12

1Before Firefox 4, this element implemented the `HTMLSpanElement`
interface instead of the standard `HTMLElement` interface.

7

15

4

4.4

18

4

14

3.2

1.0

See also
--------

- [Using the `<abbr>`
    element](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Advanced_text_formatting#abbreviations)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/abbr>>
