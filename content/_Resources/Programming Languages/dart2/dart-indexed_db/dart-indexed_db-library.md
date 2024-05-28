dart:indexed\_db library
========================

A client-side key-value store with support for indexes.

Many browsers support IndexedDB---a web standard for an indexed
database. By storing data on the client in an IndexedDB, a web app gets
some advantages, such as faster performance and persistence. To find out
which browsers support IndexedDB, refer to [Can I
Use?](http://caniuse.com/#feat=indexeddb)

In IndexedDB, each record is identified by a unique index or key, making
data retrieval speedy. You can store structured data, such as images,
arrays, and maps using IndexedDB. The standard does not specify size
limits for individual data items or for the database itself, but
browsers may impose storage limits.

Using indexed\_db
-----------------

The classes in this library provide an interface to the browser\'s
IndexedDB, if it has one. To use this library in your code:

``` {.language-dart data-language="dart"}
import 'dart:indexed_db';
```

A web app can determine if the browser supports IndexedDB with
[IdbFactory.supported](idbfactory/supported):

``` {.language-dart data-language="dart"}
if (IdbFactory.supported)
  // Use indexeddb.
else
  // Find an alternative.
```

Access to the browser\'s IndexedDB is provided by the app\'s top-level
[Window](../dart-html/window-class) object, which your code can refer to
with `window.indexedDB`. So, for example, here\'s how to use
window.indexedDB to open a database:

``` {.language-dart data-language="dart"}
Future open() {
  return window.indexedDB.open('myIndexedDB',
      version: 1,
      onUpgradeNeeded: _initializeDatabase)
    .then(_loadFromDB);
}
void _initializeDatabase(VersionChangeEvent e) {
  ...
}
Future _loadFromDB(Database db) {
  ...
}
```

All data in an IndexedDB is stored within an
[ObjectStore](objectstore-class). To manipulate the database use
[Transaction](transaction-class)s.

Other resources
---------------

Other options for client-side data storage include:

-   [Window.localStorage](../dart-html/window/localstorage)---a basic
    mechanism that stores data as a [Map](../dart-core/map-class), and
    where both the keys and the values are strings.

MDN provides [API
documentation](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API).

Classes
-------

[Cursor](cursor-class)

[CursorWithValue](cursorwithvalue-class)

[Database](database-class)

An indexed database object for storing client-side data in web apps.

[IdbFactory](idbfactory-class)

[Index](index-class)

[KeyRange](keyrange-class)

[ObjectStore](objectstore-class)

[Observation](observation-class)

[Observer](observer-class)

[ObserverChanges](observerchanges-class)

[OpenDBRequest](opendbrequest-class)

[Request](request-class)

[Transaction](transaction-class)

[VersionChangeEvent](versionchangeevent-class)

Typedefs
--------

[ObserverCallback](observercallback) = void
Function([ObserverChanges](observerchanges-class) changes)

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/dart-indexed_db-library.html>
:::
