Using multiple backgrounds
==========================

You can apply **multiple backgrounds** to elements. These are layered
atop one another with the first background you provide on top and the
last background listed in the back. Only the last background can include
a background color.

Specifying multiple backgrounds is easy:

[css]

```css
.myclass {
  background:
    background1,
    background2,
    /* …, */ backgroundN;
}
```

You can do this with both the shorthand [`background`](background.md)
property and the individual properties thereof except for
[`background-color`](background-color.md). That is, the following
background properties can be specified as a list, one per background:
[`background`](background.md),
[`background-attachment`](background-attachment.md),
[`background-clip`](background-clip.md),
[`background-image`](background-image.md),
[`background-origin`](background-origin.md),
[`background-position`](background-position.md),
[`background-repeat`](background-repeat.md),
[`background-size`](background-size.md).

Example
-------

In this example, three backgrounds are stacked: the Firefox logo, an
image of bubbles, and a [linear gradient](linear-gradient.md):

### HTML

[html]

```html
<div class="multi-bg-example"></div>
```

### CSS

[css]

```css
.multi-bg-example {
  width: 100%;
  height: 400px;
  background-image: url(firefox.png), url(bubbles.png), linear-gradient(to right, rgba(30, 75, 115, 1), rgba(255, 255, 255, 0));
  background-repeat: no-repeat, no-repeat, no-repeat;
  background-position:
    bottom right,
    left,
    right;
}
```

### Result

(If image does not appear in CodePen, click the \'Tidy\' button in the
CSS section)

As you can see here, the Firefox logo (listed first within
[`background-image`](background-image.md)) is on top, directly above the
bubbles graphic, followed by the gradient (listed last) sitting
underneath all previous \'images\'. Each subsequent sub-property
([`background-repeat`](background-repeat.md) and
[`background-position`](background-position.md)) applies to the
corresponding backgrounds. So the first listed value for
[`background-repeat`](background-repeat.md) applies to the first
(frontmost) background, and so forth.

See also
--------

- [Using CSS gradients](using_css_gradients.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders/Using_multiple_backgrounds>
