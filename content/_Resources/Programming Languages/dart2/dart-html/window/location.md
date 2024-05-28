[dart:html](../../dart-html/dart-html-library){._links-link}

location property
=================

::: {#getter .section .multi-line-signature}
[Location](../location-class) location

::: {.features}
override
:::
:::

The current location of this window.

``` {.language-dart data-language="dart"}
Location currentLocation = window.location;
print(currentLocation.href); // 'http://www.example.com:80/'
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Location get location => _location;
```

::: {#setter .section .multi-line-signature}
void location=([LocationBase](../locationbase-class) value)
:::

Sets the window\'s location, which causes the browser to navigate to the
new location.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set location(value) {
  _location = value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/location.html>
:::
