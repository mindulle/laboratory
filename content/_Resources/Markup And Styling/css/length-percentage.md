\<length-percentage\>
=====================

The `<length-percentage>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](css_types.md) represents a value that can be either a
[`<length>`](length.md) or a [`<percentage>`](percentage.md).

Syntax
------

Refer to the documentation for [`<length>`](length.md) and
[`<percentage>`](percentage.md) for details of the individual syntaxes
allowed by this type.

Formal syntax
-------------

```
<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### length-percentage examples

The following simple example demonstrates several properties that use
`<length-percentage>` values.

#### HTML

[html]

```html
<p>You can use percentages and lengths in so many places.</p>
```

#### CSS

[css]

```css
p {
  /* length-percentage examples */
  width: 75%;
  height: 200px;
  margin: 3rem;
  padding: 1%;
  border-radius: 10px 10%;
  font-size: 250%;
  line-height: 1.5em;

  /* length examples */
  text-shadow: 1px 1px 1px red;
  border: 5px solid red;
  letter-spacing: 3px;

  /* percentage example */
  text-size-adjust: 20%;
}
```

#### Result

### Use in calc()

Where a `<length-percentage>` is specified as an allowable type, this
means that the percentage resolves to a length and therefore can be used
in a [`calc()`](calc.md) expression. Therefore, all of the following values
are acceptable for [`width`](_Resources/Markup%20And%20Styling/css/width.md):

[css]

```css
width: 200px;
width: 20%;
width: calc(100% - 200px);
```

Specifications
--------------

  -------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\#
  mixed-percentages]](https://drafts.csswg.org/css-values/#mixed-percentages)

  -------------------------------------------------------------------------------------

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

`Q`

63

79

49

No

50

No

63

63

49

46

No

8.0

`length-percentage`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

`cap`

No

No

97

No

No

No

No

No

97

No

No

No

`ch`

27

12

1\[\"From Firefox 1 to Firefox 3, `ch` was the width of the *M*
character.\", \"From Firefox 1 to Firefox 3, `ch` did not work with
[`border-width`](https://developer.mozilla.org/docs/Web/CSS/border-width)
and
[`outline-width`](https://developer.mozilla.org/docs/Web/CSS/outline-width)
CSS properties.\"\]

9

15

7

4.4

27

4

15

7

1.5

`ex`

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

`ic`

No

No

97

No

No

No

No

No

97

No

No

No

`lh`

No

No

No

No

No

16.4

No

No

No

No

16.4

No

`mozmm`

No

No

4--59

No

No

No

No

No

4--59

No

No

No

`rem`

4

12

3.6

9

11.6

5

2

18

4

12

4

1.0

`rlh`

No

No

No

No

No

16.4

No

No

No

No

16.4

No

`vb`

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

`vh`

20

12

19

9

20

6

4.4

25

19

14

6

1.5

`vi`

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

`vmax`

26

16

19Starting with version 21, viewport-percentage lengths are invalid in
`@page`.

No

15

7

1.5

26

19Starting with version 21, viewport-percentage lengths are invalid in
`@page`.

14

7

1.5

`vmin`

26

1212

19Starting with version 21, viewport-percentage lengths are invalid in
`@page`.

109

15

7

4.4

26

19Starting with version 21, viewport-percentage lengths are invalid in
`@page`.

14

7

1.5

`vw`

20

12

19Starting with version 21, viewport-percentage lengths are invalid in
`@page`.

9

20

6

4.4

25

19Starting with version 21, viewport-percentage lengths are invalid in
`@page`.

14

6

1.5

See also
--------

- [`<percentage>`](percentage.md)
- [`<length>`](length.md)
- [CSS Values and Units](css_values_and_units.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage>
