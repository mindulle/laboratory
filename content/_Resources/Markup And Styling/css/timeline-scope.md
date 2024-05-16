timeline-scope
==============

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `timeline-scope`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
modifies the scope of a named animation timeline.

By default, a named timeline (i.e. declared using
[`scroll-timeline-name`](scroll-timeline-name.md) or
[`view-timeline-name`](view-timeline-name.md)) can only be set as the
controlling timeline of a direct descendant element (i.e. by setting
[`animation-timeline`](animation-timeline.md) on it with the timeline name
as its value). This is the timeline\'s default \"scope\".

`timeline-scope` is given the name of a timeline defined on a descendant
element; this causes the scope of the timeline to be increased to the
element that `timeline-scope` is set on and any of its descendants. In
other words, that element and any of its descendant elements can now be
controlled using that timeline.

**Note:** If no timeline (or more than one timeline) exists with the
name given for the `timeline-scope` value, an inactive timeline with the
specified name is created.

Syntax
------

[css]

```css
timeline-scope: none;
timeline-scope: custom_name_for_timeline;
```

### Values

Allowed values for `timeline-scope` are:

[`none`](#none)

:   There is no change in timeline scope.

[`<dashed-ident>`](#dashed-ident)

:   Specifies the name of an existing named timeline (i.e. declared
    using [`scroll-timeline-name`](scroll-timeline-name.md) or
    [`view-timeline-name`](view-timeline-name.md)) defined on a descendant
    element. This causes the timeline scope to be increased to the
    element that `timeline-scope` is set on and any of its descendants.

    **Note:** [`<dashed-ident>`](custom-ident) values must start with
    `--`, which helps to avoid name clashes with standard CSS keywords.

Formal definition
-----------------

  ---------------------------------- ------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   `none` or an ordered list of identifiers
  Animation type                     Not animatable
  ---------------------------------- ------------------------------------------

Formal syntax
-------------

Error: could not find syntax for this item

Examples
--------

In this example, a scroll timeline named `--myScroller` is defined using
the `scroll-timeline-name` property on the element with the `scroller`
class (the scrolling element). This is then applied to the animation on
the element with the `box` and `animation` classes (the animated
element) using `animation-timeline: --myScroller`. The key point to note
here is that the animated element is not a descendant of the scrolling
element --- to make this work, we increase the scope of the
`--myScroller` timeline by setting `timeline-scope: --myScroller` on the
[`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body).

#### HTML

The HTML for the example is shown below.

[html]

```html
<div class="content">
  <div class="box animation"></div>
</div>

<div class="scroller">
  <div class="long-element"></div>
</div>
```

#### CSS

The CSS is as follows.

First of all, we set the `<body>`\'s height to `100vh`, and lay its two
child elements out as two equal columns using flexbox. We also set
`timeline-scope: --myScroller` on it so that the `--myScroller` timeline
can be set as the controlling timeline for an animation set on the
`<body>` and any element inside it.

[css]

```css
body {
  margin: 0;
  height: 100vh;
  display: flex;

  /* increases the timeline scope from the .scroller <div> element
  to the whole <body> */
  timeline-scope: --myScroller;
}

.content,
.scroller {
  flex: 1;
}
```

Next, the scrolling element has the `--myScroller` timeline set on it,
`overflow` so that it will scroll, and it is given a background color so
that its boundary is clear to see. The scrolling element\'s child long
element is given a large height so that the scrolling element will
actually scroll.

[css]

```css
.scroller {
  overflow: scroll;
  scroll-timeline-name: --myScroller;
  background: deeppink;
}

.long-element {
  height: 2000px;
}
```

Next, we give the animated element some rudimentary styling, and apply
an animation to it. We also apply the `--myScroller` timeline to it
using `animation-timeline: --myScroller`. To reiterate, this is only
possible because earlier we set `timeline-scope: --myScroller` on the
`<body>` element --- the animated element is **not** a descendant of the
scrolling element.

[css]

```css
.box {
  width: 100px;
  height: 100px;
  border-radius: 10px;
  background-color: rebeccapurple;
  position: fixed;
  top: 20px;
  left: 0%;
}

.animation {
  animation: rotate-appear;
  animation-timeline: --myScroller;
}

@keyframes rotate-appear {
  from {
    rotate: 0deg;
    left: 0%;
  }

  to {
    rotate: 720deg;
    left: 100%;
  }
}
```

#### Result

Scroll the vertical bar on the pink area to see the square animate.

Specifications
--------------

  ------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------

  [Scroll-driven Animations\
  [\#
  propdef-timeline-scope]](https://drafts.csswg.org/scroll-animations/#propdef-timeline-scope)

  ------------------------------------------------------------------------------------------------------

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

`timeline-scope`

116

116

No

No

102

No

116

116

No

No

No

No

See also
--------

- [`animation-timeline`](animation-timeline.md)
- [`scroll-timeline`](scroll-timeline.md),
    [`scroll-timeline-name`](scroll-timeline-name.md)
- [`view-timeline`](view-timeline.md),
    [`view-timeline-name`](view-timeline-name.md)
- [CSS scroll-driven animations](css_scroll-driven_animations.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/timeline-scope>
