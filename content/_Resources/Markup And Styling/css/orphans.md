orphans
=======

The `orphans` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets the minimum number of lines in a block container that must
be shown at the *bottom* of a [page](css_paged_media.md), region, or
[column](css_multicol_layout.md).

In typography, an *orphan* is the first line of a paragraph that appears
alone at the bottom of a page. (The paragraph continues on a following
page.)

Syntax
------

[css]

```css
/* <integer> values */
orphans: 2;
orphans: 3;

/* Global values */
orphans: inherit;
orphans: initial;
orphans: revert;
orphans: revert-layer;
orphans: unset;
```

### Values

[`<integer>`](integer.md)

:   The minimum number of lines that can stay by themselves at the
    bottom of a fragment before a fragmentation break. The value must be
    positive.

Formal definition
-----------------

  ---------------------------------- --------------------------
  [Initial value](initial_value.md)     `2`
  Applies to                         block container elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     by computed value type
  ---------------------------------- --------------------------

Formal syntax
-------------

```
orphans = 
  <integer [0,∞]>  
```

Examples
--------

### Setting a minimum orphan size of three lines

#### HTML

[html]

```html
<div>
  <p>This is the first paragraph containing some text.</p>
  <p>
    This is the second paragraph containing some more text than the first one.
    It is used to demonstrate how orphans work.
  </p>
  <p>
    This is the third paragraph. It has a little bit more text than the first
    one.
  </p>
</div>
```

#### CSS

[css]

```css
div {
  background-color: #8cffa0;
  height: 150px;
  columns: 3;
  orphans: 3;
}

p {
  background-color: #8ca0ff;
}

p:first-child {
  margin-top: 0;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Fragmentation Module Level 3\
  [\#
  widows-orphans]](https://drafts.csswg.org/css-break/#widows-orphans)

  ------------------------------------------------------------------------------

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

`orphans`

25

12

No

8

9.2

1.3

4.4

25

No

14

1

1.5

See also
--------

- [`widows`](widows.md)
- [Paged media](css_paged_media.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/orphans>
