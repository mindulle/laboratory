\@page
======

The `@page` at-rule is a CSS at-rule used to modify different aspects of
printed pages. It targets and modifies the page\'s dimensions,
orientation, and margins. The `@page` at-rule can be used to target all
pages in a print-out or a subset using its various pseudo-classes.

Syntax
------

[css]

```css
/* Targets all the pages */
@page {
  size: 8.5in 9in;
  margin-top: 4in;
}

/* Targets all even-numbered pages */
@page :left {
  margin-top: 4in;
}

/* Targets all odd-numbered pages */
@page :right {
  size: 11in;
  margin-top: 4in;
}

/* Targets all selectors with `page: wide;` set */
@page wide {
  size: a4 landscape;
}

@page {
  /* margin box at top right showing page number */
  @top-right {
    content: "Page " counter(pageNumber);
  }
}
```

### Page properties

The `@page` at-rule can contain only [page
descriptors](#page-descriptors) and [margin at-rules](#margin_at-rules).
The following descriptors have been implemented by at least one browser:

[`margin`](margin.md)

:   Specifies the page margins. Individual margin properties
    [`margin-top`](margin-top.md), [`margin-right`](margin-right.md),
    [`margin-bottom`](margin-bottom.md), and [`margin-left`](margin-left.md)
    can also be used.

[`page-orientation`](page-orientation.md)

:   Specifies the orientation of the page. This does not affect the
    layout of the page; the rotation is applied after the layout in the
    output medium.

[`size`](size.md)

:   Specifies the target size and orientation of the page box\'s
    containing block. In the general case, where one page box is
    rendered onto one page sheet, it also indicates the size of the
    destination page sheet.

The specification mentions following CSS properties to be applicable to
page boxes via \@page at-rule. But these have *not been supported* by
any user agent yet.

Remaining page properties

  Feature                 CSS properties
  ----------------------- -----------------------
  bidi properties         direction
  background properties   background-color
                          background-image
                          background-repeat
                          background-attachment
                          background-position
                          background
  border properties       border-top-width
                          border-right-width
                          border-bottom-width
                          border-left-width
                          border-width
                          border-top-color
                          border-right-color
                          border-bottom-color
                          border-left-color
                          border-color
                          border-top-style
                          border-right-style
                          border-bottom-style
                          border-left-style
                          border-short-style
                          border-top
                          border-right
                          border-bottom
                          border-left
                          border
  counter properties      counter-reset
                          counter-increment
  color                   color
  font properties         font-family
                          font-size
                          font-style
                          font-variant
                          font-weight
                          font
  height properties       height
                          min-height
                          max-height
  line height             line-height
  margin properties       margin-top
                          margin-right
                          margin-bottom
                          margin-left
                          margin
  outline properties      outline-width
                          outline-style
                          outline-color
                          outline
  padding properties      padding-top
                          padding-right
                          padding-bottom
                          padding-left
                          padding
  quotes                  quotes
  text properties         letter-spacing
                          text-align
                          text-decoration
                          text-indent
                          text-transform
                          white-space
                          word-spacing
  visibility              visibility
  width properties        width
                          min-width
                          max-width

Description
-----------

The \@page rule defines properties of the page box. The `@page` at-rule
can be accessed via the CSS object model interface
[`CSSPageRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPageRule).

**Note:** The W3C is discussing how to handle viewport-related
[`<length>`](length.md) units, `vh`, `vw`, `vmin`, and `vmax`. Meanwhile do
not use them within a `@page` at-rule.

### Related properties

The `@page` at-rule, allows the user to assign a name to the rule, which
is then called in a declaration using the `page` property.

[`page`](page.md)

:   Allows a selector to use a user defined **named page**

Formal syntax
-------------

```
@page = 
  @page <page-selector-list>?   

<page-selector-list> = 
  <page-selector>#  

<page-selector> = 
  [ <ident-token>? <pseudo-page>* ]!  

<pseudo-page> = 
  ':' [ left | right | first | blank ]  
```

Where the `<page-body>` includes:

- page-properties
- page-margin properties

and `<pseudo-selector>` represents these pseudo-classes:

- [`:blank`](https://drafts.csswg.org/css-page/#blank-pseudo)
- [`:first`](:first)
- [`:left`](:left)
- [`:right`](:right)

Margin at-rules
---------------

**Warning:** The margin at-rules have not been implemented by any user
agent (updated: August 2023).

The margin at-rules are used inside of the `@page` at-rule. They each
target a different section of the document printed page, styling the
area of the printed page based on the property values set in the style
block:

[css]

```css
@page {
  @top-left {
    /* page-margin-properties */
  }
}
```

`@top-left` targets the top-left of the document and applies the changes
based on the page-margin-properties set.

Other margin-at rules include:

[css]

```css
@top-left-corner
@top-left
@top-center
@top-right
@top-right-corner
@bottom-left-corner
@bottom-left
@bottom-center
@bottom-right
@bottom-right-corner
@left-top
@left-middle
@left-bottom
@right-top
@right-middle
@right-bottom
```

#### Page-margin properties

The page-margin properties are the set of CSS properties can be set in
any individual margin at-rule. They include:

Page-margin properties

  Feature                 CSS properties
  ----------------------- -----------------------
  bidi properties         direction
  background properties   background-color
                          background-image
                          background-repeat
                          background-attachment
                          background-position
                          background
  border properties       border-top-width
                          border-right-width
                          border-bottom-width
                          border-left-width
                          border-width
                          border-top-color
                          border-right-color
                          border-bottom-color
                          border-left-color
                          border-color
                          border-top-style
                          border-right-style
                          border-bottom-style
                          border-left-style
                          border-short-style
                          border-top
                          border-right
                          border-bottom
                          border-left
                          border
  counter properties      counter-reset
                          counter-increment
  content                 content
  color                   color
  font properties         font-family
                          font-size
                          font-style
                          font-variant
                          font-weight
                          font
  height properties       height
                          min-height
                          max-height
  line height             line-height
  margin properties       margin-top
                          margin-right
                          margin-bottom
                          margin-left
                          margin
  outline properties      outline-width
                          outline-style
                          outline-color
                          outline
  padding properties      padding-top
                          padding-right
                          padding-bottom
                          padding-left
                          padding
  quotes                  quotes
  text properties         letter-spacing
                          text-align
                          text-decoration
                          text-indent
                          text-transform
                          white-space
                          word-spacing
  vertical alignment      vertical-align
  visibility              visibility
  width properties        width
                          min-width
                          max-width
  z-index                 z-index

Named pages
-----------

Named pages enable performing per-page layout and adding
[page-breaks](css_fragmentation.md) in a declarative manner when printing.

Named pages can be applied using the [`page`](page.md) property. This
allows the user to create different page configurations for use in print
layouts.

An example of this can be found on the [`page`](page.md#examples) examples.

Examples
--------

### Using the size property to change the page orientation

This example shows how to split the `<section>`s into individual pages
in `landscape` format with each page having a 20% margin when printed.

#### HTML

[html]

```html
<button>Print Webpage</button>
<article>
  <section>
    <h2>Header</h2>
    <p>
      Lorem ipsum dolor, sit amet consectetur adipisicing elit. Consequatur
      facilis vitae voluptatibus odio consequuntur optio placeat? Id, nam sequi
      aut in dolorem dolores, laudantium, quasi totam ipsam aliquam quibusdam
      velit.
    </p>
  </section>
  <section>
    <h2>Header</h2>
    <p>
      Lorem ipsum dolor, sit amet consectetur adipisicing elit. Consequatur
      facilis vitae voluptatibus odio consequuntur optio placeat? Id, nam sequi
      aut in dolorem dolores, laudantium, quasi totam ipsam aliquam quibusdam
      velit.
    </p>
  </section>
  <section>
    <h2>Header</h2>
    <p>
      Lorem ipsum dolor, sit amet consectetur adipisicing elit. Consequatur
      facilis vitae voluptatibus odio consequuntur optio placeat? Id, nam sequi
      aut in dolorem dolores, laudantium, quasi totam ipsam aliquam quibusdam
      velit.
    </p>
  </section>
</article>
```

#### CSS

[css]

```css
@page {
  size: landscape;
  margin: 20%;
}

section {
  page-break-after: always;
  break-after: page;
}

@media print {
  button {
    display: none;
  }
}
```

#### JavaScript

[js]

```js
const button = document.querySelector("button");

button.addEventListener("click", () => {
  window.print();
});
```

#### Result

Clicking the print button will launch a print dialog with the html
sections split into individual pages.

### \@page pseudo-class examples

Please refer to the various [pseudo-classes](pseudo-classes.md) of `@page`
for examples.

- [`:blank`](https://drafts.csswg.org/css-page/#blank-pseudo)
- [`:first`](:first)
- [`:left`](:left)
- [`:right`](:right)

Specifications
--------------

  -------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------

  [CSS Paged Media Module Level 3\
  [\#
  at-page-rule]](https://drafts.csswg.org/css-page/#at-page-rule)

[CSS Logical Properties and Values Level 1\
  [\# page]](https://drafts.csswg.org/css-logical/#page)
  -------------------------------------------------------------------------

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

`@page`

2

12

19

8

6

≤13.1

37

18

19

14

≤13.4

1.0

`page-orientation`

85

85

preview

No

71

No

85

85

No

60

No

14.0

`size`

15

79

95

No

15

≤13.1

37

18

95

14

≤13.4

1.5

See also
--------

- The `@page` [`size`](size.md) descriptor
- The [`page`](page.md) property
- See the [\[META\] CSS Paged Media Module Level
    3](https://bugzilla.mozilla.org/show_bug.cgi?id=286443) ticket in
    Bugzilla for tracking progress on the subject (page-based counters,
    etc.)
- [CSS paged media](css_paged_media.md) module
- [Paged.js: W3C paged media
    polyfill](https://pagedjs.org/documentation/1-the-big-picture)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@page>
