Resizing background images with background-size
===============================================

The **[`background-size`](background-size.md)** CSS property lets you
resize the background image of an element, overriding the default
behavior of tiling the image at its full size by specifying the width
and/or height of the image. By doing so, you can scale the image upward
or downward as desired.

Tiling a large image
--------------------

Let\'s consider a large image, a 2982x2808 Firefox logo image. We want
(for some reason likely involving horrifyingly bad site design) to tile
four copies of this image into a 300x300-pixel element. To do this, we
can use a fixed `background-size` value of 150 pixels.

### HTML

[html]

```html
<div class="tiledBackground"></div>
```

### CSS

[css]

```css
.tiledBackground {
  background-image: url(https://www.mozilla.org/media/img/logos/firefox/logo-quantum.9c5e96634f92.png);
  background-size: 150px;
  width: 300px;
  height: 300px;
  border: 2px solid;
  color: pink;
}
```

### Result

Stretching an image
-------------------

You can also specify both the horizontal and vertical sizes of the
image, like this:

[css]

```css
background-size: 300px 150px;
```

The result looks like this:

Scaling an image up
-------------------

On the other end of the spectrum, you can scale an image up in the
background. Here we scale a 32x32 pixel favicon to 300x300 pixels:

[css]

```css
.square2 {
  background-image: url(favicon.png);
  background-size: 300px;
  width: 300px;
  height: 300px;
  border: 2px solid;
  text-shadow: white 0px 0px 2px;
  font-size: 16px;
}
```

As you can see, the CSS is actually essentially identical, save the name
of the image file.

Special values: `contain` and `cover`
-------------------------------------

In addition to [`<length>`](length.md) values, the
[`background-size`](background-size.md) CSS property offers two special
size values, `contain` and `cover`. Let\'s take a look at these.

### `contain`

The `contain` value specifies that, regardless of the size of the
containing box, the background image should be scaled so that each side
is as large as possible while not exceeding the length of the
corresponding side of the container. Try resizing the example below to
see this in action.

#### HTML

[html]

```html
<div class="bgSizeContain">
  <p>Try resizing this element!</p>
</div>
```

#### CSS

[css]

```css
.bgSizeContain {
  background-image: url(https://www.mozilla.org/media/img/logos/firefox/logo-quantum.9c5e96634f92.png);
  background-size: contain;
  width: 160px;
  height: 160px;
  border: 2px solid;
  resize: both;
  overflow: scroll;
}
```

#### Result

### `cover`

The `cover` value specifies that the background image should be sized so
that it is as small as possible while ensuring that both dimensions are
greater than or equal to the corresponding size of the container. Try
resizing the example below to see this in action.

#### HTML

[html]

```html
<div class="bgSizeCover">
  <p>Try resizing this element!</p>
</div>
```

#### CSS

[css]

```css
.bgSizeCover {
  background-image: url(https://www.mozilla.org/media/img/logos/firefox/logo-quantum.9c5e96634f92.png);
  background-size: cover;
  width: 160px;
  height: 160px;
  border: 2px solid;
  resize: both;
  overflow: scroll;
}
```

#### Result

See also
--------

- [`background-size`](background-size.md)
- [`background`](background.md)
- [Scaling of SVG backgrounds](scaling_of_svg_backgrounds.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders/Resizing_background_images>
