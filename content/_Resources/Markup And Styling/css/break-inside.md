break-inside
============

The `break-inside`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
how page, column, or region breaks should behave inside a generated box.
If there is no generated box, the property is ignored.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
break-inside: auto;
break-inside: avoid;
break-inside: avoid-page;
break-inside: avoid-column;
break-inside: avoid-region;

/* Global values */
break-inside: inherit;
break-inside: initial;
break-inside: revert;
break-inside: revert-layer;
break-inside: unset;
```

Each possible break point (in other words, each element boundary) is
affected by three properties: the [`break-after`](break-after.md) value of
the previous element, the [`break-before`](break-before.md) value of the
next element, and the `break-inside` value of the containing element.

To determine if a break must be done, the following rules are applied:

1. If any of the three concerned values is a *forced break value*
    (`always`, `left`, `right`, `page`, `column`, or `region`), it has
    precedence. If more than one of them are such a break, the value of
    the element that appears the latest in the flow is used. Thus, the
    `break-before` value has precedence over the `break-after` value,
    which in turn has precedence over the `break-inside` value.
2. If any of the three concerned values is an *avoid break value*
    (`avoid`, `avoid-page`, `avoid-region`, or `avoid-column`), no such
    break will be applied at that point.

Once forced breaks have been applied, soft breaks may be added if
needed, but not on element boundaries that resolve in a corresponding
`avoid` value.

### Values

[`auto`](#auto)

:   Allows, but does not force, any break (page, column, or region) to
    be inserted within the principal box.

[`avoid`](#avoid)

:   Avoids any break (page, column, or region) from being inserted
    within the principal box.

[`avoid-page`](#avoid-page)

:   Avoids any page break within the principal box.

[`avoid-column`](#avoid-column)

:   Avoids any column break within the principal box.

[`avoid-region`](#avoid-region) [Experimental]

:   Avoids any region break within the principal box.

Page break aliases
------------------

For compatibility reasons, the legacy
[`page-break-inside`](page-break-inside.md) property should be treated by
browsers as an alias of `break-inside`. This ensures that sites using
`page-break-inside` continue to work as designed. A subset of values
should be aliased as follows:

  page-break-inside   break-inside
  ------------------- --------------
  `auto`              `auto`
  `avoid`             `avoid`

Formal definition
-----------------

  ---------------------------------- ----------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         block-level elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ----------------------

Formal syntax
-------------

```
break-inside = 
  auto          |
  avoid         |
  avoid-page    |
  avoid-column  |
  avoid-region  
```

Examples
--------

### Avoiding breaking inside a figure

In the following example we have a container that contains an `<h1>`
spanning all columns (achieved using `column-span: all`) and a series of
paragraphs laid out in multiple columns using `column-width: 200px`. We
also have a `<figure>` containing an image and a caption.

By default, it is possible for you to get a break between the image and
its caption, which is not what we want. To avoid this, we have set
`break-inside: avoid` on the `<figure>`, which causes them to always
stay together.

#### HTML

[html]

```html
<article>
  <h1>Main heading</h1>

  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla vitae
    fringilla mauris. Quisque commodo eget nisi sed pretium. Mauris luctus nec
    lacus in ultricies. Mauris vitae hendrerit arcu, ac scelerisque lacus.
    Aliquam lobortis in lacus sit amet posuere. Fusce iaculis urna id neque
    dapibus, eu lacinia lectus dictum.
  </p>

  <figure>
    <img
      src="https://mdn.dev/archives/media/attachments/2020/07/29/17350/3b4892b7e820122ac6dd7678891d4507/firefox.png" />
    <figcaption>The Firefox logo — fox wrapped around the world</figcaption>
  </figure>

  <p>
    Praesent condimentum dui dui, sit amet rutrum diam tincidunt eu. Cras
    suscipit porta leo sit amet rutrum. Sed vehicula ornare tincidunt. Curabitur
    a ipsum ac diam mattis volutpat ac ut elit. Nullam luctus justo non
    vestibulum gravida. Morbi metus libero, pharetra non porttitor a, molestie
    nec nisi.
  </p>

  <p>
    In finibus viverra enim vel suscipit. Quisque consequat velit eu orci
    malesuada, ut interdum tortor molestie. Proin sed pellentesque augue. Nam
    risus justo, faucibus non porta a, congue vel massa. Cras luctus lacus nisl,
    sed tincidunt velit pharetra ac. Duis suscipit faucibus dui sed ultricies.
  </p>
</article>
```

#### CSS

[css]

```css
html {
  font-family: helvetica, arial, sans-serif;
}

body {
  width: 80%;
  margin: 0 auto;
}

h1 {
  font-size: 3rem;
  letter-spacing: 2px;
  column-span: all;
}

h1 + p {
  margin-top: 0;
}

p {
  line-height: 1.5;
  break-after: column;
}

figure {
  break-inside: avoid;
}

img {
  max-width: 70%;
  display: block;
  margin: 0 auto;
}

figcaption {
  font-style: italic;
  font-size: 0.8rem;
  width: 70%;
}

article {
  column-width: 200px;
  gap: 20px;
}
```

### Result

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------------------------

  [CSS Fragmentation Module Level 3\
  [\# break-within]](https://drafts.csswg.org/css-break/#break-within)

  [CSS Regions Module Level 1\
  [\# region-flow-break]](https://drafts.csswg.org/css-regions/#region-flow-break)

[CSS Multi-column Layout Module Level 1\
  [\#
  break-before-break-after-break-inside]](https://drafts.csswg.org/css-multicol/#break-before-break-after-break-inside)
  -------------------------------------------------------------------------------------------------------------------------------

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

`break-inside`

50

12

65

10

3711.1--12.1

10

50

50

65

3711.1--12.1

10

5.0

`multicol_context`

50

12

65

10

3711.1--12.1

10

50

50

65

3711.1--12.1

10

5.0

`paged_context`

50

12

65

10

3711.1--12.1

10

50

50

65

3711.1--12.1

10

5.0

See also
--------

- [Multiple-column
    Layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout)
- [Breaking Boxes With CSS
    Fragmentation](https://www.smashingmagazine.com/2019/02/css-fragmentation/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/break-inside>
