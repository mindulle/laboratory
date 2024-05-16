\<bdi\>: The Bidirectional Isolate element
==========================================

The `<bdi>` [HTML](../index) element tells the browser\'s bidirectional
algorithm to treat the text it contains in isolation from its
surrounding text. It\'s particularly useful when a website dynamically
inserts some text and doesn\'t know the directionality of the text being
inserted.

Try it
------

Bidirectional text is text that may contain both sequences of characters
that are arranged left-to-right (LTR) and sequences of characters that
are arranged right-to-left (RTL), such as an Arabic quotation embedded
in an English string. Browsers implement the [Unicode Bidirectional
Algorithm](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics)
to handle this. In this algorithm, characters are given an implicit
directionality: for example, Latin characters are treated as LTR while
Arabic characters are treated as RTL. Some other characters (such as
spaces and some punctuation) are treated as neutral and are assigned
directionality based on that of their surrounding characters.

Usually, the bidirectional algorithm will do the right thing without the
author having to provide any special markup but, occasionally, the
algorithm needs help. That\'s where `<bdi>` comes in.

The `<bdi>` element is used to wrap a span of text and instructs the
bidirectional algorithm to treat this text in isolation from its
surroundings. This works in two ways:

- The directionality of text embedded in `<bdi>` *does not influence*
    the directionality of the surrounding text.
- The directionality of text embedded in `<bdi>` *is not influenced
    by* the directionality of the surrounding text.

For example, consider some text like:

```text
EMBEDDED-TEXT - 1st place
```

If `EMBEDDED-TEXT` is LTR, this works fine. But if `EMBEDDED-TEXT` is
RTL, then `- 1` will be treated as RTL text (because it consists of
neutral and weak characters). The result will be garbled:

```text
1 - EMBEDDED-TEXTst place
```

If you know the directionality of `EMBEDDED-TEXT` in advance, you can
fix this problem by wrapping `EMBEDDED-TEXT` in a [`<span>`](span) with
the [`dir`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#dir) attribute set to the known
directionality. But if you don\'t know the directionality - for example,
because `EMBEDDED-TEXT` is being read from a database or entered by the
user - you should use `<bdi>` to prevent the directionality of
`EMBEDDED-TEXT` from affecting its surroundings.

Though the same visual effect can be achieved using the CSS rule
[`unicode-bidi`](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi)`: isolate`
on a [`<span>`](span) or another text-formatting element, HTML authors
should not use this approach because it is not semantic and browsers are
allowed to ignore CSS styling.

Embedding the characters in `<span dir="auto">` has the same effect as
using `<bdi>`, but its semantics are less clear.

Attributes
----------

Like all other HTML elements, this element supports the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md), except that the
[`dir`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#dir) attribute behaves differently than
normal: it defaults to `auto`, meaning its value is never inherited from
the parent element. This means that unless you specify a value of either
`rtl` or `ltr` for `dir`, the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
will determine the correct directionality to use based on the contents
of the `<bdi>`.

Examples
--------

### No bdi with only LTR

This example lists the winners of a competition using [`<span>`](span)
elements only. When the names only contain LTR text the results look
fine:

[html]

```html
<ul>
  <li><span class="name">Henrietta Boffin</span> - 1st place</li>
  <li><span class="name">Jerry Cruncher</span> - 2nd place</li>
</ul>
```

### No bdi with RTL text

This example lists the winners of a competition using [`<span>`](span)
elements only, and one of the winners has a name consisting of RTL text.
In this case the \"`- 1`\", which consists of characters with neutral or
weak directionality, will adopt the directionality of the RTL text, and
the result will be garbled:

[html]

```html
<ul>
  <li><span class="name">اَلأَعْشَى</span> - 1st place</li>
  <li><span class="name">Jerry Cruncher</span> - 2nd place</li>
</ul>
```

### Using bdi with LTR and RTL text

This example lists the winners of a competition using `<bdi>` elements.
These elements instruct the browser to treat the name in isolation from
its embedding context, so the example output is properly ordered:

[html]

```html
<ul>
  <li><bdi class="name">اَلأَعْشَى</bdi> - 1st place</li>
  <li><bdi class="name">Jerry Cruncher</bdi> - 2nd place</li>
</ul>
```

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            `generic`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-bdi-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-bdi-element)

  -------------------------------------------------------------------------------------------------------------

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

`bdi`

16

79

10

No

15

6

≤37

18

10

14

6

1.0

See also
--------

- [Inline markup and bidirectional text in
    HTML](https://www.w3.org/International/articles/inline-bidi-markup/)
- [Unicode Bidirectional Algorithm
    basics](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics)
- [Localization](https://developer.mozilla.org/en-US/docs/Glossary/Localization)
- Related HTML element: [`<bdo>`](bdo)
- Related CSS properties:
    [`direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/direction),
    [`unicode-bidi`](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/bdi>>
