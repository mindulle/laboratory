:visited
========

The `:visited` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) applies once the link has been visited by
the user. For privacy reasons, the styles that can be modified using
this selector are very limited. The `:visited` pseudo-class applies only
[`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) and
[`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area)
elements that have an `href` attribute.

Try it
------

Styles defined by the `:visited` and unvisited [`:link`](:link)
pseudo-classes can be overridden by any subsequent user-action
pseudo-classes ([`:hover`](:hover) or [`:active`](:active)) that have at
least equal specificity. To style links appropriately, put the
`:visited` rule after the `:link` rule but before the `:hover` and
`:active` rules, as defined by the *LVHA-order*: `:link` --- `:visited`
--- `:hover` --- `:active`. The `:visited` pseudo-class and `:link`
pseudo-class are mutually exclusive.

Privacy restrictions
--------------------

For privacy reasons, browsers strictly limit which styles you can apply
using this pseudo-class, and how they can be used:

- Allowable CSS properties are [`color`](_Resources/Markup%20And%20Styling/css/color.md),
    [`background-color`](background-color.md),
    [`border-color`](border-color.md),
    [`border-bottom-color`](border-bottom-color.md),
    [`border-left-color`](border-left-color.md),
    [`border-right-color`](border-right-color.md),
    [`border-top-color`](border-top-color.md),
    [`column-rule-color`](column-rule-color.md),
    [`outline-color`](outline-color.md),
    [`text-decoration-color`](text-decoration-color.md), and
    [`text-emphasis-color`](text-emphasis-color.md).
- Allowable SVG attributes are `fill` and `stroke`.
- The alpha component of the allowed styles will be ignored. The alpha
    component of the element\'s non-`:visited` state will be used
    instead. In Firefox when the alpha component is `0`, the style set
    in `:visited` will be ignored entirely.
- Although these styles can change the appearance of colors to the end
    user, the
    [`window.getComputedStyle`](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle)
    method will lie and always return the value of the non-`:visited`
    color.
- The
    [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link)
    element is never matched by `:visited`.

**Note:** For more information on these limitations and the reasons
behind them, see [Privacy and the :visited
selector](Privacy_and_the_:visited_selector).

Syntax
------

[css]

```css
:visited {
  /* ... */
}
```

Examples
--------

Properties that would otherwise have no color or be transparent cannot
be modified with `:visited`. Of the properties that can be set with this
pseudo-class, your browser probably has a default value for `color` and
`column-rule-color` only. Thus, if you want to modify the other
properties, you\'ll need to give them a base value outside the
`:visited` selector.

### HTML

[html]

```html
<a href="#test-visited-link">Have you visited this link yet?</a><br />
<a href="">You've already visited this link.</a>
```

### CSS

[css]

```css
a {
  /* Specify non-transparent defaults to certain properties,
     allowing them to be styled with the :visited state */
  background-color: white;
  border: 1px solid white;
}

a:visited {
  background-color: yellow;
  border-color: hotpink;
  color: hotpink;
}
```

### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-visited]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-visited)

[Selectors Level 4\
  [\# link]](https://drafts.csswg.org/selectors/#link)
  ----------------------------------------------------------------------------------------------------------

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

`:visited`

1

12

1

4

3.5

1

4.4

18

4

10.1

1

1.0

`not_match_link`

1

12

87

No

15

15

4.4

18

87

14

15

1.0

`privacy_measures`

6

12

4

8

15

5

37

18

4

14

4.2

1.0

See also
--------

- [Privacy and the :visited
    selector](Privacy_and_the_:visited_selector)
- Link-related pseudo-classes: [`:link`](:link), [`:active`](:active),
    [`:hover`](:hover)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:visited>
