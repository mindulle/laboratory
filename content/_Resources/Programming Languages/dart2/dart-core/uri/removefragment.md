[dart:core](../../dart-core/dart-core-library){._links-link}

removeFragment method
=====================

::: {.section .multi-line-signature}
[Uri](../uri-class) removeFragment()
:::

Creates a `Uri` that differs from this only in not having a fragment.

If this `Uri` does not have a fragment, it is itself returned.

Example:

``` {.language-dart data-language="dart"}
final uri =
    Uri.parse('https://example.org:8080/foo/bar#frag').removeFragment();
print(uri); // https://example.org:8080/foo/bar
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uri removeFragment();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/removeFragment.html>
:::
