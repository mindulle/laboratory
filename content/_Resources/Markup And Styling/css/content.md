content
=======

The `content` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property replaces content with a generated value. It can be used to
define what is rendered inside an element or pseudo-element. For
elements, the `content` property specifies whether the element renders
normally (`normal` or `none`) or is replaced with an image (and
associated \"alt\" text). For pseudo-elements and margin boxes,
`content` defines the content as images, text, both, or none, which
determines whether the element renders at all.

Objects inserted using the `content` property are **anonymous [](replaced_element.md)**.

Try it
------

Syntax
------

[css]

```css
/* Keywords that cannot be combined with other values */
content: normal;
content: none;

/* <content-replacement>: <image> values */
content: url("http://www.example.com/test.png");
content: linear-gradient(#e66465, #9198e5);
content: image-set("image1x.png" 1x, "image2x.png" 2x);

/* speech output: alternative text after a "/"  */
content: url("../img/test.png") / "This is the alt text";

/* <string> value */
content: "unparsed text";

/* <counter> values, optionally with <list-style-type> */
content: counter(chapter_counter);
content: counter(chapter_counter, upper-roman);
content: counters(section_counter, ".");
content: counters(section_counter, ".", decimal-leading-zero);

/* attr() value linked to the HTML attribute value */
content: attr(href);

/* <quote> values */
content: open-quote;
content: close-quote;
content: no-open-quote;
content: no-close-quote;

/* <content-list>: a list of content values. 
Several values can be used simultaneously */
content: "prefix" url(http://www.example.com/test.png);
content: "prefix" url("/img/test.png") "suffix" / "Alt text";
content: open-quote counter(chapter_counter);

/* Global values */
content: inherit;
content: initial;
content: revert;
content: revert-layer;
content: unset;
```

### Values

The value can be:

- One of two keywords --- `none` or `normal`
- `<content-replacement>` when replacing a DOM node.
    `<content-replacement>` is always an `<image>`.
- A `<content-list>` when replacing pseudo-elements and margin boxes.
    A content-list is a list of one or more anonymous inline boxes
    appearing in the order specified. Each `<content-list>` item is
    either `contents` or of type [`<string>`](#string),
    [`<image>`](#image), [`<counter>`](#counter), [`<quote>`](#quote),
    [`<target>`](#target), or [`<leader()>`](#leader).
- An optional alternative text value of a `<string>` or `<counter>`,
    preceded by a slash (`/`).

The keywords and data types mentioned above are described in more detail
below:

[`none`](#none)

:   When applied to a pseudo-element, the pseudo-element is not
    generated. When applied to an element, the value has no effect.

[`normal`](#normal)

:   The default value. Computes to `none` for the [`::before`](::before)
    and [`::after`](::after) pseudo-elements. For other pseudo-elements,
    the content will be the initial (or normal) content expected for
    that [`::marker`](::marker), [`::placeholder`](::placeholder), or
    [`::file-selector-button`](::file-selector-button). For regular
    elements or page margin boxes, this computes to `contents`.

[`contents`](#contents) [Experimental]

:   Adds the contents of the element itself to the generated content
    value.

[`<string>`](string.md)

:   A sequence of characters enclosed in matching single or double
    quotes. Multiple string values will be concatenated (there is no
    concatenation operator in CSS).

[`<image>`](_Resources/Markup%20And%20Styling/css/image.md)

:   An [`<image>`](_Resources/Markup%20And%20Styling/css/image.md), representing an image to display. This can be
    equal to a [`url()`](url.md), [`image-set()`](image-set.md), or
    [`<gradient>`](gradient.md) data type, or a part of the webpage itself,
    defined by the [`element()`](element().md) function.

[`<counter>`](#counter)

:   The `<counter>` value is a [](using_css_counters.md), generally a number
    produced by computations defined by
    [`<counter-reset>`](counter-reset.md) and
    [`<counter-increment>`](counter-increment.md) properties. It can be
    displayed using either the [`counter()`](counter.md) or
    [`counters()`](counters.md) function.

    [`counter()`](counter)

    :   The [`counter()`](counter) function has two forms:
        \'counter(*name*)\' or \'counter(*name*, style)\'. The generated
        text is the value of the innermost counter of the given name in
        scope at the given pseudo-element. It is formatted in the
        specified [`<list-style-type>`](list-style-type) (`decimal` by
        default).

    [`counters()`](counters)

    :   The [`counters()`](counters) function also has two forms:
        \'counters(*name*, *string*)\' or \'counters(*name*, *string*,
        *style*)\'. The generated text is the value of all counters with
        the given name in scope at the given pseudo-element, from
        outermost to innermost, separated by the specified string. The
        counters are rendered in the indicated
        [`<list-style-type>`](list-style-type) (`decimal` by default).

[`<quote>`](#quote)

:   The `<quote>` data type includes language- and position-dependent
    keywords:

    [`open-quote`](#open-quote) and `close-quote`

    :   These values are replaced by the appropriate string from the
        [`quotes`](quotes) property.

    [`no-open-quote`](#no-open-quote) and `no-close-quote`

    :   Introduces no content, but increments (decrements) the level of
        nesting for quotes.

[`<target>`](#target) [Experimental]

:   The `<target>` data type includes three target functions,
    `<target-counter()>`, `<target-counters()>`, and `<target-text()>`
    that create cross-references obtained from the target end of a link.
    See [Formal syntax](#formal_syntax).

[`<leader()>`](#leader) [Experimental]

:   The `<leader()>` data type inclues a leader function:
    `leader( <leader-type> )`. This function accepts the keyword values
    `dotted`, `solid`, or `space` (equal to `leader(".")`,
    `leader("_")`, and `leader(" ")`, respectively), or a `<string>` as
    a parameter. When supported and used as a value for `content`, the
    leader-type provided will be inserted as a repeating pattern,
    visually connecting content across a horizontal line.

[`attr(x)`](#attrx)

:   The `attr(x)` CSS function retrieves the value of an attribute of
    the selected element, or the pseudo-element\'s originating element.
    The value of the element\'s attribute `x` is an unparsed string
    representing the attribute name. If there is no attribute `x`, an
    empty string is returned. The case sensitivity of the attribute name
    parameter depends on the document language.

[alternative text:](#alternative_text) `/ <string> | <counter>`

:   Alternative text may be specified for an image or any
    `<content-list>` items, by appending a forward slash and then a
    string of text or a counter. The alternative text is intended for
    speech output by screen-readers, but may also be displayed in some
    browsers. Note that if the browser does not support alternative
    text, the `content` declaration will be considered invalid and will
    be ignored. The [`/ <string>`](string.md) or [`/ <counter>`](counter.md)
    data types specify the \"alt text\" for the element.

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         All elements, tree-abiding pseudo-elements, and page margin boxes
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   On elements, always computes to `normal`. On [`::before`](::before) and [`::after`](::after), if `normal` is specified, computes to `none`. Otherwise, for URI values, the absolute URI; for `attr()` values, the resulting string; for other keywords, as specified.
  Animation type                     discrete
  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
content = 
  normal                                              |
  none                                                |
  [ <content-replacement> | <content-list> ] [ / [ <string> | <counter> ]+ ]?  |
  element( )                                          

<counter> = 
  <counter()>   |
  <counters()>  

<counter()> = 
  counter( <counter-name> , <counter-style>? )  

<counters()> = 
  counters( <counter-name> , <string> , <counter-style>? )  

<counter-style> = 
  <counter-style-name>  |
  <symbols()>           

<symbols()> = 
  symbols( <symbols-type>? [ <string> | <image> ]+ )  

<symbols-type> = 
  cyclic      |
  numeric     |
  alphabetic  |
  symbolic    |
  fixed       

<image> = 
  <url>       |
  <gradient>  

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  
```

Examples
--------

The first five examples create generated content on pseudo-elements. The
last three are [examples of element
replacement](#element-replacement-with-url).

### Appending strings based on an element\'s class

This example inserts generated text after the text of elements that have
a particular class name. The text is colored red.

#### HTML

[html]

```html
<h2>Paperback Best Sellers</h2>
<ol>
  <li>Political Thriller</li>
  <li class="new-entry">Halloween Stories</li>
  <li>My Biography</li>
  <li class="new-entry">Vampire Romance</li>
</ol>
```

#### CSS

[css]

```css
.new-entry::after {
  content: " New!"; /* The leading space creates separation
                       between the DOM node's content and the generated content
                       being added. */
  color: red;
}
```

#### Result

### Quotes

This example inserts differently colored quotation marks around quotes.

#### HTML

[html]

```html
<p>
  According to Sir Tim Berners-Lee,
  <q cite="http://www.w3.org/People/Berners-Lee/FAQ.html#Internet">
    I was lucky enough to invent the Web at the time when the Internet already
    existed - and had for a decade and a half.
  </q>
  We must understand that there is nothing fundamentally wrong with building on
  the contributions of others.
</p>
<p lang="fr-fr">
  Mais c'est Magritte qui a dit,
  <q lang="fr-fr"> Ceci n'est pas une pipe. </q>.
</p>
```

#### CSS

[css]

```css
q {
  color: #00f;
}

q::before,
q::after {
  font-size: larger;
  color: #f00;
  background: #ccc;
}

q::before {
  content: open-quote;
}

q::after {
  content: close-quote;
}
```

#### Result

Note the [type of quotes generated](quotes.md#auto_quotes) is based on the
language. Browsers add open- and close-quotes before and after
[`<q>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q)
elements by default, so the quotes in this example would appear without
them being explicitly set. They could have been turned off by setting
the respective `content` property values to `no-open-quote` and
`no-close-quote`, or by setting them both to `none`. They can also be
turned off by setting the [`quotes`](quotes.md) property to `none` instead.

### Adding text to list item counters

This example combines a counter sandwiched between two `<string>`s
prepended to all list items, creating a more detailed marker for list
items
([`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li))
within unordered lists
([`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol)).

#### HTML

[html]

```html
<ol>
  <li>Dogs</li>
  <li>Cats</li>
  <li>
    Birds
    <ol>
      <li>Owls</li>
      <li>Ducks</li>
      <li>Flightless</li>
    </ol>
  <li>Marsupials</li>
  </li>
</ol>
```

#### CSS

[css]

```css
ol {
  counter-reset: items;
  margin-left: 2em;
}
li {
  counter-increment: items;
}
li::marker {
  content: "item " counters(items, ".", numeric) ": ";
}
```

#### Result

The generated content on each list item\'s marker adds the text \"item
\" as a prefix, including a space to separate the prefix from the
counter, which is followed by \": \", a colon and an additional space.
The [`counters()`](counters.md) function defines a numeric `items` counter,
in which the numbers of nested ordered lists have their numbers
separated with a period (`.`) in most browsers.

### Strings with attribute values

This example is useful for print stylesheets. It uses an [](attribute_selectors.md) to select every fully qualified secure
link, adding the value of the `href` attribute after the link text as
the content of the [`::after`](::after) pseudo-element.

#### HTML

[html]

```html
<ul>
  <li><a href="https://mozilla.com">Mozilla</a></li>
  <li><a href="/">MDN</a></li>
  <li><a href="https://openwebdocs.org">OpenWebDocs</a></li>
</ul>
```

#### CSS

[css]

```css
a[href^="https://"]::after
{
  content: " (URL: " attr(href) ")";
  color: darkgreen;
}
```

#### Result

The generated content is the value of the `href` attribute, prepended by
\"URL: \", with a space, all in parentheses.

### Adding an image with alternative text

This example inserts an image before all links. Two `content` values are
provided. The later `content` value includes an image with alternative
text that a screen reader can output as speech. If a browser does not
support alternative text, this declaration will be considered invalid,
with the previous `content` value displaying. This fallback content list
includes an image and the message \" - alt text is not supported - \".

#### HTML

[html]

```html
<a href="https://www.mozilla.org/en-US/">Mozilla Home Page</a>
```

#### CSS

The CSS to show the image and set the alternative text is shown below.
This also sets the font and color for the content. This will be used on
browsers that *display* the alternative text and in browsers that don\'t
support alternative text and show the the fallback `content` value.

[css]

```css
a::before {
  /* fallback content */
  content: url("https://mozorg.cdn.mozilla.net/media/img/favicon.ico")
    " - alt text is not supported - ";
  /* content with alternative text */
  content: url("https://mozorg.cdn.mozilla.net/media/img/favicon.ico") /
    " MOZILLA: ";
  font:
    x-small Arial,
    sans-serif;
  color: gray;
}
```

#### Result

If using a screen reader, it should speak the word \"MOZILLA\" when it
reaches the image. If supported (if the \"alt text is not supported\" is
not showing), you can select the `::before` pseudo-element with your
developer tools selection tool, and view the [accessible
name](https://developer.mozilla.org/en-US/docs/Glossary/Accessible_name)
in the accessibility panel.

In browsers that don\'t support the alternative text syntax the whole
declaration containing the alt text is invalid. In this case, the
previous `content` value will be used, showing the image and \"alt text
is not supported\" text.

### Element replacement with `url()`

This example replaces a regular element! The element\'s contents are
replaced with an SVG using the [`url()`](url.md) image function.

Pseudo-elements aren\'t rendered on replaced elements. As this element
is replaced, any matching `::after` or `::before` are not generated or
applied. To demonstrate this, we include an `::after` declaration block,
attempting to add the `id` as generated content. This pseudo-element
will not be generated as the element is replaced.

#### HTML

[html]

```html
<div id="replaced">This content is replaced!</div>
```

#### CSS

[css]

```css
#replaced {
  content: url("mdn.svg");
}

/* will not show if element replacement is supported */
div::after {
  content: " (" attr(id) ")";
}
```

#### Result

When generating content on regular elements (rather than just on
pseudo-elements), the entire element is replaced. This means that
`::before` and `::after` pseudo-elements are not generated.

### Element replacement with `<gradient>`

This example demonstrates how an element\'s contents can be replaced by
any type of `<image>`, in this case, a CSS gradient. The element\'s
contents are replaced with a
[`linear-gradient()`](linear-gradient.md). With
[`@supports`](@supports.md), we provide alt text support and a
[`repeating-linear-gradient()`](repeating-linear-gradient.md) for
browsers that support alt text with element content replacement.

#### HTML

[html]

```html
<div id="replaced">I disappear</div>
```

#### CSS

[css]

```css
div {
  border: 1px solid;
  background-color: #ccc;
  min-height: 100px;
  min-width: 100px;
}

#replaced {
  content: linear-gradient(#639f, #c96a);
}

@supports (content: linear-gradient(#000, #fff) / "alt text") {
  #replaced {
    content: repeating-linear-gradient(blue 0, orange 10%) /
      "Gradients and alt text are supported";
  }
}
```

#### Result

Check the [browser compatibility chart](#browser-compatibility). All
browsers support gradients and all browsers support replacing elements
with images, but not all browsers support gradients as a `content` value
and not all browsers support alt text on replacements. If the browser
displays a box with no gradient, replacing elements is supported, but
gradients are not supported as a content replacement value. If the
element is replaced with a striped gradient, the browser supports both.

### Element replacement with `image-set()`

This example replaces an element\'s content with a
[`image-set()`](image-set.md). If the users display has normal
resolution the `1x.png` will be displayed screens with a higher
resolution will display the `2x.png` image.

#### HTML

[html]

```html
<div id="replaced">Mozilla</div>
```

#### CSS

[css]

```css
#replaced {
  content: image-set(
    "1x.png" 1x,
    "2x.png" 2x
  );
}
```

#### Result

Accessibility concerns
----------------------

CSS-generated content is not included in the
[DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction).
Because of this, it will not be represented in the [accessibility
tree](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#accessibility_apis)
and certain assistive technology/browser combinations will not announce
it. If the content conveys information that is critical to understanding
the page\'s purpose, it is better to include it in the main document.

If inserted content is not decorative, check that the information is
provided to assistive technologies and is also available when CSS is
turned off.

- [Accessibility support for CSS generated content --
    Tink](https://tink.uk/accessibility-support-for-css-generated-content/) (2015)
- [WCAG, Guideline 1.3: Create content that can be presented in
    different
    ways](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.3_%E2%80%94_create_content_that_can_be_presented_in_different_ways)
- [Understanding Success Criterion 1.3.1 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)
- [Failure of Success Criterion 1.3.1: inserting non-decorative
    generated
    content](https://www.w3.org/TR/2016/NOTE-WCAG20-TECHS-20161007/F87)
    Techniques for WCAG 2.0

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [CSS Generated Content Module Level 3\
  [\#
  content-property]](https://drafts.csswg.org/css-content/#content-property)

  ------------------------------------------------------------------------------------

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

`content`

1

12

1

8

4

1

4.4

18

4

10.1

1

1.0

`alt_text`

77

79

No

No

64

No

77

77

No

55

No

12.0

`element_replacement`

28

79

63

No

7

9

4.4

28

63

10.1

9

1.5

`gradient`

26

12

113`content: <gradient>`\` doesn\'t paint on ::before/::after pseudo
elements. See [bug 1832901](https://bugzil.la/1832901).

No

15

No

4.4

26

113`content: <gradient>`\` doesn\'t paint on ::before/::after pseudo
elements. See [bug 1832901](https://bugzil.la/1832901).

14

No

1.5

`image-set`

113

113

113`content: image-set(…);`\` doesn\'t paint on ::before/::after pseudo
elements. See [bug 1832901](https://bugzil.la/1832901).

No

99

No

113

113

113`content: image-set(…);`\` doesn\'t paint on ::before/::after pseudo
elements. See [bug 1832901](https://bugzil.la/1832901).

No

No

No

`none_applies_to_elements`

No

No

91

No

No

No

No

No

No

No

No

No

`url`

1

12

1

8

7

1

37

18

4

14

1

1.0

See also
--------

- [CSS generated content](css_generated_content.md) module
- [Replaced elements](replaced_element.md)
- [`::after`](::after)
- [`::before`](::before)
- [`::marker`](::marker)
- [`contain`](contain.md)
- [`quotes`](quotes.md)
- [`<gradient>`](gradient.md)
- [`image-set()`](image-set.md) function
- [`url()`](url.md) function

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/content>
