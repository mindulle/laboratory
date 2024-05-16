CSS conditional rules
=====================

The **CSS conditional rules** module lets you define a set of rules that
will only apply based on the capabilities of the processor or the
document the style sheet is being applied to.

Reference
---------

### At-rules

- [`@document`](@document.md)
- [`@media`](@media.md)
- [`@supports`](@supports.md)
- [`@import`](@import.md)

Specifications
--------------

  -------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------

  [CSS Cascading and Inheritance Level 5\
  [\# at-import]](https://drafts.csswg.org/css-cascade-5/#at-import)

  [Media Queries Level 4\
  [\#
  media-descriptor-table]](https://drafts.csswg.org/mediaqueries/#media-descriptor-table)

  [CSS Conditional Rules Module Level 3\
  [\# at-media]](https://drafts.csswg.org/css-conditional-3/#at-media)

  [CSS Conditional Rules Module Level 4\
  [\# at-supports-ext]](https://drafts.csswg.org/css-conditional-4/#at-supports-ext)

[CSS Conditional Rules Module Level 3\
  [\# at-supports]](https://drafts.csswg.org/css-conditional-3/#at-supports)
  -------------------------------------------------------------------------------------------------

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

`CSS_conditional_rules`

No

No

61Only supports an empty `url-prefix()` value, which is supported due to
its [use in Firefox browser
detection](https://css-tricks.com/snippets/css/css-hacks-targeting-firefox/).
Still supported in user stylesheets.

1.5--61

No

No

No

No

No

61Only supports an empty `url-prefix()` value, which is supported due to
its [use in Firefox browser
detection](https://css-tricks.com/snippets/css/css-hacks-targeting-firefox/).
Still supported in user stylesheets.

4--61

No

No

No

`regexp`

No

No

6--61

No

No

No

No

No

6--61

No

No

No

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

`CSS_conditional_rules`

28

12

22

No

12.1

9

4.4

28

22

12.1

9

1.5

`font-format`

No

No

106

No

No

17

No

No

106

No

17

No

`font-tech`

No

No

106

No

No

17

No

No

106

No

17

No

`selector`

83

83

69

No

69

14.1

83

83

79

No

14.5

13.0

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

`-moz-device-pixel-ratio`

No

No

4

No

No

No

No

No

4

No

No

No

`-webkit-animation`

2--36

No

No

No

15--23

4

2--37

18--36

No

14--24

3.2

1.0--3.0

`-webkit-device-pixel-ratio`

1

12

63Implemented as an alias for `-moz-device-pixel-ratio`.

No

15

3

≤37

18

63Implemented as an alias for `-moz-device-pixel-ratio`.

14

1

1.0

`-webkit-max-device-pixel-ratio`

1

12

63Implemented as an alias for `max--moz-device-pixel-ratio`.

No

15

3

≤37

18

63Implemented as an alias for `max--moz-device-pixel-ratio`.

14

1

1.0

`-webkit-min-device-pixel-ratio`

1

12

63Implemented as an alias for `min--moz-device-pixel-ratio`.

No

15

3

≤37

18

63Implemented as an alias for `min--moz-device-pixel-ratio`.

14

1

1.0

`-webkit-transform-2d`

2--36

No

No

No

15--23

4

2--37

18--36

No

14--24

3.2

1.0--3.0

`-webkit-transform-3d`

2

12

49

No

15

4

4.4

18

49

14

3.2

1.0

`-webkit-transition`

2--36

No

No

No

15--23

4

2--37

18--36

No

14--24

3.2

1.0--3.0

`CSS_conditional_rules`

1

12

1

6

9.2

3

≤37

18

4

10.1

1

1.0

`any-hover`

41

16

64

No

28

9

41

41

64

28

9

5.0

`any-pointer`

41

12

64

No

28

9

41

41

64

28

9

4.0

`aspect-ratio`

3

12

3.5

9

10

5

≤37

18

4

10.1

4.2

1.0

`calc`

66

79

59

No

53

12

66

66

59

47

12

9.0

`color`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

`color-gamut`

58

79

110

No

45

10

58

58

110

43

10

7.0

`color-index`

29

79

No

No

16

8

4.4

29

No

16

8

2.0

`device-aspect-ratio`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

`device-height`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

`device-width`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

`display-mode`

42

79

47Firefox 47 and later support `display-mode` values `fullscreen` and
`browser`. Firefox 57 added support for `minimal-ui` and `standalone`
values.

No

29

13

42

42

47Only supports the `browser` value, which always reports `true`.

29

12.2

4.0

`dynamic-range`

98

98

100

No

84

13.1

98

98

100

68

13.4

18.0

`forced-colors`

89

79

89

No

75

16

89

89

89

63

16

15.0

`grid`

1

12

2

10

10

3

≤37

18

4

10.1

1

1.0

`height`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

`hover`

38Before Chrome 41, the implementation was buggy and reported
`(hover: none)` on non-touch-based computers with a mouse/trackpad. See
[bug 441613](https://crbug.com/441613).

12

64

No

28

9

38Before Chrome 41, the implementation was buggy and reported
`(hover: none)` on non-touch-based computers with a mouse/trackpad. See
[bug 441613](https://crbug.com/441613).

50

64

28

9

5.0

`inverted-colors`

No

No

114

No

No

9.1

No

No

No

No

10

No

`media_features`

1

12

1

9

9.2

3

4.4

18

4

10.1

1

1.0

`media_query_values`

66

79

59

No

53

No

66

66

59

47

No

9.0

`monochrome`

1

79

2

No

10

3

≤37

18

4

10.1

1

1.0

`nested-queries`

26

12

11

No

12.1

7

4.4

26

14

12.1

7

1.5

`or_syntax`

104

104

64

No

90

16.4

104

104

64

71

16.4

20.0

`orientation`

3

12

2

9

10.6

5

≤37

18

4

11

4.2

1.0

`overflow-block`

113

113

66

No

99

17

113

113

66

No

17

No

`overflow-inline`

113

113

66

No

99

17

113

113

66

No

17

No

`pointer`

41

12

64

No

28

9

41

50

64

28

9

5.0

`prefers-color-scheme`

76

79

67

No

62

12.1

76

76

67

54

13

14.2

`prefers-contrast`

96

96

101

No

82

14.1

96

96

101

No

14.5

17.0

`prefers-reduced-data`

85

85

No

No

71

No

No

85

No

No

No

No

`prefers-reduced-motion`

74

79

63

No

62

10.1

74

74

64

53

10.3

11.0

`prefers-reduced-transparency`

118

118

113

No

104

No

118

118

No

No

No

No

`range_syntax`

104

104

102

63Only supports range notations where the feature name comes before any
value `(width > 500px)`

No

90

16.4

104

104

102

63Only supports range notations where the feature name comes before any
value `(width > 500px)`

71

16.4

20.0

`resolution`

29

12

8

3.5Supports
[`<integer>`](https://developer.mozilla.org/docs/Web/CSS/integer) values
only.

9

1610--15

16

4.4

29

8

4Supports
[`<integer>`](https://developer.mozilla.org/docs/Web/CSS/integer) values
only.

1610.1--14

16

2.0

`scripting`

120

120

113

No

No

17

No

No

113

No

17

No

`update`

113

113

102

No

99

17

113

113

102

No

17

No

`video-dynamic-range`

98

98

100

No

84

No

No

98

100

No

No

No

`width`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

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

`CSS_conditional_rules`

1

12

1

5.5

3.5

1

≤37

18

4

10.1

1

1.0

`layer`

99

99

97

No

85

15.4

99

99

97

68

15.4

18.0

`supports`

No

No

115

No

No

No

No

No

115

No

No

No

### css.at-rules.import

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.at-rules.media

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.at-rules.supports

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.at-rules.document

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_conditional_rules>
