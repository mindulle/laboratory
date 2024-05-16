:link
=====

The `:link` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents an element that has not yet
been visited. It matches every unvisited
[`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) or
[`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area)
element that has an `href` attribute.

Try it
------

Styles defined by the `:link` and [`:visited`](:visited) pseudo-classes
can be overridden by any subsequent user-action pseudo-classes
([`:hover`](:hover) or [`:active`](:active)) that have at least equal
specificity. To style links appropriately, put the `:link` rule before
all other link-related rules, as defined by the *LVHA-order*: `:link`
--- `:visited` --- `:hover` --- `:active`. The `:visited` pseudo-class
and `:link` pseudo-class are mutually exclusive.

**Note:** Use [`:any-link`](:any-link) to select an element independent
of whether it has been visited or not.

Syntax
------

[css]

```css
:link {
  /* ... */
}
```

Examples
--------

By default, most browsers apply a special [`color`](_Resources/Markup%20And%20Styling/css/color.md) value to
visited links. Thus, the links in this example will probably have
special font colors only before you visit them. (After that, you\'ll
need to clear your browser history to see them again.) However, the
[`background-color`](background-color.md) values are likely to remain, as
most browsers do not set that property on visited links by default.

### HTML

[html]

```html
<a href="#ordinary-target">This is an ordinary link.</a><br />
<a href="">You've already visited this link.</a><br />
<a>Placeholder link (won't get styled)</a>
```

### CSS

[css]

```css
a:link {
  background-color: gold;
  color: green;
}
```

### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-link]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-link)

[Selectors Level 4\
  [\# link]](https://drafts.csswg.org/selectors/#link)
  ----------------------------------------------------------------------------------------------------

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

`:link`

1

12

1

3

3.5

1

1.5

18

4

14

3.2

1.0

`not_match_link`

1

12

87

No

3.5

15

1.5

18

87

14

15

1.0

See also
--------

- Link-related pseudo-classes: [`:visited`](:visited),
    [`:hover`](:hover), [`:active`](:active)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:link>
