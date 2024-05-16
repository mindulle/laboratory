\<display-inside\>
==================

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

These keywords specify the element\'s inner [`display`](display.md) type,
which defines the type of formatting context that lays out its contents
(assuming it is a non-replaced element). These keywords are used as
values of the `display` property, and can be used for legacy purposes as
a single keyword, or as defined in the Level 3 specification alongside a
value from the [`<display-outside>`](display-outside.md) keywords.

Syntax
------

Valid `<display-inside>` values:

[`flow`](#flow) [Experimental]

:   The element lays out its contents using flow layout
    (block-and-inline layout).

    If its outer display type is `inline` or `run-in`, and it is
    participating in a block or inline formatting context, then it
    generates an inline box. Otherwise it generates a block container
    box.

    Depending on the value of other properties (such as
    [`position`](position), [`float`](float), or [`overflow`](overflow))
    and whether it is itself participating in a block or inline
    formatting context, it either establishes a new [block formatting
    context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)
    (BFC) for its contents or integrates its contents into its parent
    formatting context.

[`flow-root`](#flow-root)

:   The element generates a block element box that establishes a new
    [block formatting
    context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context),
    defining where the formatting root lies.

[`table`](#table)

:   These elements behave like HTML
    [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
    elements. It defines a block-level box.

[`flex`](#flex)

:   The element behaves like a block element and lays out its content
    according to the [flexbox model](css_flexible_box_layout.md).

[`grid`](#grid)

:   The element behaves like a block element and lays out its content
    according to the [](basic_concepts_of_grid_layout.md).

[`ruby`](#ruby) [Experimental]

:   The element behaves like an inline element and lays out its content
    according to the ruby formatting model. It behaves like the
    corresponding HTML
    [`<ruby>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ruby)
    elements.

**Note:** Browsers that support the two value syntax, on finding the
inner value only, such as when `display: flex` or `display: grid` is
specified, will set their outer value to `block`. This will result in
expected behavior; for example if you specify an element to be
`display: grid`, you would expect that the box created on the grid
container would be a block level box.

Formal syntax
-------------

```
<display-inside> = 
  flow       |
  flow-root  |
  table      |
  flex       |
  grid       |
  ruby       
```

Examples
--------

In this example the parent box has been given `display: flow-root` and
so establishes a new BFC and contains the floated item.

### HTML

[html]

```html
<div class="box">
  <div class="float">I am a floated box!</div>
  <p>I am content inside the container.</p>
</div>
```

### CSS

[css]

```css
.box {
  background-color: rgb(224, 206, 247);
  border: 5px solid rebeccapurple;
  display: flow-root;
}

.float {
  float: left;
  width: 200px;
  height: 150px;
  background-color: white;
  border: 1px solid black;
  padding: 10px;
}
```

### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------

  [CSS Display Module Level 3\
  [\#
  typedef-display-inside]](https://drafts.csswg.org/css-display/#typedef-display-inside)

  ------------------------------------------------------------------------------------------------

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

`display-inside`

No

12--79

38

7

No

No

No

No

38

No

No

No

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

`display-inside`

2921

12

20Firefox 28 added multi-line flexbox support.

11IE incorrectly positions inline block content inside flex containers.
See the [discussion on Microsoft
Answers](https://answers.microsoft.com/en-us/ie/forum/ie11-iewindows_10/inline-block-content-in-a-flex-container-not/deea64e2-933b-4bd2-a98c-62be16d04b57).

8IE incorrectly positions inline block content inside flex containers.
See the [discussion on Microsoft
Answers](https://answers.microsoft.com/en-us/ie/forum/ie11-iewindows_10/inline-block-content-in-a-flex-container-not/deea64e2-933b-4bd2-a98c-62be16d04b57).

161512.1--15

97

≤374.4

2925

20Firefox 28 added multi-line flexbox support.

161412.1--14

97

2.01.5

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

`display-inside`

57

1612

52

10Internet Explorer implements an older version of the specification.

44

10.1

57

57

52

43

10.3

6.0Samsung Internet added this earlier than the corresponding Chrome
version would indicate.

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

`display-inside`

1

12

1

8

7

1

≤37

18

4

14

1

1.0

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

`display-inside`

58

79

53

No

45

13

58

58

53

43

13

7.0

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

`display-inside`

115

115

70

No

101

15

115

115

79

No

15

No

### css.properties.display.multi-keyword\_values

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.properties.display.flow-root

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.properties.display.table\_values

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.properties.display.grid

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.properties.display.flex

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.properties.display.ruby\_values

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

See also
--------

- [`display`](display.md)
  - [`<display-outside>`](display-outside.md)
  - [`<display-listitem>`](display-listitem.md)
  - [`<display-internal>`](display-internal.md)
  - [`<display-box>`](display-box.md)
  - [`<display-legacy>`](display-legacy.md)
- [](basic_concepts_of_flexbox.md)
- [](basic_concepts_of_grid_layout.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/display-inside>
