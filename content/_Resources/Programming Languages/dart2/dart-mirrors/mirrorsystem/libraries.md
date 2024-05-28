[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

libraries property
==================

::: {#getter .section .multi-line-signature}
[Map](../../dart-core/map-class)\<[Uri](../../dart-core/uri-class),
[LibraryMirror](../librarymirror-class)\> libraries
:::

All libraries known to the mirror system, indexed by their URI.

Returns an unmodifiable map of the libraries with
[LibraryMirror.uri](../librarymirror/uri) as keys.

For a runtime mirror system, only libraries which are currently loaded
are included, and repeated calls of this method may return different
maps as libraries are loaded.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Map<Uri, LibraryMirror> get libraries;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/MirrorSystem/libraries.html>
:::
