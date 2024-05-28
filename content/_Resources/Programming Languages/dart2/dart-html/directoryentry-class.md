[dart:html](../dart-html/dart-html-library){._links-link}

DirectoryEntry class
====================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Entry](entry-class)
    -   DirectoryEntry

Annotations

:   -   \@Native(\"DirectoryEntry,webkitFileSystemDirectoryEntry,FileSystemDirectoryEntry\")

Properties {#instance-properties}
----------

[filesystem](entry/filesystem) → [FileSystem](filesystem-class)?

::: {.features}
read-only, inherited
:::

[fullPath](entry/fullpath) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isDirectory](entry/isdirectory) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[isFile](entry/isfile) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[name](entry/name) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
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
\@JSName(\'copyTo\'), inherited
:::

[createDirectory](directoryentry/createdirectory)([String](../dart-core/string-class)
path, {[bool](../dart-core/bool-class) exclusive = false}) →
[Future](../dart-async/future-class)\<[Entry](entry-class)\>

Create a new directory with the specified `path`. If `exclusive` is
true, the returned Future will complete with an error if a directory
already exists with the specified `path`.

[createFile](directoryentry/createfile)([String](../dart-core/string-class)
path, {[bool](../dart-core/bool-class) exclusive = false}) →
[Future](../dart-async/future-class)\<[Entry](entry-class)\>

Create a new file with the specified `path`. If `exclusive` is true, the
returned Future will complete with an error if a file already exists at
the specified `path`.

[createReader](directoryentry/createreader)() →
[DirectoryReader](directoryreader-class)

[getDirectory](directoryentry/getdirectory)([String](../dart-core/string-class)
path) → [Future](../dart-async/future-class)\<[Entry](entry-class)\>

Retrieve an already existing directory entry. The returned future will
result in an error if a directory at `path` does not exist or if the
item at `path` is not a directory.

[getFile](directoryentry/getfile)([String](../dart-core/string-class)
path) → [Future](../dart-async/future-class)\<[Entry](entry-class)\>

Retrieve an already existing file entry. The returned future will result
in an error if a file at `path` does not exist or if the item at `path`
is not a file.

[getMetadata](entry/getmetadata)() →
[Future](../dart-async/future-class)\<[Metadata](metadata-class)\>

::: {.features}
\@JSName(\'getMetadata\'), inherited
:::

[getParent](entry/getparent)() →
[Future](../dart-async/future-class)\<[Entry](entry-class)\>

::: {.features}
\@JSName(\'getParent\'), inherited
:::

[moveTo](entry/moveto)([DirectoryEntry](directoryentry-class) parent,
{[String](../dart-core/string-class)? name}) →
[Future](../dart-async/future-class)\<[Entry](entry-class)\>

::: {.features}
\@JSName(\'moveTo\'), inherited
:::

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[remove](entry/remove)() → [Future](../dart-async/future-class)

::: {.features}
\@JSName(\'remove\'), inherited
:::

[removeRecursively](directoryentry/removerecursively)() →
[Future](../dart-async/future-class)

::: {.features}
\@JSName(\'removeRecursively\')
:::

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[toUrl](entry/tourl)() → [String](../dart-core/string-class)

::: {.features}
\@JSName(\'toURL\'), inherited
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
<https://api.dart.dev/stable/2.18.5/dart-html/DirectoryEntry-class.html>
:::
