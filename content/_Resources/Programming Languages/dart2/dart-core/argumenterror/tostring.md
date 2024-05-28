[dart:core](../../dart-core/dart-core-library){._links-link}

toString method
===============

::: {.section .multi-line-signature}
[String](../string-class) toString()

::: {.features}
override
:::
:::

A string representation of this object.

Some classes have a default textual representation, often paired with a
static `parse` function (like [int.parse](../int/parse)). These classes
will provide the textual representation as their string representation.

Other classes have no meaningful textual representation that a program
will care about. Such classes will typically override `toString` to
provide useful information when inspecting the object, mainly for
debugging or logging.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toString() {
  String? name = this.name;
  String nameString = (name == null) ? "" : " ($name)";
  Object? message = this.message;
  var messageString = (message == null) ? "" : ": ${message}";
  String prefix = "$_errorName$nameString$messageString";
  if (!_hasValue) return prefix;
  // If we know the invalid value, we can try to describe the problem.
  String explanation = _errorExplanation;
  String errorValue = Error.safeToString(invalidValue);
  return "$prefix$explanation: $errorValue";
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/ArgumentError/toString.html>
:::
