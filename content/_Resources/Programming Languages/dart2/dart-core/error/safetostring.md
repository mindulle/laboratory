[dart:core](../../dart-core/dart-core-library){._links-link}

safeToString method
===================

::: {.section .multi-line-signature}
[String](../string-class) safeToString(

1.  [Object](../object-class)? object

)
:::

Safely convert a value to a [String](../string-class) description.

The conversion is guaranteed to not throw, so it won\'t use the
object\'s toString method except for specific known and trusted types.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String safeToString(Object? object) {
  if (object is num || object is bool || null == object) {
    return object.toString();
  }
  if (object is String) {
    return _stringToSafeString(object);
  }
  return _objectToString(object);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Error/safeToString.html>
:::
