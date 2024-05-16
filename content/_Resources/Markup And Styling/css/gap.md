gap
===

The `gap` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[shorthand property](shorthand_properties.md) sets the gaps
([gutters](https://developer.mozilla.org/en-US/docs/Glossary/Gutters))
between rows and columns.

Early versions of the specification called this property `grid-gap`, and
to maintain compatibility with legacy websites, browsers will still
accept `grid-gap` as an alias for `gap`.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`column-gap`](column-gap.md)
- [`row-gap`](row-gap.md)

Syntax
------

[css]

```css
/* One <length> value */
gap: 20px;
gap: 1em;
gap: 3vmin;
gap: 0.5cm;

/* One <percentage> value */
gap: 16%;
gap: 100%;

/* Two <length> values */
gap: 20px 10px;
gap: 1em 0.5em;
gap: 3vmin 2vmax;
gap: 0.5cm 2mm;

/* One or two <percentage> values */
gap: 16% 100%;
gap: 21px 82%;

/* calc() values */
gap: calc(10% + 20px);
gap: calc(20px + 10%) calc(10% - 5px);

/* Global values */
gap: inherit;
gap: initial;
gap: revert;
gap: revert-layer;
gap: unset;
```

This property is specified as a value for `<'row-gap'>` followed
optionally by a value for `<'column-gap'>`. If `<'column-gap'>` is
omitted, it\'s set to the same value as `<'row-gap'>`.

`<'row-gap'>` and `<'column-gap'>` are each specified as a `<length>` or
a `<percentage>`.

### Values

[`<length>`](length.md)

:   Is the width of the gutter separating the grid lines.

[`<percentage>`](percentage.md)

:   Is the width of the gutter separating the grid lines, relative to
    the dimension of the element.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [`row-gap`](row-gap.md):         |
|                                   |     `normal`                      |
|                                   | -   [`column-gap`](column-gap.md):   |
|                                   |     `normal`                      |
+-----------------------------------+-----------------------------------+
| Applies to                        | multi-column elements, flex       |
|                                   | containers, grid containers       |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [`row-gap`](row-gap.md): as      |
|                                   |     specified, with \<length\>s   |
|                                   |     made absolute, and normal     |
|                                   |     computing to zero except on   |
|                                   |     multi-column elements         |
|                                   | -   [`column-gap`](column-gap.md):   |
|                                   |     as specified, with            |
|                                   |     \<length\>s made absolute,    |
|                                   |     and normal computing to zero  |
|                                   |     except on multi-column        |
|                                   |     elements                      |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [`row-gap`](row-gap.md): a       |
|                                   |                                   |
|                                   |   [length](length.md#interpolation), |
|                                   |     [](percentage.md#interpolation) |
|                                   |     or calc();                    |
|                                   | -   [`column-gap`](column-gap.md): a |
|                                   |                                   |
|                                   |   [length](length.md#interpolation), |
|                                   |     [](percentage.md#interpolation) |
|                                   |     or calc();                    |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
gap = 
  <'row-gap'> <'column-gap'>?  
```

Examples
--------

### Flex layout

#### HTML

[html]

```html
<div id="flexbox">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>
```

#### CSS

[css]

```css
#flexbox {
  display: flex;
  flex-wrap: wrap;
  width: 300px;
  gap: 20px 5px;
}

#flexbox > div {
  border: 1px solid green;
  background-color: lime;
  flex: 1 1 auto;
  width: 100px;
  height: 50px;
}
```

#### Result

### Grid layout

#### HTML

[html]

```html
<div id="grid">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>
```

#### CSS

[css]

```css
#grid {
  display: grid;
  height: 200px;
  grid-template: repeat(3, 1fr) / repeat(3, 1fr);
  gap: 20px 5px;
}

#grid > div {
  border: 1px solid green;
  background-color: lime;
}
```

#### Result

### Multi-column layout

#### HTML

[html]

```html
<p class="content-box">
  This is some multi-column text with a 40px column gap created with the CSS
  <code>gap</code> property. Don't you think that's fun and exciting? I sure do!
</p>
```

#### CSS

[css]

```css
.content-box {
  column-count: 3;
  gap: 40px;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------

  [CSS Box Alignment Module Level 3\
  [\#
  gap-shorthand]](https://drafts.csswg.org/css-align/#gap-shorthand)

  ----------------------------------------------------------------------------

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

`gap`

57

16

52

No

44

10.1

57

57

52

43

10.3

7.0

`flex_context`

84

84

63

No

70

14.1

84

84

63

60

14.5

14.0

`grid_context`

6657

1616

6152

No

5344

1210.1

6657

6657

6152

4743

1210.3

9.07.0

`multicol_context`

66

16

61

No

53

14.1

66

66

61

47

14.5

9.0

See also
--------

- Related CSS properties: [`row-gap`](row-gap.md),
    [`column-gap`](column-gap.md)
- Grid Layout Guide: *[](basic_concepts_of_grid_layout.md#gutters)*

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/gap>
