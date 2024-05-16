-webkit-line-clamp
==================

The `-webkit-line-clamp` CSS property allows limiting of the contents of
a [block](https://developer.mozilla.org/en-US/docs/Glossary/Block) to
the specified number of lines.

It only works in combination with the [`display`](display.md) property set
to `-webkit-box` or `-webkit-inline-box` and the
[`-webkit-box-orient`](box-orient) property set to `vertical`.

In most cases you will also want to set [`overflow`](overflow.md) to
`hidden`, otherwise the contents won\'t be clipped but an ellipsis will
still be shown after the specified number of lines.

When applied to anchor elements, the truncating can happen in the middle
of the text, not necessarily at the end.

**Note:** This property was originally implemented in WebKit and has
some issues. It got standardized in [CSS Overflow Module Level
4](https://drafts.csswg.org/css-overflow-4/#propdef--webkit-line-clamp)
for legacy support. The [CSS Overflow Module Level
4](https://drafts.csswg.org/css-overflow-4/#propdef-line-clamp)
specification also defines a [`line-clamp`] property,
which is meant to replace this property and avoid its issues.

Syntax
------

[css]

```css
/* Keyword value */
-webkit-line-clamp: none;

/* <integer> values */
-webkit-line-clamp: 3;
-webkit-line-clamp: 10;

/* Global values */
-webkit-line-clamp: inherit;
-webkit-line-clamp: initial;
-webkit-line-clamp: revert;
-webkit-line-clamp: revert-layer;
-webkit-line-clamp: unset;
```

### Values

[`none`](#none)

:   This value specifies that the content won\'t be clamped.

[`<integer>`](integer.md)

:   This value specifies the number of lines after which the content
    will be clamped. It must be greater than 0.

Formal definition
-----------------

  ---------------------------------- ------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     by computed value type
  ---------------------------------- ------------------------

Formal syntax
-------------

```
-webkit-line-clamp = 
  none       |
  <integer>  
```

Examples
--------

### Truncating a paragraph

#### HTML

[html]

```html
<p>
  In this example the <code>-webkit-line-clamp</code> property is set to
  <code>3</code>, which means the text is clamped after three lines. An ellipsis
  will be shown at the point where the text is clamped.
</p>
```

#### CSS

[css]

```css
p {
  width: 300px;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 3;
  overflow: hidden;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------

  [CSS Overflow Module Level 4\
  [\#
  propdef\--webkit-line-clamp]](https://drafts.csswg.org/css-overflow-4/#propdef--webkit-line-clamp)

  ------------------------------------------------------------------------------------------------------------

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

`-webkit-line-clamp`

6

17

68

No

15

5

≤37

18

68

14

4.2

1.0

See also
--------

- [Line Clampin\' (Truncating Multiple Line
    Text)](https://css-tricks.com/line-clampin/)
- [`line-clamp`]

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-line-clamp>
