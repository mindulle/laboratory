:nth-of-type()
==============

The `:nth-of-type()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) matches elements based on their position
among siblings of the same type (tag name).

Try it
------

Syntax
------

The `nth-of-type` pseudo-class is specified with a single argument,
which represents the pattern for matching elements.

See [`:nth-child`](:nth-child) for a more detailed explanation of its
syntax.

[css]

```css
:nth-of-type(<an-plus-b> | even | odd) {
  /* ... */
}
```

Examples
--------

### Basic example

#### HTML

[html]

```html
<div>
  <div>This element isn't counted.</div>
  <p>1st paragraph.</p>
  <p class="fancy">2nd paragraph.</p>
  <div>This element isn't counted.</div>
  <p class="fancy">3rd paragraph.</p>
  <p>4th paragraph.</p>
</div>
```

#### CSS

[css]

```css
/* Odd paragraphs */
p:nth-of-type(2n + 1) {
  color: red;
}

/* Even paragraphs */
p:nth-of-type(2n) {
  color: blue;
}

/* First paragraph */
p:nth-of-type(1) {
  font-weight: bold;
}

/* This will match the 3rd paragraph as it will match elements which are 2n+1 AND have a class of fancy.
The second paragraph has a class of fancy but is not matched as it is not :nth-of-type(2n+1) */
p.fancy:nth-of-type(2n + 1) {
  text-decoration: underline;
}
```

#### Result

**Note:** There is no way to select the nth-of-class using this
selector. The selector looks at the type only when creating the list of
matches. You can however apply CSS to an element based on `:nth-of-type`
location **and** a class, as shown in the example above.

Specifications
--------------

  --------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  nth-of-type-pseudo]](https://drafts.csswg.org/selectors/#nth-of-type-pseudo)

  --------------------------------------------------------------------------------------

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

`:nth-of-type`

1

12Before Edge 16, Microsoft Edge treats all unknown elements (such as
custom elements) as the same element type.

3.5

9Internet Explorer treats all unknown elements (such as custom elements)
as the same element type.

9.5

3.1

2

18

4

10.1

2

1.0

See also
--------

- [`:nth-child`](:nth-child), [`:nth-last-of-type`](:nth-last-of-type)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-of-type>
