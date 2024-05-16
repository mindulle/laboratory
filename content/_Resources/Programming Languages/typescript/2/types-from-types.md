Creating Types from Types
=========================

TypeScript's type system is very powerful because it allows expressing
types *in terms of other types*.

The simplest form of this idea is generics. Additionally, we have a wide
variety of *type operators* available to use. It's also possible to
express types in terms of *values* that we already have.

By combining various type operators, we can express complex operations
and values in a succinct, maintainable way. In this section we'll cover
ways to express a new type in terms of an existing type or value.

-   [Generics](generics) - Types which take parameters
-   [Keyof Type Operator](keyof-types) - Using the `keyof` operator to
    create new types
-   [Typeof Type Operator](typeof-types) - Using the `typeof` operator
    to create new types
-   [Indexed Access Types](indexed-access-types) - Using `Type['a']`
    syntax to access a subset of a type
-   [Conditional Types](conditional-types) - Types which act like if
    statements in the type system
-   [Mapped Types](mapped-types) - Creating types by mapping each
    property in an existing type
-   [Template Literal Types](template-literal-types) - Mapped types
    which change properties via template literal strings

 
© 2012-2023 Microsoft\
Licensed under the Apache License, Version 2.0.\
https://www.typescriptlang.org/docs/handbook/2/types-from-types.html>

