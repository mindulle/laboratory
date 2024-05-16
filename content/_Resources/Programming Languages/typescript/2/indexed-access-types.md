Indexed Access Types
====================

We can use an *indexed access type* to look up a specific property on
another type:

```ts
type Person = { age: number; name: string; alive: boolean };
type Age = Person["age"];
```

The indexing type is itself a type, so we can use unions, `keyof`, or
other types entirely:

```ts
type I1 = Person["age" | "name"];
 
type I2 = Person[keyof Person];
 
type AliveOrName = "alive" | "name";
type I3 = Person[AliveOrName];
```

You'll even see an error if you try to index a property that doesn't
exist:

```ts
type I1 = Person["alve"];
```

Another example of indexing with an arbitrary type is using `number` to
get the type of an array's elements. We can combine this with `typeof`
to conveniently capture the element type of an array literal:

```ts
const MyArray = [
  { name: "Alice", age: 15 },
  { name: "Bob", age: 23 },
  { name: "Eve", age: 38 },
];
 
type Person = typeof MyArray[number];
type Age = typeof MyArray[number]["age"];
// Or
type Age2 = Person["age"];
```

You can only use types when indexing, meaning you can't use a `const` to
make a variable reference:

```ts
const key = "age";
type Age = Person[key];
```

However, you can use a type alias for a similar style of refactor:

```ts
type key = "age";
type Age = Person[key];
```

 
© 2012-2023 Microsoft\
Licensed under the Apache License, Version 2.0.\
https://www.typescriptlang.org/docs/handbook/2/indexed-access-types.html>

