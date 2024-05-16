paint()
=======

The `paint()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) defines an [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) value
generated with a PaintWorklet.

Syntax
------

[css]

```css
paint(workletName, ...parameters)
```

where:

[*workletName*](#workletname)

:   The name of the registered worklet.

[*parameters*](#parameters)

:   Optional additional parameters to pass to the paintWorklet

Examples
--------

### Basic usage example

In JavaScript, we register the [paint
worklet](https://developer.mozilla.org/en-US/docs/Web/API/PaintWorkletGlobalScope):

[js]

```js
CSS.paintWorklet.addModule("boxbg.js");
```

\...then, in the CSS, we define the `background-image` as a `paint()`
type with the worklet name, `boxbg`, along with any variables (ex.
`--boxColor` and `--widthSubtractor`) the worklet will use:

[css]

```css
li {
  background-image: paint(boxbg);
  --boxColor: hsl(55 90% 60% / 1);
}
li:nth-of-type(3n) {
  --boxColor: hsl(155 90% 60% / 1);
  --widthSubtractor: 20;
}
li:nth-of-type(3n + 1) {
  --boxColor: hsl(255 90% 60% / 1);
  --widthSubtractor: 40;
}
```

The result will be the following:

### With additional parameters

You can pass additional arguments via the CSS paint() function. In this
example, we passed two arguments: whether the background-image on a
group of list items is filled or just has a stroke outline, and the
width of that outline:

[css]

```css
li {
  --boxColor: hsl(55 90% 60% / 1);
  background-image: paint(hollowHighlights, stroke, 2px);
}

li:nth-of-type(3n) {
  --boxColor: hsl(155 90% 60% / 1);
  background-image: paint(hollowHighlights, filled, 3px);
}

li:nth-of-type(3n + 1) {
  --boxColor: hsl(255 90% 60% / 1);
  background-image: paint(hollowHighlights, stroke, 1px);
}
```

We\'ve included a custom property in the selector block defining a
boxColor. Custom properties are accessible to the PaintWorklet.

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [CSS Painting API Level 1\
  [\#
  paint-notation]](https://drafts.css-houdini.org/css-paint-api/#paint-notation)

  ----------------------------------------------------------------------------------------

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

`paint`

65

79

No

No

52

No

65

65

No

47

No

9.2

`additional_parameters`

No

No

No

No

No

No

No

No

No

No

No

No

See also
--------

- [`PaintWorkletGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/PaintWorkletGlobalScope)
- [CSS Painting
    API](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Painting_API)
- [Using the CSS Painting
    API](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Painting_API/Guide)
- [`<image>`](_Resources/Markup%20And%20Styling/css/image.md)
- [Canvas
    API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/image/paint>
