:fullscreen
===========

The `:fullscreen`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) matches every element which is currently
in fullscreen mode. If multiple elements have been put into fullscreen
mode, this selects them all.

Syntax
------

[css]

```css
:fullscreen {
  /* ... */
}
```

Usage notes
-----------

The `:fullscreen` pseudo-class lets you configure your stylesheets to
automatically adjust the size, style, or layout of content when elements
switch back and forth between fullscreen and traditional presentations.

Examples
--------

In this example, the color of a button is changed depending on whether
or not the document is in fullscreen mode. This is done without needing
to specifically apply style changes using JavaScript.

### HTML

The page\'s HTML looks like this:

[html]

```html
<h1>MDN Web Docs Demo: :fullscreen pseudo-class</h1>

<p>
  This demo uses the <code>:fullscreen</code> pseudo-class to automatically
  change the style of a button used to toggle fullscreen mode on and off,
  entirely using CSS.
</p>

<button id="fs-toggle">Toggle Fullscreen</button>
```

The
[`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)
with the ID `"fs-toggle"` will change between pale red and pale green
depending on whether or not the document is in fullscreen mode.

### CSS

The magic happens in the CSS. There are two rules here. The first
establishes the background color of the \"Toggle Fullscreen Mode\"
button when the element is not in a fullscreen state. The key is the use
of the `:not(:fullscreen)`, which looks for the element to not have the
`:fullscreen` pseudo-class applied to it.

[css]

```css
#fs-toggle:not(:fullscreen) {
  background-color: #afa;
}
```

When the document *is* in fullscreen mode, the following CSS applies
instead, setting the background color to a pale shade of red.

[css]

```css
#fs-toggle:fullscreen {
  background-color: #faa;
}
```

Specifications
--------------

  --------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------

  [Fullscreen API Standard\
  [\#
  :fullscreen-pseudo-class]](https://fullscreen.spec.whatwg.org/#:fullscreen-pseudo-class)

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

`:fullscreen`

7115

12

649

11

5815

6

7137

7118

649

5014

No

10.01.0

`all_elements`

No

12--79

43

11

No

No

No

No

43

No

No

No

See also
--------

- [Fullscreen
    API](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API)
- [Guide to the Fullscreen
    API](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API/Guide)
- [`:not`](:not)
- [`::backdrop`](::backdrop)
- DOM API:
    [`Element.requestFullscreen()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/requestFullscreen),
    [`Document.exitFullscreen()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/exitFullscreen),
    [`Document.fullscreenElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenElement)
- [`allowfullscreen`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#allowfullscreen)
    attribute

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:fullscreen>
