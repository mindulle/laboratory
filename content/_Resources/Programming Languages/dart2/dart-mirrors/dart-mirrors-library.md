dart:mirrors library
====================

Basic reflection in Dart, with support for introspection and dynamic
invocation.

*Introspection* is that subset of reflection by which a running program
can examine its own structure. For example, a function that prints out
the names of all the members of an arbitrary object.

*Dynamic invocation* refers the ability to evaluate code that has not
been literally specified at compile time, such as calling a method whose
name is provided as an argument (because it is looked up in a database,
or provided interactively by the user).

How to interpret this library\'s documentation
----------------------------------------------

As a rule, the names of Dart declarations are represented using
instances of class [Symbol](../dart-core/symbol-class). Whenever the doc
speaks of an object *s* of class [Symbol](../dart-core/symbol-class)
denoting a name, it means the string that was used to construct *s*.

The documentation frequently abuses notation with Dart pseudo-code such
as `o.x(a)`, where o and a are defined to be objects; what is actually
meant in these cases is `o'.x(a')` where *o\'* and *a\'* are Dart
variables bound to *o* and *a* respectively. Furthermore, *o\'* and
*a\'* are assumed to be fresh variables (meaning that they are distinct
from any other variables in the program).

Sometimes the documentation refers to *serializable* objects. An object
is serializable across isolates if and only if it is an instance of num,
bool, String, a list of objects that are serializable across isolates,
or a map with keys and values that are all serializable across isolates.

Status: Unstable
----------------

The dart:mirrors library is unstable and its API might change slightly
as a result of user feedback. This library is only supported by the Dart
VM and only available on some platforms.

Classes
-------

[ClassMirror](classmirror-class)
:   A [ClassMirror](classmirror-class) reflects a Dart language class.

[ClosureMirror](closuremirror-class)
:   A [ClosureMirror](closuremirror-class) reflects a closure.

[CombinatorMirror](combinatormirror-class)
:   A mirror on a show/hide combinator declared on a library dependency.

[Comment](comment-class)
:   Class used for encoding comments as metadata annotations.

[DeclarationMirror](declarationmirror-class)
:   A [DeclarationMirror](declarationmirror-class) reflects some entity
    declared in a Dart program.

[FunctionTypeMirror](functiontypemirror-class)
:   A [FunctionTypeMirror](functiontypemirror-class) represents the type
    of a function in the Dart language.

[InstanceMirror](instancemirror-class)
:   An [InstanceMirror](instancemirror-class) reflects an instance of a
    Dart language object.

[IsolateMirror](isolatemirror-class)
:   An [IsolateMirror](isolatemirror-class) reflects an isolate.

[LibraryDependencyMirror](librarydependencymirror-class)
:   A mirror on an import or export declaration.

[LibraryMirror](librarymirror-class)
:   A [LibraryMirror](librarymirror-class) reflects a Dart language
    library, providing access to the variables, functions, and classes
    of the library.

[MethodMirror](methodmirror-class)
:   A [MethodMirror](methodmirror-class) reflects a Dart language
    function, method, constructor, getter, or setter.

[Mirror](mirror-class)
:   A [Mirror](mirror-class) reflects some Dart language entity.

[MirrorsUsed](mirrorsused-class){.deprecated}
:   Annotation describing how \"dart:mirrors\" is used (EXPERIMENTAL).

[MirrorSystem](mirrorsystem-class)
:   A [MirrorSystem](mirrorsystem-class) is the main interface used to
    reflect on a set of associated libraries.

[ObjectMirror](objectmirror-class)
:   An [ObjectMirror](objectmirror-class) is a common superinterface of
    [InstanceMirror](instancemirror-class),
    [ClassMirror](classmirror-class), and
    [LibraryMirror](librarymirror-class) that represents their shared
    functionality.

[ParameterMirror](parametermirror-class)
:   A [ParameterMirror](parametermirror-class) reflects a Dart formal
    parameter declaration.

[SourceLocation](sourcelocation-class)
:   A [SourceLocation](sourcelocation-class) describes the span of an
    entity in Dart source code.

[TypedefMirror](typedefmirror-class)
:   A [TypedefMirror](typedefmirror-class) represents a typedef in a
    Dart language program.

[TypeMirror](typemirror-class)
:   A [TypeMirror](typemirror-class) reflects a Dart language class,
    typedef, function type or type variable.

[TypeVariableMirror](typevariablemirror-class)
:   A [TypeVariableMirror](typevariablemirror-class) represents a type
    parameter of a generic type.

[VariableMirror](variablemirror-class)
:   A [VariableMirror](variablemirror-class) reflects a Dart language
    variable declaration.

Functions
---------

[currentMirrorSystem](currentmirrorsystem)() → [MirrorSystem](mirrorsystem-class)
:   Returns a [MirrorSystem](mirrorsystem-class) for the current
    isolate.

[reflect](reflect)(dynamic reflectee) → [InstanceMirror](instancemirror-class)
:   Reflects an instance.

[reflectClass](reflectclass)([Type](../dart-core/type-class) key) → [ClassMirror](classmirror-class)
:   Reflects a class declaration.

[reflectType](reflecttype)([Type](../dart-core/type-class) key, \[[List](../dart-core/list-class)\<[Type](../dart-core/type-class)\>? typeArguments\]) → [TypeMirror](typemirror-class)
:   Reflects the type represented by `key`.

Exceptions / Errors {#exceptions}
-------------------

[AbstractClassInstantiationError](../dart-core/abstractclassinstantiationerror-class){.deprecated}
:   Error thrown when trying to instantiate an abstract class.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/dart-mirrors-library.html>
:::
