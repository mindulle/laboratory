page
====

The `page` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property is used to specify the named page, a specific type of page
defined by the [`@page`](@page.md) [at-rule](at-rule.md).

If there are multiple selectors that are using a named page
consecutively then a forced page break using
[`break-after`](break-after.md) may be needed.

Syntax
------

[css]

```css
/* set a named page */
page: exampleName;
page: chapterIntro;

/* Use ancestors named page */
page: auto; /* default value */

/* Global values */
page: inherit;
page: initial;
page: revert;
page: revert-layer;
page: unset;
```

### Values

[`auto`](#auto)

:   Default value. Use the value of the nearest ancestor with a
    non-`auto` value. If no ancestor has a named page value set, the
    used value for auto is the empty string.

[`<custom-ident>`](custom-ident.md)

:   Case-sensitive name defined in a [`@page`](@page.md) at-rule.

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         block-level elements in the normal flow of the root element. User agents may also apply it to other elements like `table-row` elements.
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
page = 
  auto            |
  <custom-ident>  
```

Examples
--------

### Named page example

#### HTML

There are two parts to this HTML:

- The print controls
- The content to be printed

The print controls allow the user to select how the `section`s in the
`article` will be printed.

[html]

```html
<!-- print options -->
<fieldset id="printStyle">
  <legend>How would you like to print</legend>
  <label for="single"
    ><input type="radio" id="single" name="type" value="single" checked />No
    Pages</label
  >
  <label for="double"
    ><input type="radio" id="grouped" name="type" value="grouped" />Pages with
    Grouped Chapters</label
  >
  <label for="double"
    ><input type="radio" id="paged" name="type" value="paged" />Chapters
    Paged</label
  >
  <button id="print">Print</button>
</fieldset>
<!-- Content to be printed -->
<article id="print-area" data-print="single">
  <section id="toc">
    <h2>Table of contents</h2>
    <ul>
      <li>Foreword</li>
      <li>Introduction</li>
      <li>Chapter One - named pages</li>
      <li>Chapter Two - page orientation</li>
      <li>Chapter Three - page margins</li>
      <li>Conclusion</li>
    </ul>
  </section>
  <section id="foreword">
    <h2>Foreword</h2>
    <p>
      This book is all about how the CSS <code>@page</code> at-rule can help
      with printing HTML books.
    </p>
  </section>
  <section id="introduction">
    <h2>Introduction</h2>
    <p>
      This book is a concept to show how an <em>HTML</em> document can easily be
      printed out in pages.
    </p>
  </section>
  <section id="chapter1" class="chapter">
    <h2>Named pages</h2>
    <p>Lorem ipsum</p>
  </section>
  <section id="chapter2" class="chapter">
    <h2>Page Orientation</h2>
    <p>Lorem ipsum</p>
  </section>
  <section id="chapter3" class="chapter">
    <h2>Page Margins</h2>
    <p>There are 16 page margins that can be set:</p>
    <ul>
      <li>@top-left-corner</li>
      <li>@top-left</li>
      <li>@top-middle</li>
      <li>@top-right</li>
      <li>@top-right-corner</li>
      <li>@left-top</li>
      <li>@left-middle</li>
      <li>@left-bottom</li>
      <li>@right-top</li>
      <li>@right-middle</li>
      <li>@right-bottom</li>
      <li>@bottom-left-corner</li>
      <li>@bottom-left</li>
      <li>@bottom-middle</li>
      <li>@bottom-right</li>
      <li>@bottom-right-corner</li>
    </ul>
    <p>They can be used to show what appears in these parts of the margin</p>
  </section>
  <section id="conclusion">
    <h2>Conclusion</h2>
    <p>Now go ahead and write books.</p>
  </section>
</article>
```

#### CSS

The first part of the CSS sets up the **named** pages, these include the
size and orientation and also some content to go in the [](@page.md#margin_at-rules) of the printed pages.

[css]

```css
@page toc {
  size: a4 portrait;
  @top-middle {
    content: "Table of contents";
  }
}

@page foreword {
  size: a4 portrait;
  @top-middle {
    content: "Foreword";
  }
}

@page introduction {
  size: a4 portrait;
  @top-middle {
    content: "Introduction";
  }
}

@page conclusion {
  size: a4 portrait;
  @top-middle {
    content: "Conclusion";
  }
}

@page chapter {
  size: a4 landscape;
  @top-middle {
    content: "Chapter";
  }
}
```

The next part of the CSS uses [attribute selectors](attribute_selectors.md)
to apply the print dimensions, orientation, and margins defined in the
named `@page` rules defined in the previous CSS section to elements
using the `page` property.

The sections with `class="chapter"` are concurrent and appear as one
page. The `break-after: page;` is used to split them up, which splits
each chapter into a separately printed page.

[css]

```css
@media print {
  fieldset {
    display: none;
  }
  section {
    font-size: 2rem;
    font-family: Roboto;
  }
  .chapter {
    border: tomato 2px solid;
  }
  [data-print="grouped"] > #toc,
  [data-print="paged"] > #toc {
    page: toc;
    font-family: Courier;
  }
  [data-print="grouped"] > #foreword,
  [data-print="paged"] > #foreword {
    page: foreword;
    font-family: Courier;
  }
  [data-print="grouped"] > #introduction,
  [data-print="paged"] > #introduction {
    page: introduction;
    font-family: Courier;
  }
  [data-print="grouped"] > #conclusion,
  [data-print="paged"] > #conclusion {
    page: conclusion;
    font-family: Courier;
  }
  [data-print="grouped"] > .chapter,
  [data-print="paged"] > .chapter {
    page: chapter;
  }
  [data-print="paged"] > .chapter {
    border: none;
    break-after: page;
  }
  .chapter > ul {
    columns: 2;
  }
}
```

#### JavaScript

The JavaScript updates the value of the `data-print` attribute, which is
the attribute on which the named page is applied, when you select a
different printing option:

[js]

```js
const printArea = document.querySelector("#print-area");
const printButton = document.querySelector("#print");
const printOption = document.querySelector("#printStyle");
printOption.addEventListener("change", (event) => {
  if (event.target.value === "single") {
    printArea.dataset.print = "single";
  } else if (event.target.value === "grouped") {
    printArea.dataset.print = "grouped";
  } else {
    printArea.dataset.print = "paged";
  }
});
printButton.addEventListener("click", () => {
  window.print();
});
```

#### Result

What is printed, and what is shown in the print preview dialog, will
change depending on which print style radio button is selected.

Specifications
--------------

  -----------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------

  [CSS Paged Media Module Level 3\
  [\#
  using-named-pages]](https://drafts.csswg.org/css-page/#using-named-pages)

  -----------------------------------------------------------------------------------

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

`page`

85

85

110

No

71

≤13.1

85

85

110

60

≤13.4

14.0

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/page>
