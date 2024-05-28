[dart:io](../dart-io/dart-io-library){._links-link}

HttpOverrides class
===================

This class facilitates overriding [HttpClient](httpclient-class) with a
mock implementation. It should be extended by another class in client
code with overrides that construct a mock implementation. The
implementation in this base class defaults to the actual
[HttpClient](httpclient-class) implementation. For example:

``` {.language-dart data-language="dart"}
// An implementation of the HttpClient interface
class MyHttpClient implements HttpClient {
  MyHttpClient(SecurityContext? c);

  @override
  noSuchMethod(Invocation invocation) {
    // your implementation here
  }
}

void main() {
  HttpOverrides.runZoned(() {
    // Operations will use MyHttpClient instead of the real HttpClient
    // implementation whenever HttpClient is used.
  }, createHttpClient: (SecurityContext? c) => MyHttpClient(c));
}
```

Constructors
------------

[HttpOverrides](httpoverrides/httpoverrides)()

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[createHttpClient](httpoverrides/createhttpclient)([SecurityContext](securitycontext-class)?
context) → [HttpClient](httpclient-class)

Returns a new [HttpClient](httpclient-class) using the given `context`.

[findProxyFromEnvironment](httpoverrides/findproxyfromenvironment)([Uri](../dart-core/uri-class)
url, [Map](../dart-core/map-class)\<[String](../dart-core/string-class),
[String](../dart-core/string-class)\>? environment) →
[String](../dart-core/string-class)

Resolves the proxy server to be used for HTTP connections.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Properties
-----------------

[current](httpoverrides/current) → [HttpOverrides](httpoverrides-class)?

::: {.features}
read-only
:::

[global](httpoverrides/global) ← [HttpOverrides](httpoverrides-class)?

::: {.features}
write-only
:::

The [HttpOverrides](httpoverrides-class) to use in the root
[Zone](../dart-async/zone-class).

Static Methods
--------------

[runWithHttpOverrides](httpoverrides/runwithhttpoverrides)\<R\>(R body(), [HttpOverrides](httpoverrides-class) overrides) → R
:   Runs `body` in a fresh [Zone](../dart-async/zone-class) using the
    overrides found in `overrides`.

[runZoned](httpoverrides/runzoned)\<R\>(R body(), {[HttpClient](httpclient-class) createHttpClient([SecurityContext](securitycontext-class)?)?, [String](../dart-core/string-class) findProxyFromEnvironment([Uri](../dart-core/uri-class) uri, [Map](../dart-core/map-class)\<[String](../dart-core/string-class), [String](../dart-core/string-class)\>? environment)?}) → R
:   Runs `body` in a fresh [Zone](../dart-async/zone-class) using the
    provided overrides.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpOverrides-class.html>
:::
