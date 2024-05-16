text-indent
===========

The `text-indent` CSS property sets the length of empty space
(indentation) that is put before lines of text in a block.

Try it
------

Horizontal spacing is with respect to the left (or right, for
right-to-left layout) edge of the containing block-level element\'s
content box.

Syntax
------

[css]

```css
/* <length> values */
text-indent: 3mm;
text-indent: 40px;

/* <percentage> value
   relative to the containing block width */
text-indent: 15%;

/* Keyword values */
text-indent: 5em each-line;
text-indent: 5em hanging;
text-indent: 5em hanging each-line;

/* Global values */
text-indent: inherit;
text-indent: initial;
text-indent: revert;
text-indent: revert-layer;
text-indent: unset;
```

### Values

[`<length>`](length.md)

:   Indentation is specified as an absolute [`<length>`](length.md).
    Negative values are allowed. See [`<length>`](length.md) values for
    possible units.

[`<percentage>`](percentage.md)

:   Indentation is a [`<percentage>`](percentage.md) of the containing
    block\'s width.

[`each-line`](#each-line)

:   Indentation affects the first line of the block container as well as
    each line after a *forced line break*, but does not affect lines
    after a *soft wrap break*.

[`hanging`](#hanging)

:   Inverts which lines are indented. All lines *except* the first line
    will be indented.

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         block containers
  [Inherited](inheritance.md)           yes
  Percentages                        refer to the width of the containing block
  [Computed value](computed_value.md)   the percentage as specified or the absolute length, plus any keywords as specified
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- -------------------------------------------------------------------------------------

Formal syntax
-------------

```
text-indent = 
  [ <length-percentage> ]  &&
  hanging?                 &&
  each-line?               

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Simple indent

#### HTML

[html]

```html
<p>
  Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy
  nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.
</p>
<p>
  Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy
  nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.
</p>
```

#### CSS

[css]

```css
p {
  text-indent: 5em;
  background: powderblue;
}
```

#### Result

### Skipping indentation on the first paragraph

A common typographic practice when paragraph indentation is present is
to skip the indentation for the first paragraph. As the *The Chicago
Manual of Style* puts it, \"the first line of text following a subhead
may begin flush left or be indented by the usual paragraph indention.\"

Treating first paragraphs differently from subsequent paragraphs can be
done using the [next-sibling combinator](next-sibling_combinator.md), as in
the following example:

#### HTML

[html]

```html
<h2>Lorem ipsum</h2>

<p>
  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse eu
  venenatis quam. Vivamus euismod eleifend metus vitae pharetra. In vel tempor
  metus. Donec dapibus feugiat euismod. Vivamus interdum tellus dolor. Vivamus
  blandit eros et imperdiet auctor. Mauris sapien nunc, condimentum a efficitur
  non, elementum ac sapien. Cras consequat turpis non augue ullamcorper, sit
  amet porttitor dui interdum.
</p>

<p>
  Sed laoreet luctus erat at rutrum. Proin velit metus, luctus in sapien in,
  tincidunt mattis ex. Praesent venenatis orci at sagittis eleifend. Nulla
  facilisi. In feugiat vehicula magna iaculis vehicula. Nulla suscipit tempor
  odio a semper. Donec vitae dapibus ipsum. Donec libero purus, convallis eu
  efficitur id, pulvinar elementum diam. Maecenas mollis blandit placerat. Ut
  gravida pellentesque nunc, in eleifend ante convallis sit amet.
</p>

<h2>Donec ullamcorper elit nisl</h2>

<p>
  Donec ullamcorper elit nisl, sagittis bibendum massa gravida in. Fusce tempor
  in ante gravida iaculis. Integer posuere tempor metus. Vestibulum lacinia,
  nunc et dictum viverra, urna massa aliquam tellus, id mollis sem velit
  vestibulum nulla. Pellentesque habitant morbi tristique senectus et netus et
  malesuada fames ac turpis egestas. Donec vulputate leo ut iaculis ultrices.
  Cras egestas rhoncus lorem. Nunc blandit tempus lectus, rutrum hendrerit orci
  eleifend id. Ut at quam velit.
</p>

<p>
  Aenean rutrum tempor ligula, at luctus ligula auctor vestibulum. Sed
  sollicitudin velit in leo fringilla sollicitudin. Proin eu gravida arcu. Nam
  iaculis malesuada massa, eget aliquet turpis sagittis sed. Sed mollis tellus
  ac dui ullamcorper, nec lobortis diam pellentesque. Quisque dapibus accumsan
  libero, sed euismod ipsum ullamcorper sed.
</p>
```

#### CSS

[css]

```css
p {
  text-align: justify;
  margin: 1em 0 0 0;
}
p + p {
  text-indent: 2em;
  margin: 0;
}
```

#### Result

### Percentage indent

#### HTML

[html]

```html
<p>
  Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy
  nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.
</p>
<p>
  Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy
  nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.
</p>
```

#### CSS

[css]

```css
p {
  text-indent: 30%;
  background: plum;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------

  [CSS Text Module Level 3\
  [\#
  text-indent-property]](https://drafts.csswg.org/css-text/#text-indent-property)

  -----------------------------------------------------------------------------------------

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

`text-indent`

1

12

1

3

3.5

1

≤37

18

4

14

1

1.0

`each-line`

No

No

No

No

No

No

No

No

No

No

No

No

`hanging`

No

No

No

No

No

No

No

No

No

No

No

No

See also
--------

- [Learn to style HTML using
    CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS)
- Related CSS properties:
  - [`text-justify`](text-justify.md)
  - [`text-orientation`](text-orientation.md)
  - [`text-overflow`](text-overflow.md)
  - [`text-rendering`](text-rendering.md)
  - [`text-transform`](text-transform.md)
  - [`hanging-punctuation`](hanging-punctuation.md)
- [CSS Text Decoration](css_text_decoration.md) CSS module
- [CSS Text module](css_text.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent>
