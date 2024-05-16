overflow-wrap
=============

The `overflow-wrap`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property applies
to inline elements, setting whether the browser should insert line
breaks within an otherwise unbreakable string to prevent text from
overflowing its line box.

Try it
------

**Note:** In contrast to [`word-break`](word-break.md), `overflow-wrap`
will only create a break if an entire word cannot be placed on its own
line without overflowing.

The property was originally a nonstandard and unprefixed Microsoft
extension called `word-wrap`, and was implemented by most browsers with
the same name. It has since been renamed to `overflow-wrap`, with
`word-wrap` being an alias.

Syntax
------

[css]

```css
/* Keyword values */
overflow-wrap: normal;
overflow-wrap: break-word;
overflow-wrap: anywhere;

/* Global values */
overflow-wrap: inherit;
overflow-wrap: initial;
overflow-wrap: revert;
overflow-wrap: revert-layer;
overflow-wrap: unset;
```

The `overflow-wrap` property is specified as a single keyword chosen
from the list of values below.

### Values

[`normal`](#normal)

:   Lines may only break at normal word break points (such as a space
    between two words).

[`anywhere`](#anywhere)

:   To prevent overflow, an otherwise unbreakable string of characters
    --- like a long word or URL --- may be broken at any point if there
    are no otherwise-acceptable break points in the line. No hyphenation
    character is inserted at the break point. Soft wrap opportunities
    introduced by the word break are considered when calculating
    min-content intrinsic sizes.

[`break-word`](#break-word)

:   The same as the `anywhere` value, with normally unbreakable words
    allowed to be broken at arbitrary points if there are no otherwise
    acceptable break points in the line, but soft wrap opportunities
    introduced by the word break are NOT considered when calculating
    min-content intrinsic sizes.

Formal definition
-----------------

  ---------------------------------- ------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         non-replaced inline elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ------------------------------

Formal syntax
-------------

```
overflow-wrap = 
  normal      |
  break-word  |
  anywhere    
```

Examples
--------

### Comparing overflow-wrap, word-break, and hyphens

This example compares the results of `overflow-wrap`, `word-break`, and
`hyphens` when breaking up a long word.

#### HTML

[html]

```html
<p>
  They say the fishing is excellent at Lake
  <em class="normal">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>, though
  I've never been there myself. (<code>normal</code>)
</p>
<p>
  They say the fishing is excellent at Lake
  <em class="ow-anywhere">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
  though I've never been there myself. (<code>overflow-wrap: anywhere</code>)
</p>
<p>
  They say the fishing is excellent at Lake
  <em class="ow-break-word">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
  though I've never been there myself. (<code>overflow-wrap: break-word</code>)
</p>
<p>
  They say the fishing is excellent at Lake
  <em class="word-break">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
  though I've never been there myself. (<code>word-break</code>)
</p>
<p>
  They say the fishing is excellent at Lake
  <em class="hyphens">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>, though
  I've never been there myself. (<code>hyphens</code>, without
  <code>lang</code> attribute)
</p>
<p lang="en">
  They say the fishing is excellent at Lake
  <em class="hyphens">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>, though
  I've never been there myself. (<code>hyphens</code>, English rules)
</p>
<p class="hyphens" lang="de">
  They say the fishing is excellent at Lake
  <em class="hyphens">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>, though
  I've never been there myself. (<code>hyphens</code>, German rules)
</p>
```

#### CSS

[css]

```css
p {
  width: 13em;
  margin: 2px;
  background: gold;
}

.ow-anywhere {
  overflow-wrap: anywhere;
}

.ow-break-word {
  overflow-wrap: break-word;
}

.word-break {
  word-break: break-all;
}

.hyphens {
  hyphens: auto;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------

  [CSS Text Module Level 3\
  [\#
  overflow-wrap-property]](https://drafts.csswg.org/css-text/#overflow-wrap-property)

  ---------------------------------------------------------------------------------------------

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

`overflow-wrap`

231

1812

493.5

5.5

12.110.5

71

4.41

2518

494

12.111

71

1.51.0

`anywhere`

80

80

65

No

67

15.4

80

80

65

57

15.4

13.0

`break-word`

1

12

3.5

5.5

10.5

1

≤37

18

4

11

1

1.0

See also
--------

- [`word-break`](word-break.md)
- [`hyphens`](hyphens.md)
- [`text-overflow`](text-overflow.md)
- [](wrapping_breaking_text.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap>
