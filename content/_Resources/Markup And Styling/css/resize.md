resize
======

The `resize` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets whether an element is resizable, and if so, in which
directions.

Try it
------

`resize` does not apply to the following:

- Inline elements
- Block elements for which the [`overflow`](overflow.md) property is set
    to `visible`

Syntax
------

[css]

```css
/* Keyword values */
resize: none;
resize: both;
resize: horizontal;
resize: vertical;
resize: block;
resize: inline;

/* Global values */
resize: inherit;
resize: initial;
resize: revert;
resize: revert-layer;
resize: unset;
```

The `resize` property is specified as a single keyword value from the
list below.

### Values

[`none`](#none)

:   The element offers no user-controllable method for resizing it.

[`both`](#both)

:   The element displays a mechanism for allowing the user to resize it,
    which may be resized both horizontally and vertically.

[`horizontal`](#horizontal)

:   The element displays a mechanism for allowing the user to resize it
    in the *horizontal* direction.

[`vertical`](#vertical)

:   The element displays a mechanism for allowing the user to resize it
    in the *vertical* direction.

[`block`](#block) [Experimental]

:   The element displays a mechanism for allowing the user to resize it
    in the *block* direction (either horizontally or vertically,
    depending on the [`writing-mode`](writing-mode.md) and
    [`direction`](direction.md) value).

[`inline`](#inline) [Experimental]

:   The element displays a mechanism for allowing the user to resize it
    in the *inline* direction (either horizontally or vertically,
    depending on the [`writing-mode`](writing-mode.md) and
    [`direction`](direction.md) value).

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         elements with [`overflow`](overflow.md) other than `visible`, and optionally replaced elements representing images or videos, and iframes
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
resize = 
  none        |
  both        |
  horizontal  |
  vertical    |
  block       |
  inline      
```

Examples
--------

### Disabling resizability of textareas

In many browsers,
[`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)
elements are resizable by default. You may override this behavior with
the `resize` property.

#### HTML

[html]

```html
<textarea>Type some text here.</textarea>
```

#### CSS

[css]

```css
textarea {
  resize: none; /* Disables resizability */
}
```

#### Result

### Using resize with arbitrary elements

You can use the `resize` property to make any element resizable. In the
example below, a resizable
[`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
contains a resizable paragraph
([`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)
element).

#### HTML

[html]

```html
<div class="resizable">
  <p class="resizable">
    This paragraph is resizable in all directions, because the CSS `resize`
    property is set to `both` on this element.
  </p>
</div>
```

#### CSS

[css]

```css
.resizable {
  resize: both;
  overflow: scroll;
  border: 1px solid black;
}

div {
  height: 300px;
  width: 300px;
}

p {
  height: 200px;
  width: 200px;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Basic User Interface Module Level 4\
  [\# resize]](https://drafts.csswg.org/css-ui/#resize)

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

`resize`

1

79

4

No

12.1

3

37

18

4

14

1

1.0

`block_level_support`

4

79

5`resize` doesn\'t have any effect on
[`<iframe>`](https://developer.mozilla.org/docs/Web/HTML/Element/iframe).
See [bug 680823](https://bugzil.la/680823))

No

15

4

37

18

5`resize` doesn\'t have any effect on
[`<iframe>`](https://developer.mozilla.org/docs/Web/HTML/Element/iframe).
See [bug 680823](https://bugzil.la/680823))

14

3.2

1.0

`flow_relative_support`

118

118

63

No

104

16

118

118

63

No

16

No

See also
--------

- [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/resize>
