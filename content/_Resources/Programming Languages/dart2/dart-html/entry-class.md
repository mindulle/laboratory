[dart:html](../dart-html/dart-html-library){._links-link}

Entry class
===========

Implementers

:   -   [DirectoryEntry](directoryentry-class)
    -   [FileEntry](fileentry-class)

Annotations

:   -   \@Native(\"Entry,webkitFileSystemEntry,FileSystemEntry\")

Properties {#instance-properties}
----------

[filesystem](entry/filesystem) → [FileSystem](filesystem-class)?

::: {.features}
read-only
:::

[fullPath](entry/fullpath) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isDirectory](entry/isdirectory) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[isFile](entry/isfile) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[name](entry/name) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[copyTo](entry/copyto)([DirectoryEntry](directoryentry-class) parent,
{[String](../dart-core/string-class)? name}) →
[Future](../dart-async/future-class)\<[Entry](entry-class)\>

::: {.features}
\@JSName(\'copyTo\')
:::

[getMetadata](entry/getmetadata)() →
[Future](../dart-async/future-class)\<[Metadata](metadata-class)\>

::: {.features}
\@JSName(\'getMetadata\')
:::

[getParent](entry/getparent)() →
[Future](../dart-async/future-class)\<[Entry](entry-class)\>

::: {.features}
\@JSName(\'getParent\')
:::

[moveTo](entry/moveto)([DirectoryEntry](directoryentry-class) parent,
{[String](../dart-core/string-class)? name}) →
[Future](../dart-async/future-class)\<[Entry](entry-class)\>

::: {.features}
\@JSName(\'moveTo\')
:::

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[remove](entry/remove)() → [Future](../dart-async/future-class)

::: {.features}
\@JSName(\'remove\')
:::

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[toUrl](entry/tourl)() → [String](../dart-core/string-class)

::: {.features}
\@JSName(\'toURL\')
:::

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Entry-class.html>
:::
