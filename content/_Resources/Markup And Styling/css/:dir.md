:dir()
======

The `:dir()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) matches elements based on the
directionality of the text contained in them.

[css]

```css
/* Selects any element with right-to-left text */
:dir(rtl) {
  background-color: red;
}
```

The `:dir()` pseudo-class uses only the *semantic* value of the
directionality, i.e., the one defined in the document itself. It
doesn\'t account for *styling* directionality, i.e., the directionality
set by CSS properties such as [`direction`](direction.md).

**Note:** Be aware that the behavior of the `:dir()` pseudo-class is not
equivalent to the `[dir=…]` [attribute selectors](attribute_selectors.md).
The latter match the HTML
[`dir`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#dir)
attribute, and ignore elements that lack it --- even if they inherit a
direction from their parent. (Similarly, `[dir=rtl]` and `[dir=ltr]`
won\'t match the `auto` value.) In contrast, `:dir()` will match the
value calculated by the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent),
even if inherited.

**Note:** In HTML, the direction is determined by the
[`dir`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#dir)
attribute. Other document types may have different methods.

Syntax
------

The `:dir()` pseudo-class requires one parameter, representing the text
directionality you want to target.

[css]

```css
:dir([ltr | rtl]) {
  /* ... */
}
```

### Parameters

[`ltr`](#ltr)

:   Target left-to-right elements.

[`rtl`](#rtl)

:   Target right-to-left elements.

Examples
--------

### HTML

[html]

```html
<div dir="rtl">
  <span>test1</span>
  <div dir="ltr">
    test2
    <div dir="auto">עִבְרִית</div>
  </div>
</div>
```

### CSS

[css]

```css
:dir(ltr) {
  background-color: yellow;
}

:dir(rtl) {
  background-color: powderblue;
}
```

### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-ltr]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-ltr)

[Selectors Level 4\
  [\# the-dir-pseudo]](https://drafts.csswg.org/selectors/#the-dir-pseudo)
  --------------------------------------------------------------------------------------------------

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

`:dir`

No

No

4917--53

No

No

16.4

No

No

4917--53

No

16.4

No

See also
--------

- Language-related pseudo-classes: [`:lang`](:lang), [`:dir`](:dir)
- HTML
    [`lang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#lang)
    attribute
- HTML
    [`translate`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#translate)
    attribute

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:dir>
