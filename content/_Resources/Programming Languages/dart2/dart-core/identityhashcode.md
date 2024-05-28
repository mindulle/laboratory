[dart:core](../dart-core/dart-core-library){._links-link}

identityHashCode function
=========================

::: {.section .multi-line-signature}
[int](int-class) identityHashCode(

1.  [Object](object-class)? object

)
:::

The identity hash code of `object`.

Returns the value that the original [Object.hashCode](object/hashcode)
would return on this object, even if `hashCode` has been overridden.

This hash code is compatible with [identical](identical), which just
means that it\'s guaranteed to be stable over time.

``` {.language-dart data-language="dart"}
var identitySet = HashSet(equals: identical, hashCode: identityHashCode);
var dt1 = DateTime.now();
var dt2 = DateTime.fromMicrosecondsSinceEpoch(dt1.microsecondsSinceEpoch);
assert(dt1 == dt2);
identitySet.add(dt1);
print(identitySet.contains(dt1)); // true
print(identitySet.contains(dt2)); // false
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma("vm:entry-point")
external int identityHashCode(Object? object);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/identityHashCode.html>
:::
