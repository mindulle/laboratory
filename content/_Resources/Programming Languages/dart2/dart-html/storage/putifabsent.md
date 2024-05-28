[dart:html](../../dart-html/dart-html-library){._links-link}

putIfAbsent method
==================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) putIfAbsent(

1.  [String](../../dart-core/string-class) key,
2.  [String](../../dart-core/string-class) ifAbsent( )

)

::: {.features}
override
:::
:::

Look up the value of `key`, or add a new entry if it isn\'t there.

Returns the value associated to `key`, if there is one. Otherwise calls
`ifAbsent` to get a new value, associates `key` to that value, and then
returns the new value.

``` {.language-dart data-language="dart"}
final diameters = <num, String>{1.0: 'Earth'};
final otherDiameters = <double, String>{0.383: 'Mercury', 0.949: 'Venus'};

for (final item in otherDiameters.entries) {
  diameters.putIfAbsent(item.key, () => item.value);
}
print(diameters); // {1.0: Earth, 0.383: Mercury, 0.949: Venus}

// If the key already exists, the current value is returned.
final result = diameters.putIfAbsent(0.383, () => 'Random');
print(result); // Mercury
print(diameters); // {1.0: Earth, 0.383: Mercury, 0.949: Venus}
```

Calling `ifAbsent` must not add or remove keys from the map.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String putIfAbsent(String key, String ifAbsent()) {
  if (!containsKey(key)) this[key] = ifAbsent();
  return this[key] as String;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Storage/putIfAbsent.html>
:::
