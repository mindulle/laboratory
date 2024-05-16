itemref
=======

Properties that are not descendants of an element with the
[`itemscope`](itemscope) attribute can be associated with an item using
the [global attribute](_Resources/Markup%20And%20Styling/html/global_attributes/index.md) `itemref`.

`itemref` provides a list of element IDs (not `itemid`s) elsewhere in
the document, with additional properties

The `itemref` attribute can only be specified on elements that have an
`itemscope` attribute specified.

**Note:** The `itemref` attribute is not part of the microdata data
model. It is merely a syntactic construct to aid authors in adding
annotations to pages where the data to be annotated does not follow a
convenient tree structure. For example, it allows authors to mark up
data in a table so that each column defines a separate item while
keeping the properties in the cells.

Examples
--------

### Representing structured data for a band

This example uses microdata attributes to represent the following
structured data (in [JSON-LD](https://json-ld.org/) format):

[json]

```json
{
  "@id": "amanda",
  "name": "Amanda",
  "band": {
    "@id": "b",
    "name": "Jazz Band",
    "size": 12
  }
}
```

#### HTML

[html]

```html
<div itemscope id="amanda" itemref="a b"></div>
<p id="a">Name: <span itemprop="name">Amanda</span></p>
<div id="b" itemprop="band" itemscope itemref="c"></div>
<div id="c">
  <p>Band: <span itemprop="name">Jazz Band</span></p>
  <p>Size: <span itemprop="size">12</span> players</p>
</div>
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  attr-itemref]](https://html.spec.whatwg.org/multipage/microdata.html#attr-itemref)

  --------------------------------------------------------------------------------------------

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

`itemref`

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

- [Other different global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md)
- Other microdata related global attributes:
  - [`itemid`](itemid)
  - [`itemprop`](itemprop)
  - [`itemscope`](itemscope)
  - [`itemtype`](itemtype)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/itemref>>
