[dart:io](../dart-io/dart-io-library){._links-link}

ProcessSignal class
===================

On Posix systems, [ProcessSignal](processsignal-class) is used to send a
specific signal to a child process, see `Process.kill`.

Some [ProcessSignal](processsignal-class)s can also be watched, as a way
to intercept the default signal handler and implement another. See
[ProcessSignal.watch](processsignal/watch) for more information.

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

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](processsignal/tostring)() →
[String](../dart-core/string-class)

::: {.features}
override
:::

A string representation of this object.

[watch](processsignal/watch)() →
[Stream](../dart-async/stream-class)\<[ProcessSignal](processsignal-class)\>

Watch for process signals.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

Constants
---------

[sigabrt](processsignal/sigabrt-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(6, "SIGABRT")`

    </div>

[sigalrm](processsignal/sigalrm-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(14, "SIGALRM")`

    </div>

[sigbus](processsignal/sigbus-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(7, "SIGBUS")`

    </div>

[sigchld](processsignal/sigchld-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(17, "SIGCHLD")`

    </div>

[sigcont](processsignal/sigcont-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(18, "SIGCONT")`

    </div>

[sigfpe](processsignal/sigfpe-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(8, "SIGFPE")`

    </div>

[sighup](processsignal/sighup-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(1, "SIGHUP")`

    </div>

[sigill](processsignal/sigill-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(4, "SIGILL")`

    </div>

[sigint](processsignal/sigint-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(2, "SIGINT")`

    </div>

[sigkill](processsignal/sigkill-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(9, "SIGKILL")`

    </div>

[sigpipe](processsignal/sigpipe-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(13, "SIGPIPE")`

    </div>

[sigpoll](processsignal/sigpoll-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(29, "SIGPOLL")`

    </div>

[sigprof](processsignal/sigprof-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(27, "SIGPROF")`

    </div>

[sigquit](processsignal/sigquit-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(3, "SIGQUIT")`

    </div>

[sigsegv](processsignal/sigsegv-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(11, "SIGSEGV")`

    </div>

[sigstop](processsignal/sigstop-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(19, "SIGSTOP")`

    </div>

[sigsys](processsignal/sigsys-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(31, "SIGSYS")`

    </div>

[sigterm](processsignal/sigterm-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(15, "SIGTERM")`

    </div>

[sigtrap](processsignal/sigtrap-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(5, "SIGTRAP")`

    </div>

[sigtstp](processsignal/sigtstp-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(20, "SIGTSTP")`

    </div>

[sigttin](processsignal/sigttin-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(21, "SIGTTIN")`

    </div>

[sigttou](processsignal/sigttou-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(22, "SIGTTOU")`

    </div>

[sigurg](processsignal/sigurg-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(23, "SIGURG")`

    </div>

[sigusr1](processsignal/sigusr1-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(10, "SIGUSR1")`

    </div>

[sigusr2](processsignal/sigusr2-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(12, "SIGUSR2")`

    </div>

[sigvtalrm](processsignal/sigvtalrm-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(26, "SIGVTALRM")`

    </div>

[sigwinch](processsignal/sigwinch-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(28, "SIGWINCH")`

    </div>

[sigxcpu](processsignal/sigxcpu-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(24, "SIGXCPU")`

    </div>

[sigxfsz](processsignal/sigxfsz-constant) → const [ProcessSignal](processsignal-class)

:   <div>

    `const ProcessSignal._(25, "SIGXFSZ")`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ProcessSignal-class.html>
:::
