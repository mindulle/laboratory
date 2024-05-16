text-overflow
=============

The `text-overflow`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
how hidden overflow content is signaled to users. It can be clipped,
display an ellipsis (\'`…`\'), or display a custom string.

Try it
------

The `text-overflow` property doesn\'t force an overflow to occur. To
make text overflow its container, you have to set other CSS properties:
[`overflow`](overflow.md) and [`white-space`](white-space.md). For example:

[css]

```css
overflow: hidden;
white-space: nowrap;
```

The `text-overflow` property only affects content that is overflowing a
block container element in its *inline* progression direction (not text
overflowing at the bottom of a box, for example).

Syntax
------

[css]

```css
text-overflow: clip;
text-overflow: ellipsis ellipsis;
text-overflow: ellipsis " [..]";

/* Global values */
text-overflow: inherit;
text-overflow: initial;
text-overflow: revert;
text-overflow: revert-layer;
text-overflow: unset;
```

The `text-overflow` property may be specified using one or two values.
If one value is given, it specifies overflow behavior for the end of the
line (the right end for left-to-right text, the left end for
right-to-left text). If two values are given, the first specifies
overflow behavior for the left end of the line, and the second specifies
it for the right end of the line. The property accepts either a keyword
value (`clip` or `ellipsis`) or a `<string>` value.

### Values

[`clip`](#clip)

:   The default for this property. This keyword value will truncate the
    text at the limit of the [](introduction_to_the_css_box_model.md), therefore
    the truncation can happen in the middle of a character. To clip at
    the transition between characters you can specify `text-overflow` as
    an empty string, if that is supported in your target browsers:
    `text-overflow: '';`.

[`ellipsis`](#ellipsis)

:   This keyword value will display an ellipsis (`'…'`,
    `U+2026 HORIZONTAL ELLIPSIS`) to represent clipped text. The
    ellipsis is displayed inside the [](introduction_to_the_css_box_model.md), decreasing
    the amount of text displayed. If there is not enough space to
    display the ellipsis, it is clipped.

[`<string>`](#string) [Experimental]

:   The [`<string>`](string.md) to be used to represent clipped text. The
    string is displayed inside the [](introduction_to_the_css_box_model.md), shortening
    the size of the displayed text. If there is not enough space to
    display the string itself, it is clipped.

Formal definition
-----------------

  ---------------------------------- --------------------------
  [Initial value](initial_value.md)     `clip`
  Applies to                         block container elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------------------

Formal syntax
-------------

```
text-overflow = 
  clip      |
  ellipsis  
```

Examples
--------

### One-value syntax

This example shows different values for `text-overflow` applied to a
paragraph, for left-to-right and right-to-left text.

#### HTML

[html]

```html
<div class="ltr">
  <h2>Left to right text</h2>
  <pre>clip</pre>
  <p class="overflow-clip">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit.
  </p>
  <pre>ellipsis</pre>
  <p class="overflow-ellipsis">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit.
  </p>
  <pre>" [..]"</pre>
  <p class="overflow-string">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit.
  </p>
</div>

<div class="rtl">
  <h2>Right to left text</h2>
  <pre>clip</pre>
  <p class="overflow-clip">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit.
  </p>
  <pre>ellipsis</pre>
  <p class="overflow-ellipsis">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit.
  </p>
  <pre>" [..]"</pre>
  <p class="overflow-string">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit.
  </p>
</div>
```

#### CSS

[css]

```css
p {
  width: 200px;
  border: 1px solid;
  padding: 2px 5px;

  /* Both of the following are required for text-overflow */
  white-space: nowrap;
  overflow: hidden;
}

.overflow-clip {
  text-overflow: clip;
}

.overflow-ellipsis {
  text-overflow: ellipsis;
}

.overflow-string {
  text-overflow: " [..]";
}

body {
  display: flex;
  justify-content: space-around;
}

.ltr > p {
  direction: ltr;
}

.rtl > p {
  direction: rtl;
}
```

#### Result

### Two-value syntax

This example shows the two-value syntax for `text-overflow`, where you
can define different overflow behavior for the start and end of the
text. To show the effect we have to scroll the line so the start of the
line is also hidden.

#### HTML

[html]

```html
<pre>clip clip</pre>
<p class="overflow-clip-clip">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit.
</p>
<pre>clip ellipsis</pre>
<p class="overflow-clip-ellipsis">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit.
</p>
<pre>ellipsis ellipsis</pre>
<p class="overflow-ellipsis-ellipsis">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit.
</p>
<pre>ellipsis " [..]"</pre>
<p class="overflow-ellipsis-string">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit.
</p>
```

#### CSS

[css]

```css
p {
  width: 200px;
  border: 1px solid;
  padding: 2px 5px;

  /* Both of the following are required for text-overflow */
  white-space: nowrap;
  overflow: scroll;
}

.overflow-clip-clip {
  text-overflow: clip clip;
}

.overflow-clip-ellipsis {
  text-overflow: clip ellipsis;
}

.overflow-ellipsis-ellipsis {
  text-overflow: ellipsis ellipsis;
}

.overflow-ellipsis-string {
  text-overflow: ellipsis " [..]";
}
```

#### JavaScript

[js]

```js
// Scroll each paragraph so the start is also hidden
const paras = document.querySelectorAll("p");

for (const para of paras) {
  para.scroll(100, 0);
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------

  [CSS Overflow Module Level 3\
  [\#
  text-overflow]](https://drafts.csswg.org/css-overflow/#text-overflow)

  -------------------------------------------------------------------------------

A previous version of this interface reached the *Candidate
Recommendation* status. As some not-listed-at-risk features needed to be
removed, the spec was demoted to the *Working Draft* level, explaining
why browsers implemented this property unprefixed, though not at the CR
state.

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

`text-overflow`

1

12

7Until Firefox 10, handling of `text-overflow` on blocks with inline
overflow on both horizontal sides was incorrect. Before Firefox 10, if
only one value was specified (such as `text-overflow: ellipsis;`), text
was ellipsed on both sides of the block, instead of only the end edge
based on the block\'s text direction.

86

119--15

1.3

≤37

18

7Until Firefox 10, handling of `text-overflow` on blocks with inline
overflow on both horizontal sides was incorrect. Before Firefox 10, if
only one value was specified (such as `text-overflow: ellipsis;`), text
was ellipsed on both sides of the block, instead of only the end edge
based on the block\'s text direction.

1110.1--14

1

1.0

`string`

No

No

9

No

No

No

No

No

9

No

No

No

`two_value_syntax`

No

No

9

No

No

No

No

No

9

No

No

No

See also
--------

- Related CSS properties: [`overflow`](overflow.md),
    [`white-space`](white-space.md)
- CSS properties that control line breaks in words:
    [`overflow-wrap`](overflow-wrap.md), [`word-break`](word-break.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow>
