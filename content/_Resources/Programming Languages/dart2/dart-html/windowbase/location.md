[dart:html](../../dart-html/dart-html-library){._links-link}

location property
=================

::: {#getter .section .multi-line-signature}
[LocationBase](../locationbase-class) location
:::

The current location of this window.

``` {.language-dart data-language="dart"}
Location currentLocation = window.location;
print(currentLocation.href); // 'http://www.example.com:80/'
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
LocationBase get location;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/WindowBase/location.html>
:::
