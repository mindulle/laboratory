attr()
======

**Note:** The `attr()` function can be used with any CSS property, but
support for properties other than [`content`](content.md) is experimental,
and support for the type-or-unit parameter is sparse.

The `attr()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) is used to retrieve the value of an attribute
of the selected element and use it in the stylesheet. It can also be
used on [pseudo-elements](pseudo-elements.md), in which case the value of
the attribute on the pseudo-element\'s originating element is returned.

Try it
------

Syntax
------

[css]

```css
/* Simple usage */
attr(data-count);
attr(title);

/* With type */
attr(src url);
attr(data-count number);
attr(data-width px);

/* With fallback */
attr(data-count number, 0);
attr(src url, "");
attr(data-width px, inherit);
attr(data-something, "default");
```

### Values

[`attribute-name`](#attribute-name)

:   The name of an attribute on the HTML element referenced in the CSS.

[`<type-or-unit>`](#type-or-unit) [Experimental]

:   A keyword representing either the type of the attribute\'s value, or
    its unit, as in HTML some attributes have implicit units. If the use
    of `<type-or-unit>` as a value for the given attribute is invalid,
    the `attr()` expression will be invalid too. If omitted, it defaults
    to `string`. The list of valid values are:

    [`string`](#string)

    :   The attribute value is treated as a CSS [`<string>`](string). It
        is NOT reparsed, and in particular the characters are used as-is
        instead of CSS escapes being turned into different characters.

        Default value: an empty string.

    [`color`](#color) [Experimental]

    :   The attribute value is parsed as a hash (3- or 6-value hash) or
        a keyword. It must be a valid CSS [`<string>`](string) value.
        Leading and trailing spaces are stripped.

        Default value: `currentcolor`.

    [`url`](#url) [Experimental]

    :   The attribute value is parsed as a string that is used inside a
        CSS `url()` function. Relative URL are resolved relatively to
        the original document, not relatively to the style sheet.
        Leading and trailing spaces are stripped.

        Default value: the URL `about:invalid` that points to a
        non-existent document with a generic error condition.

    [`integer`](#integer) [Experimental]

    :   The attribute value is parsed as a CSS [`<integer>`](integer).
        If it is not valid, that is not an integer or out of the range
        accepted by the CSS property, the default value is used. Leading
        and trailing spaces are stripped.

        Default value: `0`, or, if `0` is not a valid value for the
        property, the property\'s minimum value.

    [`number`](#number) [Experimental]

    :   The attribute value is parsed as a CSS [`<number>`](number). If
        it is not valid, that is not a number or out of the range
        accepted by the CSS property, the default value is used. Leading
        and trailing spaces are stripped.

        Default value: `0`, or, if `0` is not a valid value for the
        property, the property\'s minimum value.

    [`length`](#length) [Experimental]

    :   The attribute value is parsed as a CSS [`<length>`](length)
        dimension, that is including the unit (e.g. `12.5em`). If it is
        not valid, that is not a length or out of the range accepted by
        the CSS property, the default value is used. If the given unit
        is a relative length, `attr()` computes it to an absolute
        length. Leading and trailing spaces are stripped.

        Default value: `0`, or, if `0` is not a valid value for the
        property, the property\'s minimum value.

    [`em`](#em), `ex`, `px`, `rem`, `vw`, `vh`, `vmin`, `vmax`, `mm`, `cm`, `in`, `pt`, or `pc` [Experimental]

    :   The attribute value is parsed as a CSS [`<number>`](number),
        that is without the unit (e.g. `12.5`), and interpreted as a
        [`<length>`](length) with the specified unit. If it is not
        valid, that is not a number or out of the range accepted by the
        CSS property, the default value is used. If the given unit is a
        relative length, `attr()` computes it to an absolute length.
        Leading and trailing spaces are stripped.

        Default value: `0`, or, if `0` is not a valid value for the
        property, the property\'s minimum value.

    [`angle`](#angle) [Experimental]

    :   The attribute value is parsed as a CSS [`<angle>`](angle)
        dimension, that is including the unit (e.g. `30.5deg`). If it is
        not valid, that is not an angle or out of the range accepted by
        the CSS property, the default value is used. Leading and
        trailing spaces are stripped.

        Default value: `0deg`, or, if `0deg` is not a valid value for
        the property, the property\'s minimum value.

    [`deg`](#deg), `grad`, `rad` [Experimental]

    :   The attribute value is parsed as a CSS [`<number>`](number),
        that is without the unit (e.g. `12.5`), and interpreted as an
        [`<angle>`](angle) with the specified unit. If it is not valid,
        that is not a number or out of the range accepted by the CSS
        property, the default value is used. Leading and trailing spaces
        are stripped.

        Default value: `0deg`, or, if `0deg` is not a valid value for
        the property, the property\'s minimum value.

    [`time`](#time) [Experimental]

    :   The attribute value is parsed as a CSS [`<time>`](time)
        dimension, that is including the unit (e.g. `30.5ms`). If it is
        not valid, that is not a time or out of the range accepted by
        the CSS property, the default value is used. Leading and
        trailing spaces are stripped.

        Default value: `0s`, or, if `0s` is not a valid value for the
        property, the property\'s minimum value.

    [`s`](#s), `ms` [Experimental]

    :   The attribute value is parsed as a CSS [`<number>`](number),
        that is without the unit (e.g. `12.5`), and interpreted as an
        [`<time>`](time) with the specified unit. If it is not valid,
        that is not a number or out of the range accepted by the CSS
        property, the default value is used. Leading and trailing spaces
        are stripped.

        Default value: `0s`, or, if `0s` is not a valid value for the
        property, the property\'s minimum value.

    [`frequency`](#frequency) [Experimental]

    :   The attribute value is parsed as a CSS
        [`<frequency>`](frequency) dimension, that is including the unit
        (e.g. `30.5kHz`). If it is not valid, that is not a frequency or
        out of the range accepted by the CSS property, the default value
        is used.

        Default value: `0Hz`, or, if `0Hz` is not a valid value for the
        property, the property\'s minimum value.

    [`Hz`](#hz), `kHz` [Experimental]

    :   The attribute value is parsed as a CSS [`<number>`](number),
        that is without the unit (e.g. `12.5`), and interpreted as a
        [`<frequency>`](frequency) with the specified unit. If it is not
        valid, that is not a number or out of the range accepted by the
        CSS property, the default value is used. Leading and trailing
        spaces are stripped.

        Default value: `0Hz`, or, if `0Hz` is not a valid value for the
        property, the property\'s minimum value.

    [`%`](#sect2) [Experimental]

    :   The attribute value is parsed as a CSS [`<number>`](number),
        that is without the unit (e.g. `12.5`), and interpreted as a
        [`<percentage>`](percentage). If it is not valid, that is not a
        number or out of the range accepted by the CSS property, the
        default value is used. If the given value is used as a length,
        `attr()` computes it to an absolute length. Leading and trailing
        spaces are stripped.

        Default value: `0%`, or, if `0%` is not a valid value for the
        property, the property\'s minimum value.

[`<fallback>`](#fallback) [Experimental]

:   The value to be used if the associated attribute is missing or
    contains an invalid value. If not set, CSS will use the default
    value defined for each `<type-or-unit>`.

### Formal syntax

```
<attr()> = 
  attr( <q-name> <attr-type>? , <declaration-value>? )  

