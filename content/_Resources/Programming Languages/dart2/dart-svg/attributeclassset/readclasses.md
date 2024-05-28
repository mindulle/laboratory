[dart:svg](../../dart-svg/dart-svg-library){._links-link}

readClasses method
==================

::: {.section .multi-line-signature}
[Set](../../dart-core/set-class)\<[String](../../dart-core/string-class)\>
readClasses()
:::

Read the class names from the Element class property, and put them into
a set (duplicates are discarded). This is intended to be overridden by
specific implementations.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Set<String> readClasses() {
  var classname = _element.attributes['class'];
  if (classname is AnimatedString) {
    classname = (classname as AnimatedString).baseVal;
  }

  Set<String> s = new LinkedHashSet<String>();
  if (classname == null) {
    return s;
  }
  for (String name in classname.split(' ')) {
    String trimmed = name.trim();
    if (!trimmed.isEmpty) {
      s.add(trimmed);
    }
  }
  return s;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/readClasses.html>
:::
