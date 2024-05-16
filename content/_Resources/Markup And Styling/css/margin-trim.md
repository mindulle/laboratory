margin-trim
===========

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `margin-trim` property allows the container to trim the margins of
its children where they adjoin the container\'s edges.

Syntax
------

[css]

```css
margin-trim: none;
margin-trim: block;
margin-trim: block-start;
margin-trim: block-end;
margin-trim: inline;
margin-trim: inline-start;
margin-trim: inline-end;

/* Global values */
margin-trim: inherit;
margin-trim: initial;
margin-trim: revert;
margin-trim: revert-layer;
margin-trim: unset;
```

### Values

[`none`](#none)

:   Margins are not trimmed by the container.

[`block`](#block)

:   Margins provided to the block children where they adjoin the
    container\'s edges are trimmed to zero without affecting the margins
    provided to the container.

[`block-start`](#block-start)

:   Margin of the first block child with the container\'s edge is
    trimmed to zero.

[`block-end`](#block-end)

:   Margin of last block child with the container\'s edge is trimmed to
    zero.

[`inline`](#inline)

:   Margins provided to the inline children where they adjoin the
    container\'s edges are trimmed to zero, without affecting the
    spacing at the beginning and end of the row.

[`inline-start`](#inline-start)

:   Margin between the container\'s edge and the first inline child is
    trimmed to zero.

[`inline-end`](#inline-end)

:   Margin between the container\'s edge and the last inline child is
    trimmed to zero.

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         Block containers and multi-column containers. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
margin-trim = 
  none                                                |
  block                                               |
  inline                                              |
  [ block-start || inline-start || block-end || inline-end ]  
```

Examples
--------

### Basic usage

Once support is implemented for this property, it will probably work
like so:

When you\'ve got a container with some inline children and you want to
put a margin between each child but not have it interfere with the
spacing at the end of the row, you might do something like this:

[css]

```css
article {
  background-color: red;
  margin: 20px;
  padding: 20px;
  display: inline-block;
}

article > span {
  background-color: black;
  color: white;
  text-align: center;
  padding: 10px;
  margin-right: 20px;
  margin-left: 30px;
}
```

The problem here is that you\'d end up with 20px too much spacing at the
right of the row, so you\'d maybe do this to fix it:

[css]

```css
span:last-child {
  margin-right: 0;
  margin-left: 0;
}
```

It is a pain having to write another rule to achieve this, and it is
also not very flexible. Instead, `margin-trim` could fix it:

[css]

```css
article {
  margin-trim: inline-end;
  /* … */
}
```

Similarly, to remove left margin with the container\'s edge:

[css]

```css
article {
  margin-trim: inline-start;
  /* … */
}
```

Specifications
--------------

  ------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------

  [CSS Box Model Module Level 4\
  [\#
  margin-trim]](https://drafts.csswg.org/css-box-4/#margin-trim)

  ------------------------------------------------------------------------

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

`margin-trim`

No

No

No

No

No

16.4

No

No

No

No

16.4

No

See also
--------

- [`margin`](margin.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/margin-trim>
