Class selectors
===============

The [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) **class
selector** matches elements based on the contents of their
[`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#class)
attribute.

[css]

```css
/* All elements with class="spacious" */
.spacious {
  margin: 2em;
}

/* All <li> elements with class="spacious" */
li.spacious {
  margin: 2em;
}

/* All <li> elements with a class list that includes both "spacious" and "elegant" */
/* For example, class="elegant retro spacious" */
li.spacious.elegant {
  margin: 2em;
}
```

Syntax
------

[css]

```css
.class_name 
```

Note that this is equivalent to the following
[`attribute selector`](attribute_selectors.md):

[css]

```css
[class~=class_name] 
```

Examples
--------

### CSS

[css]

```css
.red {
  color: #f33;
}

.yellow-bg {
  background: #ffa;
}

.fancy {
  font-weight: bold;
  text-shadow: 4px 4px 3px #77f;
}
```

### HTML

[html]

```html
<p class="red">This paragraph has red text.</p>
<p class="red yellow-bg">
  This paragraph has red text and a yellow background.
</p>
<p class="red fancy">This paragraph has red text and "fancy" styling.</p>
<p>This is just a regular paragraph.</p>
```

### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  class-html]](https://drafts.csswg.org/selectors/#class-html)

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

`Class_selectors`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

See also
--------

- [CSS Selectors](css_selectors.md)
- [Learn CSS:
    Selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors>
