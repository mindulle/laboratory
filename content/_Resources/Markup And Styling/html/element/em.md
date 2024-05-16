\<em\>: The Emphasis element
============================

The `<em>` [HTML](../index) element marks text that has stress emphasis.
The `<em>` element can be nested, with each level of nesting indicating
a greater degree of emphasis.

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

The `<em>` element is for words that have a stressed emphasis compared
to surrounding text, which is often limited to a word or words of a
sentence and affects the meaning of the sentence itself.

Typically this element is displayed in italic type. However, it should
not be used to apply italic styling; use the CSS
[`font-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style)
property for that purpose. Use the [`<cite>`](cite) element to mark the
title of a work (book, play, song, etc.). Use the [`<i>`](i) element to
mark text that is in an alternate tone or mood, which covers many common
situations for italics such as scientific names or words in other
languages. Use the [`<strong>`](strong) element to mark text that has
greater importance than surrounding text.

### \<i\> vs. \<em\>

Some developers may be confused by how multiple elements seemingly
produce similar visual results. `<em>` and `<i>` are a common example,
since they both italicize text. What\'s the difference? Which should you
use?

By default, the visual result is the same. However, the semantic meaning
is different. The `<em>` element represents stress emphasis of its
contents, while the `<i>` element represents text that is set off from
the normal prose, such as a foreign word, fictional character thoughts,
or when the text refers to the definition of a word instead of
representing its semantic meaning. (The title of a work, such as the
name of a book or movie, should use `<cite>`.)

This means the right one to use depends on the situation. Neither is for
purely decorative purposes, that\'s what CSS styling is for.

An example for `<em>` could be: \"Just *do* it already!\", or: \"We
*had* to do something about it\". A person or software reading the text
would pronounce the words in italics with an emphasis, using verbal
stress.

An example for `<i>` could be: \"The *Queen Mary* sailed last night\".
Here, there is no added emphasis or importance on the word \"Queen
Mary\". It is merely indicated that the object in question is not a
queen named Mary, but a ship named *Queen Mary*. Another example for
`<i>` could be: \"The word *the* is an article\".

Examples
--------

In this example, the `<em>` element is used to highlight an implicit or
explicit contrast between two ingredient lists:

[html]

```html
<p>
  Ice cream is made with milk, sweetener, and cream. Frozen custard, on the
  other hand, is made of milk, cream, sweetener, and <em>egg yolks</em>.
</p>
```

### Result

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            `emphasis`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) Up to Gecko 1.9.2 (Firefox 4) inclusive, Firefox implements the [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement) interface for this element.
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -----------------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-em-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-em-element)

  -----------------------------------------------------------------------------------------------------------

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

`em`

1

12

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

See also
--------

- [`<i>`](i)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/em>>
