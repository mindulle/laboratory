[dart:core](../dart-core/dart-core-library){._links-link}

WeakReference\<T extends Object\> class
=======================================

A weak reference to a Dart object.

A *weak* reference to the [target](weakreference/target) object which
may be cleared (set to reference `null` instead) at any time when there
is no other way for the program to access the target object.

*Being the target of a weak reference does not keep an object from being
garbage collected.*

There are no guarantees that a weak reference will ever be cleared even
if all references to its target are weak references.

Not all objects are supported as targets for weak references. The
[WeakReference](weakreference-class) constructor will reject any object
that is not supported as an [Expando](expando-class) key.

Use-cases like caching can benefit from using weak references. Example:

``` {.language-dart data-language="dart"}
/// [CachedComputation] caches the computation result, weakly holding
/// on to the cache.
///
/// If nothing else in the program is holding on the result, and the
/// garbage collector runs, the cache is purged, freeing the memory.
///
/// Until the cache is purged, the computation will not run again on
/// a subsequent request.
///
/// Example use:
/// ```
/// final cached = CachedComputation(
///     () => jsonDecode(someJsonSource) as Object);
/// print(cached.result); // Executes computation.
/// print(cached.result); // Most likely uses cache.
/// ```
class CachedComputation<R extends Object> {
  final R Function() computation;

  WeakReference<R>? _cache;

  CachedComputation(this.computation);

  R get result {
    final cachedResult = _cache?.target;
    if (cachedResult != null) {
      return cachedResult;
    }

    final result = computation();

    // WeakReferences do not support nulls, bools, numbers, and strings.
    if (result is! bool && result is! num && result is! String) {
      _cache = WeakReference(result);
    }

    return result;
  }
}
```

Annotations

:   -   \@Since(\"2.17\")

Constructors
------------

[WeakReference](weakreference/weakreference)(T target)

::: {.constructor-modifier .features}
factory
:::

Creates a [WeakReference](weakreference-class) pointing to the given
`target`.

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[target](weakreference/target) → T?

::: {.features}
read-only
:::

The current object weakly referenced by [this](weakreference-class), if
any.

Methods {#instance-methods}
-------

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](object/tostring)() → [String](string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/WeakReference-class.html>
:::
