background-attachment
=====================

The `background-attachment`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
whether a background image\'s position is fixed within the
[viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport),
or scrolls with its containing block.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
background-attachment: scroll;
background-attachment: fixed;
background-attachment: local;

/* Global values */
background-attachment: inherit;
background-attachment: initial;
background-attachment: revert;
background-attachment: revert-layer;
background-attachment: unset;
```

The `background-attachment` property is specified as one of the keyword
values from the list below.

### Values

[`fixed`](#fixed)

:   The background is fixed relative to the viewport. Even if an element
    has a scrolling mechanism, the background doesn\'t move with the
    element. (This is not compatible with
    [`background-clip: text`](background-clip.md#values).)

[`local`](#local)

:   The background is fixed relative to the element\'s contents. If the
    element has a scrolling mechanism, the background scrolls with the
    element\'s contents, and the background painting area and background
    positioning area are relative to the scrollable area of the element
    rather than to the border framing them.

[`scroll`](#scroll)

:   The background is fixed relative to the element itself and does not
    scroll with its contents. (It is effectively attached to the
    element\'s border.)

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `scroll`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
background-attachment = 
  <attachment>#  

<attachment> = 
  scroll  |
  fixed   |
  local   
```

Examples
--------

### Simple example

#### HTML

[html]

```html
<p>
  There were doors all round the hall, but they were all locked; and when Alice
  had been all the way down one side and up the other, trying every door, she
  walked sadly down the middle, wondering how she was ever to get out again.
</p>
```

#### CSS

[css]

```css
p {
  background-image: url("starsolid.gif");
  background-attachment: fixed;
}
```

#### Result

### Multiple background images

This property supports multiple background images. You can specify a
different `<attachment>` for each background, separated by commas. Each
image is matched with the corresponding `<attachment>` type, from first
specified to last.

#### HTML

[html]

```html
<p>
  There were doors all round the hall, but they were all locked; and when Alice
  had been all the way down one side and up the other, trying every door, she
  walked sadly down the middle, wondering how she was ever to get out again.
  Suddenly she came upon a little three-legged table, all made of solid glass;
  there was nothing on it except a tiny golden key, and Alice's first thought
  was that it might belong to one of the doors of the hall; but, alas! either
  the locks were too large, or the key was too small, but at any rate it would
  not open any of them. However, on the second time round, she came upon a low
  curtain she had not noticed before, and behind it was a little door about
  fifteen inches high: she tried the little golden key in the lock, and to her
  great delight it fitted!
</p>
```

#### CSS

[css]

```css
p {
  background-image: url("starsolid.gif"), url("startransparent.gif");
  background-attachment: fixed, scroll;
  background-repeat: no-repeat, repeat-y;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  the-background-attachment]](https://drafts.csswg.org/css-backgrounds/#the-background-attachment)

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

`background-attachment`

1

12

1

4

3.5

1

≤37

18

4

10.1

3.2

1.0

`fixed`

1

12

2

9

10.5

15.4

14--15.4`local` is recognized but has no effect due to [a
bug](https://webkit.org/b/219324).

3.1--14

37

18

4

14

15.4

5--15.4`fixed` is recognized but has no effect. See [bug
219324](https://webkit.org/b/219324).

1.0

`local`

1

12

25

9

10.5

15.4

13--15.4`local` is recognized but has no effect due to [a
bug](https://webkit.org/b/219324).

5--13

37

18

25

14

15.4

13--15.4`local` is recognized but has no effect due to [a
bug](https://webkit.org/b/219324).

4.2--13If `-webkit-overflow-scrolling: touch` is set, then `local` has
no effect.

1.0

`multiple_backgrounds`

1

12

3.6

9

10.5

1.3

≤37

18

4

11

3.2

1.0

See also
--------

- [](using_multiple_backgrounds.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/background-attachment>
