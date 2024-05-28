[dart:async](../dart-async/dart-async-library){._links-link}

scheduleMicrotask function
==========================

::: {.section .multi-line-signature}
void scheduleMicrotask(

1.  void callback( )

)
:::

Runs a function asynchronously.

Callbacks registered through this function are always executed in order
and are guaranteed to run before other asynchronous events (like
[Timer](timer-class) events, or DOM events).

**Warning:** it is possible to starve the DOM by registering
asynchronous callbacks through this method. For example the following
program runs the callbacks without ever giving the Timer callback a
chance to execute:

``` {.language-dart data-language="dart"}
main() {
  Timer.run(() { print("executed"); });  // Will never be executed.
  foo() {
    scheduleMicrotask(foo);  // Schedules [foo] in front of other events.
  }
  foo();
}
```

Other resources
---------------

-   [The Event Loop and Dart](https://dart.dev/articles/event-loop/):
    Learn how Dart handles the event queue and microtask queue, so you
    can write better asynchronous code with fewer surprises.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma('vm:entry-point', 'call')
void scheduleMicrotask(void Function() callback) {
  _Zone currentZone = Zone._current;
  if (identical(_rootZone, currentZone)) {
    // No need to bind the callback. We know that the root's scheduleMicrotask
    // will be invoked in the root zone.
    _rootScheduleMicrotask(null, null, _rootZone, callback);
    return;
  }
  _ZoneFunction implementation = currentZone._scheduleMicrotask;
  if (identical(_rootZone, implementation.zone) &&
      _rootZone.inSameErrorZone(currentZone)) {
    _rootScheduleMicrotask(
        null, null, currentZone, currentZone.registerCallback(callback));
    return;
  }
  Zone.current.scheduleMicrotask(Zone.current.bindCallbackGuarded(callback));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/scheduleMicrotask.html>
:::
