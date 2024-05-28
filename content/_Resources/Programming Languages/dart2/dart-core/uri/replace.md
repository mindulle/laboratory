[dart:core](../../dart-core/dart-core-library){._links-link}

replace method
==============

::: {.section .multi-line-signature}
[Uri](../uri-class) replace(

1.  {[String](../string-class)? scheme,
2.  [String](../string-class)? userInfo,
3.  [String](../string-class)? host,
4.  [int](../int-class)? port,
5.  [String](../string-class)? path,
6.  [Iterable](../iterable-class)\<[String](../string-class)\>?
    pathSegments,
7.  [String](../string-class)? query,
8.  [Map](../map-class)\<[String](../string-class), dynamic\>?
    queryParameters,
9.  [String](../string-class)? fragment}

)
:::

Creates a new `Uri` based on this one, but with some parts replaced.

This method takes the same parameters as the [Uri](../uri-class)
constructor, and they have the same meaning.

At most one of `path` and `pathSegments` must be provided. Likewise, at
most one of `query` and `queryParameters` must be provided.

Each part that is not provided will default to the corresponding value
from this `Uri` instead.

This method is different from [Uri.resolve](resolve), which overrides in
a hierarchical manner, and can instead replace each part of a `Uri`
individually.

Example:

``` {.language-dart data-language="dart"}
final uri1 = Uri.parse(
    'http://dart.dev/guides/libraries/library-tour#utility-classes');

final uri2 = uri1.replace(
    scheme: 'https',
    path: 'guides/libraries/library-tour',
    fragment: 'uris');
print(uri2); // https://dart.dev/guides/libraries/library-tour#uris
```

This method acts similarly to using the `Uri` constructor with some of
the arguments taken from this `Uri`. Example:

``` {.language-dart data-language="dart"}
final Uri uri3 = Uri(
    scheme: 'https',
    userInfo: uri1.userInfo,
    host: uri1.host,
    port: uri2.port,
    path: '/guides/language/language-tour',
    query: uri1.query,
    fragment: null);
print(uri3); // https://dart.dev/guides/language/language-tour
```

Using this method can be seen as shorthand for the `Uri` constructor
call above, but may also be slightly faster because the parts taken from
this `Uri` need not be checked for validity again.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uri replace(
    {String? scheme,
    String? userInfo,
    String? host,
    int? port,
    String? path,
    Iterable<String>? pathSegments,
    String? query,
    Map<String, dynamic /*String|Iterable<String>*/ >? queryParameters,
    String? fragment});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/replace.html>
:::
