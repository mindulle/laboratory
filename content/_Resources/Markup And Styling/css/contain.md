contain
=======

The `contain` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property indicates that an element and its contents are, as much as
possible, independent from the rest of the document tree. Containment
enables isolating a subsection of the DOM, providing performance
benefits by limiting calculations of layout, style, paint, size, or any
combination to a DOM subtree rather than the entire page. Containment
can also be used to scope CSS counters and quotes.

Try it
------

There are four types of CSS containment: size, layout, style, and paint,
which are set on the container. The property is a space-separated list
of a subset of the five standard values or one of the two shorthand
values. Changes to the contained properties within the container are not
propagated outside of the contained element to the rest of the page. The
main benefit of containment is that the browser does not have to
re-render the DOM or page layout as often, leading to small performance
benefits during the rendering of static pages and greater performance
benefits in more dynamic applications.

Using the `contain` property is useful on pages with groups of elements
that are supposed to be independent, as it can prevent element internals
from having side effects outside of its bounding-box.

**Note:** using `layout`, `paint`, `strict` or `content` values for this
property creates:

1. A new [containing block](containing_block.md) (for the descendants
    whose [`position`](position.md) property is `absolute` or `fixed`).
2. A new [](stacking_context.md).
3. A new [block formatting
    context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context).

Syntax
------

[css]

```css
/* Keyword values */
contain: none;
contain: strict;
contain: content;
contain: size;
contain: inline-size;
contain: layout;
contain: style;
contain: paint;

/* Multiple keywords */
contain: size paint;
contain: size layout paint;
contain: inline-size layout;

/* Global values */
contain: inherit;
contain: initial;
contain: revert;
contain: revert-layer;
contain: unset;
```

### Values

The `contain` property can have any of the following values:

- The keyword `none` **or**
- One or more of the space-separated keywords `size` (or
    `inline-size`), `layout`, `style`, and `paint` in any order **or**
- One of the shorthand values `strict` or `content`

The keywords have the following meanings:

