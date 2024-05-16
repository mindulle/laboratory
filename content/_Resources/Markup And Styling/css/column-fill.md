column-fill
===========

The `column-fill`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
controls how an element\'s contents are balanced when broken into
columns.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
column-fill: auto;
column-fill: balance;
column-fill: balance-all;

/* Global values */
column-fill: inherit;
column-fill: initial;
column-fill: revert;
column-fill: revert-layer;
column-fill: unset;
```

The `column-fill` property is specified as one of the keyword values
listed below. The initial value is `balance` so the content will be
balanced across the columns.

### Values

[`auto`](#auto)

:   Columns are filled sequentially. Content takes up only the room it
    needs, possibly resulting in some columns remaining empty.

[`balance`](#balance)

:   Content is equally divided between columns. In fragmented contexts,
    such as [paged media](css_paged_media.md), only the last fragment is
    balanced. Therefore in paged media, only the last page would be
    balanced.

[`balance-all`](#balance-all) [Experimental]

:   Content is equally divided between columns. In fragmented contexts,
    such as [paged media](css_paged_media.md), all fragments are balanced.

Formal definition
-----------------

  ---------------------------------- -------------------
  [Initial value](initial_value.md)     `balance`
  Applies to                         multicol elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -------------------

Formal syntax
-------------

```
column-fill = 
  auto         |
  balance      |
  balance-all  
```

Examples
--------

### Balancing column content

#### HTML

[html]

```html
<p class="fill-auto">
  This paragraph fills columns one at a time. Since all of the text can fit in
  the first column, the others are empty.
</p>

<p class="fill-balance">
  This paragraph attempts to balance the amount of content in each column.
</p>
```

#### CSS

[css]

```css
p {
  height: 7em;
  background: #ff9;
  columns: 3;
  column-rule: 1px solid;
}

p.fill-auto {
  column-fill: auto;
}

p.fill-balance {
  column-fill: balance;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Multi-column Layout Module Level 1\
  [\# cf]](https://drafts.csswg.org/css-multicol/#cf)

  -----------------------------------------------------------------------

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

`column-fill`

50

12

5213--74

10

37

98

50

50

5214

37

98

5.0

`balance-all`

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

**Warning:** There are some interoperability issues and bugs with
`column-fill` across browsers, due to unresolved issues in the
specification.

In particular, when using `column-fill: auto` to fill columns
sequentially, Chrome will only consult this property if the multicol
container has a size in the block dimension (e.g., height in a
horizontal writing mode). Firefox will always consult this property,
therefore filling the first column with all of the content in cases
where there is no size.

See also
--------

- [Multiple-column
    Layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout)
- [`column-count`](column-count.md)
- [`column-width`](column-width.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/column-fill>
