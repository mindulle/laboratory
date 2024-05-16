Attribute selectors
===================

The CSS **attribute selector** matches elements based on the element
having a given attribute explicitly set, with options for defining an
attribute value or substring value match.

The case sensitivity of attribute names and values depends on the
document language. In HTML, attribute names are case insensitive, as are
spec-defined
[enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
values. The [case-insensitive HTML attribute
values](https://html.spec.whatwg.org/multipage/semantics-other.html#case-sensitivity-of-selectors)
are listed in the HTML spec. For these attributes, the attribute value
in the selector is case-insensitive, regardless of whether the value is
invalid or the attribute for the element on which it is set is invalid.

If the attribute value is case sensitive, like
[`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/class),
[`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/id),
and
[`data-*`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*)
attributes, the attribute selector value match is case-sensitive.
Attributes defined outside of the HTML specification, like
[`role`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles)
and
[`aria-*`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes)
attributes, are also case-sensitive. Normally case-sensitive attribute
selectors can be made case-insensitive with the inclusion of the
case-insensitive modifier (`i`).

[css]

```css
/* <a> elements with a title attribute */
a[title] {
  color: purple;
}

/* <a> elements with an href matching "https://example.org" */
a[href="https://example.org"]
{
  color: green;
}

/* <a> elements with an href containing "example" */
a[href*="example"] {
  font-size: 2em;
}

/* <a> elements with an href ending ".org", case-insensitive */
a[href$=".org" i] {
  font-style: italic;
}

/* <a> elements whose class attribute contains the word "logo" */
a[class~="logo"] {
  padding: 2px;
}
```

Syntax
------

[`[attr]`](#attr)

:   Represents elements with an attribute name of *attr*.

[`[attr=value]`](#attrvalue)

:   Represents elements with an attribute name of *attr* whose value is
    exactly *value*.

[`[attr~=value]`](#attrvalue_2)

:   Represents elements with an attribute name of *attr* whose value is
    a whitespace-separated list of words, one of which is exactly
    *value*.

[`[attr|=value]`](#attrvalue_3)

:   Represents elements with an attribute name of *attr* whose value can
    be exactly *value* or can begin with *value* immediately followed by
    a hyphen, `-` (U+002D). It is often used for language subcode
    matches.

[`[attr^=value]`](#attrvalue_4)

:   Represents elements with an attribute name of *attr* whose value is
    prefixed (preceded) by *value*.

[`[attr$=value]`](#attrvalue_5)

:   Represents elements with an attribute name of *attr* whose value is
    suffixed (followed) by *value*.

[`[attr*=value]`](#attrvalue_6)

:   Represents elements with an attribute name of *attr* whose value
    contains at least one occurrence of *value* within the string.

[`[attr operator value i]`](#attr_operator_value_i)

:   Adding an `i` (or `I`) before the closing bracket causes the value
    to be compared case-insensitively (for characters within the
    [ASCII](https://developer.mozilla.org/en-US/docs/Glossary/ASCII)
    range).

[`[attr operator value s]`](#attr_operator_value_s) [Experimental]

:   Adding an `s` (or `S`) before the closing bracket causes the value
    to be compared case-sensitively (for characters within the ASCII
    range).

Examples
--------

### Links

#### CSS

[css]

```css
a {
  color: blue;
}

/* Internal links, beginning with "#" */
a[href^="#"] {
  background-color: gold;
}

/* Links with "example" anywhere in the URL */
a[href*="example"] {
  background-color: silver;
}

/* Links with "insensitive" anywhere in the URL,
   regardless of capitalization */
a[href*="insensitive" i] {
  color: cyan;
}

/* Links with "cAsE" anywhere in the URL,
with matching capitalization */
a[href*="cAsE" s] {
  color: pink;
}

/* Links that end in ".org" */
a[href$=".org"] {
  color: red;
}

/* Links that start with "https://" and end in ".org" */
a[href^="https://"][href$=".org"]
{
  color: green;
}
```

#### HTML

[html]

```html
<ul>
  <li><a href="#internal">Internal link</a></li>
  <li><a href="http://example.com">Example link</a></li>
  <li><a href="#InSensitive">Insensitive internal link</a></li>
  <li><a href="http://example.org">Example org link</a></li>
  <li><a href="https://example.org">Example https org link</a></li>
</ul>
```

#### Result

### Languages

#### CSS

[css]

```css
/* All divs with a `lang` attribute are bold. */
div[lang] {
  font-weight: bold;
}

/* All divs without a `lang` attribute are italicized. */
div:not([lang]) {
  font-style: italic;
}

/* All divs in US English are blue. */
div[lang~="en-us"] {
  color: blue;
}

/* All divs in Portuguese are green. */
div[lang="pt"] {
  color: green;
}

/* All divs in Chinese are red, whether
   simplified (zh-Hans-CN) or traditional (zh-Hant-TW). */
div[lang|="zh"] {
  color: red;
}

/* All divs with a Traditional Chinese
   `data-lang` are purple. */
/* Note: You could also use hyphenated attributes
   without double quotes */
div[data-lang="zh-Hant-TW"] {
  color: purple;
}
```

#### HTML

[html]

```html
<div lang="en-us en-gb en-au en-nz">Hello World!</div>
<div lang="pt">Olá Mundo!</div>
<div lang="zh-Hans-CN">世界您好！</div>
<div lang="zh-Hant-TW">世界您好！</div>
<div data-lang="zh-Hant-TW">世界您好！</div>
```

#### Result

### HTML ordered lists

The HTML specification requires the
[`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#type)
attribute to be matched case-insensitively because it is primarily used
in the
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
element. Note that if a modifier is not supported by the user agent,
then the selector will not match.

#### CSS

[css]

```css
/* Case-sensitivity depends on document language */
ol[type="a"] {
  list-style-type: lower-alpha;
  background: red;
}

ol[type="b" s] {
  list-style-type: lower-alpha;
  background: lime;
}

ol[type="B" s] {
  list-style-type: upper-alpha;
  background: grey;
}

ol[type="c" i] {
  list-style-type: upper-alpha;
  background: green;
}
```

#### HTML

[html]

```html
<ol type="A">
  <li>
    Red background for case-insensitive matching (default for the type selector)
  </li>
</ol>
<ol type="b">
  <li>Lime background if `s` modifier is supported (case-sensitive match)</li>
</ol>
<ol type="B">
  <li>Grey background if `s` modifier is supported (case-sensitive match)</li>
</ol>
<ol type="C">
  <li>
    Green background if `i` modifier is supported (case-insensitive match)
  </li>
</ol>
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  attribute-selectors]](https://drafts.csswg.org/selectors/#attribute-selectors)

  ----------------------------------------------------------------------------------------

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

`Attribute_selectors`

1

12

1

7

9

3

≤37

18

4

14

1

1.0

`case_insensitive_modifier`

49

79

47

No

36

9

49

49

47

36

9

5.0

`case_sensitive_modifier`

No

No

66

No

No

No

No

No

66

No

No

No

See also
--------

- [`attr()`](attr.md)
- Selecting a single element:
    [`Document.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector),
    [`DocumentFragment.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/querySelector),
    or
    [`Element.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector)
- Selecting all matching elements:
    [`Document.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll),
    [`DocumentFragment.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/querySelectorAll),
    or
    [`Element.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelectorAll)
- [Case-insensitive attribute selector
    values](https://html.spec.whatwg.org/multipage/semantics-other.html#case-sensitivity-of-selectors)
    on WHATWG

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors>