[`none`](#none)

:   The element renders as normal, with no containment applied.

[`strict`](#strict)

:   All containment rules are applied to the element. This is equivalent
    to `contain: size layout paint style`.

[`content`](#content)

:   All containment rules except `size` are applied to the element. This
    is equivalent to `contain: layout paint style`.

[`size`](#size)

:   Size containment is applied to the element in both the inline and
    block directions. The size of the element can be computed in
    isolation, ignoring the child elements. This value cannot be
    combined with `inline-size`.

[`inline-size`](#inline-size)

:   Inline size containment is applied to the element. The inline size
    of the element can be computed in isolation, ignoring the child
    elements. This value cannot be combined with `size`.

[`layout`](#layout)

:   The internal layout of the element is isolated from the rest of the
    page. This means nothing outside the element affects its internal
    layout, and vice versa.

[`style`](#style)

:   For properties that can affect more than just an element and its
    descendants, the effects don\'t escape the containing element.
    Counters and quotes are scoped to the element and its contents.

[`paint`](#paint)

:   Descendants of the element don\'t display outside its bounds. If the
    containing box is offscreen, the browser does not need to paint its
    contained elements --- these must also be offscreen as they are
    contained completely by that box. If a descendant overflows the
    containing element\'s bounds, then that descendant will be clipped
    to the containing element\'s border-box.

Formal definition
-----------------

  ---------------------------------- ----------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- ----------------

Formal syntax
-------------

```
contain = 
  none                                  |
  strict                                |
  content                               |
  [ size || layout || style || paint ]  
```

Examples
--------

### Paint containment

The following example shows how to use `contain: paint` to prevent an
element\'s descendants from painting outside of its bounds.

[css]

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  margin: 10px;
  font-size: 20px;
}
```

[html]

```html
<div style="contain: paint">
  <p>This text will be clipped to the bounds of the box.</p>
</div>
<div>
  <p>This text will not be clipped to the bounds of the box.</p>
</div>
```

### Layout containment

Consider the example below which shows how elements behave with and
without layout containment applied:

[html]

```html
<div class="card" style="contain: layout;">
  <h2>Card 1</h2>
  <div class="fixed"><p>Fixed box 1</p></div>
  <div class="float"><p>Float box 1</p></div>
</div>
<div class="card">
  <h2>Card 2</h2>
  <div class="fixed"><p>Fixed box 2</p></div>
  <div class="float"><p>Float box 2</p></div>
</div>
<div class="card">
  <h2>Card 3</h2>
  <!-- ... -->
</div>
```

[css]

```css
.card {
  width: 70%;
  height: 90px;
}

.fixed {
  position: fixed;
  right: 10px;
  top: 10px;
  background: coral;
}

.float {
  float: left;
  margin: 10px;
  background: aquamarine;
}
```

The first card has layout containment applied, and its layout is
isolated from the rest of the page. We can reuse this card in other
places on the page without worrying about layout recalculation of the
other elements. If floats overlap the card bounds, elements on the rest
of the page are not affected. When the browser recalculates the
containing element\'s subtree, only that element is recalculated.
Nothing outside of the contained element needs to be recalculated.
Additionally, the fixed box uses the card as a layout container to
position itself.

The second and third cards have no containment. The layout context for
the fixed box in the second card is the root element so the fixed box is
positioned in the top right corner of the page. A float overlaps the
second card\'s bounds causing the third card to have unexpected layout
shift that\'s visible in the positioning of the `<h2>` element. When
recalculation occurs, it is not limited to a container. This impacts
performance and interferes with the rest of the page layout.

### Style containment

Style containment scopes
[counters](using_css_counters.md) and [quotes](quotes.md)
to the contained element. For CSS counters, the
[`counter-increment`](counter-increment.md) and
[`counter-set`](counter-set.md) properties are scoped to the element as if
the element is at the root of the document.

#### Containment and counters

The example below takes a look at how counters work when style
containment is applied:

[html]

```html
<ul>
  <li>Item A</li>
  <li>Item B</li>
  <li class="container">Item C</li>
  <li>Item D</li>
  <li>Item E</li>
</ul>
```

[css]

```css
body {
  counter-reset: list-items;
}

li::before {
  counter-increment: list-items;
  content: counter(list-items) ": ";
}

.container {
  contain: style;
}
```

Without containment, the counter would increment from 1 to 5 for each
list item. Style containment causes the
[`counter-increment`](counter-increment.md) property to be scoped to the
element\'s subtree and the counter begins again at 1:

#### Containment and quotes

CSS quotes are similarly affected in that the [`content`](content.md)
values relating to quotes are scoped to the element:

[html]

```html
<!-- With style containment -->
<span class="open-quote">
  outer
  <span style="contain: style;">
    <span class="open-quote"> inner </span>
  </span>
</span>
<span class="close-quote"> close </span>
<br />
<!-- Without containment -->
<span class="open-quote">
  outer
  <span>
    <span class="open-quote"> inner </span>
  </span>
</span>
<span class="close-quote"> close </span>
```

[css]

```css
body {
  quotes: "[" "]" "‹" "›";
}
.open-quote:before {
  content: open-quote;
}

.close-quote:after {
  content: close-quote;
}
```

Because of containment, the first closing quote ignores the inner span
and uses the outer span\'s closing quote instead:

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [CSS Containment Module Level 2\
  [\#
  contain-property]](https://drafts.csswg.org/css-contain/#contain-property)

  ------------------------------------------------------------------------------------

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

`contain`

52

79

69

No

39

15.4

52

52

79

41

15.4

6.0

`inline-size`

105

105

101

No

91

15.4

105

105

101

72

15.4

20.0

`style`

52Before Chrome 115, style containment did not affect quotes, see
[Chromium bug 882385](https://crbug.com/882385)).

79Before Edge 115, style containment did not affect quotes, see
[Chromium bug 882385](https://crbug.com/882385)).

103

No

39Before Opera 101, style containment did not affect quotes, see
[Chromium bug 882385](https://crbug.com/882385)).

15.4Style containment does not affect quotes, see [WebKit bug
232083](https://webkit.org/b/232083)).

52Before Chrome 115, style containment did not affect quotes, see
[Chromium bug 882385](https://crbug.com/882385)).

52Before Chrome 115, style containment did not affect quotes, see
[Chromium bug 882385](https://crbug.com/882385)).

103

41Before Opera false, style containment did not affect quotes, see
[Chromium bug 882385](https://crbug.com/882385)).

15.4Style containment does not affect quotes, see [WebKit bug
232083](https://webkit.org/b/232083)).

6.0Before Samsung Internet false, style containment did not affect
quotes, see [Chromium bug 882385](https://crbug.com/882385)).

See also
--------

- [CSS containment](css_containment.md)
- [CSS container queries](css_container_queries.md)
- CSS [`content-visibility`](content-visibility.md) property
- CSS [`position`](position.md) property

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/contain>
