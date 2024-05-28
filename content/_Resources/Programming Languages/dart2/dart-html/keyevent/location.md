[dart:html](../../dart-html/dart-html-library){._links-link}

location property
=================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) location

::: {.features}
override
:::
:::

Accessor to the part of the keyboard that the key was pressed from (one
of KeyLocation.STANDARD, KeyLocation.RIGHT, KeyLocation.LEFT,
KeyLocation.NUMPAD, KeyLocation.MOBILE, KeyLocation.JOYSTICK).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get location => _parent.location;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/KeyEvent/location.html>
:::
