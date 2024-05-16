\<ratio\>
=========

The `<ratio>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[data type](css_types.md), used for describing [](_Resources/Markup%20And%20Styling/css/@media/aspect-ratio.md) in [media queries](css_media_queries.md),
denotes the proportion between two unitless values.

Syntax
------

In Media Queries Level 3, the `<ratio>` data type consisted of a
strictly positive [`<integer>`](integer.md) followed by a forward slash
(\'/\', Unicode `U+002F SOLIDUS`) and a second strictly positive
[`<integer>`](integer.md). Spaces before and after the slash are optional.
The first number represents the width, while the second represents the
height.

In Media Queries Level 4, the `<ratio>` date type is updated to consist
of a strictly positive [`<number>`](number.md) followed by a forward slash
(\'/\', Unicode `U+002F SOLIDUS`) and a second strictly positive
[`<number>`](number.md). In addition a single [`<number>`](number.md) as a
value is allowable.

Formal syntax
-------------

```
<ratio> = 
  <number [0,∞]> [ / <number [0,∞]> ]?  
```

Examples
--------

### Use in a media query

[css]

```css
@media screen and (min-aspect-ratio: 16/9) {
  /* … */
}
```

### Common aspect ratios

![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAO0AAADHCAMAAADCpCTtAAAA1VBMVEX///9NTk87PDv39/f6+vqrq6v2//+Zy/sAAACq1Pyam50LCwv99dFQUFD//usdQ5Tw/v////hmZ2dPDgosBwVEDAi53vlXicNcXmC2trKt0++IRxT878t2pdPJnmXZ19SujGYtKB2ldDYADWnl0q0mLj0dQ42Ls9rgxp3R5PCWZCskUJuBRBOpg1D03K8ACEMABSwkUJRikcmbwuSnt9DTrnmPqMimn5lcOQ/19N7CwsJbDwsUMYyeiomAeWcdQVqEiYLa8f7e8f5pTzG7pYVkeZb55bsN0I14AAACcElEQVR42u3d21LaUBSA4UgCXVWIAUEBkUMrCFoFPJ9ae9C+/yN1J5AOYRy96PQia/3/RXRgnOGbDTt7Z0bieW9W3FppsPak5K63sV6rkCTJsbKu/ZCvPr6nTV2vP4oWLVq0aNGiRYsWLVq0aNGiRYsWLVq0aNGiRYsWLVq0aNGiRYsWLVq0aNGiRYsWLVq0aNGiVab1fd+KNnweiMjTdWRB23lY/uPM5x/6teEXB31pnbrjKFKvHYtM2+7nYV2krV1b/SSyl/zmRvdAvbZfWA5pN2XrnpP9v4N8ZGV1EfbdNLVrQht+/ebmqOzQ6tWWY6tMf9rQdnY2bkXqs7aZXcFhw62mIjN7oDP3dr4wo41PQefaVxe91uby/dvVry030tNs9Ti7dNSoDffTBeOZZLcFKj+3Vw55vZyTR5GJ/e3w+y93nBlYOd4dp9cuJibWUuPasDBsXpa4wooWLVq0aNGiRYsWLVq0aNGiRYsWLVq0aNGiRYsWLVq0aNGiRYsWLVq0aNGiRYsWLVq0aNGiRYtWhba3mSTJsahdW1y9D/JAu3ZSXKm1rtV23+qqR0RERERERIut/n2uXu5975/+fEOCHGF9qaBFixatam2+YmzRokWrWVsxpSUiSus05KRkBRt/sfF2ZEXbdQv4bStjG39TtRlteGtJeypSa1jRjkUe7x6MaMs7MtstGxnbxZ0DHNmE9kpkHlnR/q7LdOIZ0cY3EDhafHjn+rVuEXVSCoLArZNHUaB9aPczV38PlE/IWe2ecm2/tqjprM3mhZF9gZul7OxvkzNQZEk7NzS2dXm0M7bhzc2lR0RERERE9B/6A9Fbtqcp2UvrAAAAAElFTkSuQmCC)

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Media Queries Level 4\
  [\# values]](https://drafts.csswg.org/mediaqueries/#values)

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

`ratio`

3

12

3.5

9

9.5

5

≤37

18

4

14

4.2

1.0

`number_value`

No

No

70

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

- [`aspect-ratio`](_Resources/Markup%20And%20Styling/css/@media/aspect-ratio.md) media feature

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/ratio>
