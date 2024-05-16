background-repeat
=================

The `background-repeat`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
how background images are repeated. A background image can be repeated
along the horizontal and vertical axes, or not repeated at all.

Try it
------

By default, the repeated images are clipped to the size of the element,
but they can be scaled to fit (using `round`) or evenly distributed from
end to end (using `space`).

Syntax
------

[css]

```css
/* Keyword values */
background-repeat: repeat-x;
background-repeat: repeat-y;
background-repeat: repeat;
background-repeat: space;
background-repeat: round;
background-repeat: no-repeat;

/* Two-value syntax: horizontal | vertical */
background-repeat: repeat space;
background-repeat: repeat repeat;
background-repeat: round space;
background-repeat: no-repeat round;

/* Global values */
background-repeat: inherit;
background-repeat: initial;
background-repeat: revert;
background-repeat: revert-layer;
background-repeat: unset;
```

### Values

[`<repeat-style>`](#repeat-style)

:   The one-value syntax is a shorthand for the full two-value syntax:

      ------------------ --------------------------
      **Single value**   **Two-value equivalent**
      `repeat-x`         `repeat no-repeat`
      `repeat-y`         `no-repeat repeat`
      `repeat`           `repeat repeat`
      `space`            `space space`
      `round`            `round round`
      `no-repeat`        `no-repeat no-repeat`
      ------------------ --------------------------
    

    In the two-value syntax, the first value represents the horizontal
    repetition behavior and the second value represents the vertical
    behavior. Here is an explanation of how each option works for either
    direction:

    
      ------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
      `repeat`      The image is repeated as much as needed to cover the whole background image painting area. The last image will be clipped if it doesn\'t fit.
      `space`       The image is repeated as much as possible without clipping. The first and last images are pinned to either side of the element, and whitespace is distributed evenly between the images. The [`background-position`](background-position) property is ignored unless only one image can be displayed without clipping. The only case where clipping happens using `space` is when there isn\'t enough room to display one image.
      `round`       As the allowed space increases in size, the repeated images will stretch (leaving no gaps) until there is room (space left \>= half of the image width) for another one to be added. When the next image is added, all of the current ones compress to allow room. Example: An image with an original width of 260px, repeated three times, might stretch until each repetition is 300px wide, and then another image will be added. They will then compress to 225px.
      `no-repeat`   The image is not repeated (and hence the background image painting area will not necessarily be entirely covered). The position of the non-repeated background image is defined by the [`background-position`](background-position) CSS property.
      ------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `repeat`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   a list, each item consisting of two keywords, one per dimension
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
background-repeat = 
  <repeat-style>#  

<repeat-style> = 
  repeat-x                                     |
  repeat-y                                     |
  [ repeat | space | round | no-repeat ]  
```

Examples
--------

### Setting background-repeat

#### HTML

[html]

```html
<ol>
  <li>
    no-repeat
    <div class="one"></div>
  </li>
  <li>
    repeat
    <div class="two"></div>
  </li>
  <li>
    repeat-x
    <div class="three"></div>
  </li>
  <li>
    repeat-y
    <div class="four"></div>
  </li>
  <li>
    space
    <div class="five"></div>
  </li>
  <li>
    round
    <div class="six"></div>
  </li>
  <li>
    repeat-x, repeat-y (multiple images)
    <div class="seven"></div>
  </li>
</ol>
```

#### CSS

[css]

```css
/* Shared for all DIVS in example */
ol,
li {
  margin: 0;
  padding: 0;
}
li {
  margin-bottom: 12px;
}
div {
  background-image: url(starsolid.gif);
  width: 160px;
  height: 70px;
}

/* Background repeats */
.one {
  background-repeat: no-repeat;
}
.two {
  background-repeat: repeat;
}
.three {
  background-repeat: repeat-x;
}
.four {
  background-repeat: repeat-y;
}
.five {
  background-repeat: space;
}
.six {
  background-repeat: round;
}

/* Multiple images */
.seven {
  background-image: url(starsolid.gif), url(favicon32.png);
  background-repeat: repeat-x, repeat-y;
  height: 144px;
}
```

#### Result

In this example, each list item is matched with a different value of
`background-repeat`.

Specifications
--------------

  --------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  the-background-repeat]](https://drafts.csswg.org/css-backgrounds/#the-background-repeat)

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

`2-value`

3

12

13

9

10.5

5

≤37

18

14

11

4

1.0

`background-repeat`

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

`multiple_backgrounds`

1

12

3.6

9

10.5

1.3

4.4

18

4

11

1

1.0

`round_space`

30

12

49

9

1710.5--15

8

4.4

30

49

18

8

2.0

See also
--------

- [](using_multiple_backgrounds.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/background-repeat>