<attr-type> = 
  string            |
  url               |
  ident             |
  color             |
  number            |
  percentage        |
  length            |
  angle             |
  time              |
  frequency         |
  flex              |
  <dimension-unit>  
```

Examples
--------

### content property

In this example, we prepend the value of the `data-foo`
[`data-*`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*)
[global
attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes)
to the contents of the
[`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)
element.

#### HTML

[html]

```html
<p data-foo="hello">world</p>
```

#### CSS

[css]

```css
[data-foo]::before {
  content: attr(data-foo) " ";
}
```

#### Result

### color value

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

In this example, we set the CSS value of
[`background-color`](background-color.md) to the value of the
`data-background`
[`data-*`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*)
[global
attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes)
assigned to the
[`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
element.

#### HTML

[html]

```html
<div class="background" data-background="lime">
  background expected to be red if your browser does not support advanced usage
  of attr()
</div>
```

#### CSS

[css]

```css
.background {
  background-color: red;
}

.background[data-background] {
  background-color: attr(data-background color, red);
}
```

#### Result

### using fallback

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

In this example, we append the value of `data-browser`
[`data-*`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*)
[global
attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes)
to the
[`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)
element. If the `data-browser` attribute is missing from the
[`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)
element, we append the *fallback* value of \"**Unknown**\".

#### HTML

[html]

```html
<p data-browser="Firefox">My favorite browser is:</p>
<p>Your favorite browser is:</p>
```

#### CSS

[css]

```css
p::after {
  content: " " attr(data-browser, "Unknown");
  color: tomato;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------

  [CSS Values and Units Module Level 5\
  [\#
  attr-notation]](https://drafts.csswg.org/css-values-5/#attr-notation)

  -------------------------------------------------------------------------------

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

`attr`

2

12

1

8

9

3.1

≤37

18

4

10.1

2

1.0

`fallback`

No

No

119

No

No

No

No

No

119

No

No

No

`type-or-unit`

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

- [Attribute selectors](attribute_selectors.md)
- [HTML `data-*`
    attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*)
- [SVG `data-*`
    attributes](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/data-*)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/attr>
