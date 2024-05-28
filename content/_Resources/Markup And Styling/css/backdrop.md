::backdrop
==========

The `::backdrop` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-element](pseudo-elements.md) is a box the size of the
[viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport),
which is rendered immediately beneath any element being presented in the
[top
layer](https://developer.mozilla.org/en-US/docs/Glossary/Top_layer).

Try it
------

Syntax
------

[css]

```css
::backdrop {
  /* ... */
}
```

Description
-----------

Backdrops appear in the following instances:

- Elements which have been placed in fullscreen mode using the
    [Fullscreen
    API](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API)
    [`Element.requestFullscreen()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/requestFullscreen)
    method.
- [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog)
    elements that have been shown in the top layer via a
    [`HTMLDialogElement.showModal()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement/showModal)
    call.
- [Popover](https://developer.mozilla.org/en-US/docs/Web/API/Popover_API)
    elements that have been shown in the top layer via a
    [`HTMLElement.showPopover()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/showPopover)
    call.

When multiple elements have been placed into the top layer, each one has
its own `::backdrop` pseudo-element.

[css]

```css
/* Backdrop is only displayed when dialog is opened with dialog.showModal() */
dialog::backdrop {
  background: rgba(255, 0, 0, 0.25);
}
```

Elements are placed in a last-in/first out (LIFO) stack in the top
layer. The `::backdrop` pseudo-element makes it possible to obscure,
style, or completely hide everything located below a top layer element.

`::backdrop` neither inherits from nor is inherited by any other
elements. No restrictions are made on what properties apply to this
pseudo-element.

Examples
--------

### Styling the backdrop for fullscreen video

In this example, the backdrop style used when a video is shifted to
fullscreen mode is configured to be a grey-blue color rather than the
black it defaults to in most browsers.

[css]

```css
video::backdrop {
  background-color: #448;
}
```

The resulting screen looks like this:

![An almost full-screen video player with purple above and below the
player as the video player doesn\'t completely fill the
screen.](https://developer.mozilla.org/en-US/docs/Web/CSS/::backdrop/bbb-backdrop.png)

[See this example in
action](https://mdn.github.io/css-examples/backdrop/index.html), after
changing the color of the background cause the video to go fullscreen to
see the change to the backdrop color.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Positioned Layout Module Level 4\
  [\#
  backdrop]](https://drafts.csswg.org/css-position-4/#backdrop)

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

`::backdrop`

3732

7912--79

47

11

2419

15.4

374.4.3

3732

47

2419

15.4

3.02.0

`dialog`

32

79

98

No

19

15.4

4.4.3

32

98

19

15.4

2.0

`fullscreen`

No

12--79

47

11

No

No

No

No

47

No

No

No

`popover`

114

114

114

No

100

17

114

114

No

No

17

No

See also
--------

- [`:fullscreen`](:fullscreen) pseudo-class
- [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog)
    HTML element
- [Fullscreen
    API](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API)
- [Popover
    API](https://developer.mozilla.org/en-US/docs/Web/API/Popover_API)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/::backdrop>
