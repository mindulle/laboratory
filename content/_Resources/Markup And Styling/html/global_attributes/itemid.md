itemid
======

The `itemid` [global attribute](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) provides microdata
in the form of a unique, global identifier of an item.

An `itemid` attribute can only be specified for an element that has both
[`itemscope`](itemscope) and [`itemtype`](itemtype) attributes. Also,
`itemid` can only be specified on elements that possess an `itemscope`
attribute whose corresponding `itemtype` refers to or defines a
vocabulary that supports global identifiers.

The exact meaning of an `itemtype`\'s global identifier is provided by
the definition of that identifier within the specified vocabulary. The
vocabulary defines whether several items with the same global identifier
can coexist and, if so, how items with the same identifier are handled.

**Note:** The
[WHATWG](https://developer.mozilla.org/en-US/docs/Glossary/WHATWG)
definition specifies that an `itemid` must be a
[URL](https://developer.mozilla.org/en-US/docs/Glossary/URL). However,
the following example correctly illustrates that a
[URN](https://developer.mozilla.org/en-US/docs/Glossary/URN) may also be
used. This inconsistency may reflect the incomplete nature of the
Microdata specification.

Examples
--------

### Representing structured data for a book

This example uses microdata attributes to represent the following
structured data:

itemscope

itemtype: itemid

https://schema.org/Book>>: urn:isbn:0-374-22848-5

itemprop

title

Owls of the Eastern Ice

itemprop

author

Jonathan C Slaght

itemprop

datePublished

2020-08-04

#### HTML

[html]

```html
<dl
  itemscope
  itemtype="https://schema.org/Book"
  itemid="urn:isbn:0-374-22848-5<">
  <dt>Title</dt>
  <dd itemprop="title">Owls of the Eastern Ice</dd>
  <dt>Author</dt>
  <dd itemprop="author">Jonathan C Slaght</dd>
  <dt>Publication date</dt>
  <dd>
    <time itemprop="datePublished" datetime="2020-08-04">August 4 2020</time>
  </dd>
</dl>
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  attr-itemid]](https://html.spec.whatwg.org/multipage/microdata.html#attr-itemid)

  ------------------------------------------------------------------------------------------

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

`itemid`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

- All [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).
- Other microdata related global attributes:
  - [`itemprop`](itemprop)
  - [`itemref`](itemref)
  - [`itemscope`](itemscope)
  - [`itemtype`](itemtype)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/itemid>>
