# Programming languages

### Built-in
#### Value properties 
| Names    | JS/TS        | Go  |
| --- | ------------ | --- |
| globalthis    | `globalThis` |     |
| infinity    | `Infinity`   |     |
| nan    | `NaN`        |     |
| undefined    | `undefined`  |     |
#### Function properties 
| Names | JS/TS | Go |
| ---- | ---- | ---- |
| eval | `eval()` |  |
| isfinite | `isFinite()` |  |
| isnan | `isNaN()` |  |
| parsefloat | `parseFloat()` |  |
| parseint | `parseInt()` |  |
| decodeuri | `decodeURI()` |  |
| decodeuricomponent | `decodeURIComponent()` |  |
| encodeuri | `encodeURI()` |  |
| encodeuricomponent | `encodeURIComponent()` |  |
| unescape | `unescape()` |  |
#### Fundamental objects 
| Names    | JS/TS      | Go  |
| --- | ---------- | --- |
| object    | `Object`   |     |
| function    | `Function` |     |
| boolean    | `Boolean`  |     |
| symbol    | `Symbol`   |     |
#### Error objects 
| Names | JS/TS            | Go  |
| ---------- | ---------------- | --- |
| error           | `Error`          | `error`    |
| aggregateerror           | `AggregateError` |     |
| evalerror           | `EvalError`      |     |
| rangeerror           | `RangeError`     |     |
| referenceerror           | `ReferenceError` |     |
| syntaxerror           | `SyntaxError`    |     |
| typeerror           | `TypeError`      |     |
| urierror           | `URIError`       |     |
#### Numbers and dates
| Names    | JS/TS    | Go            |
| --- | -------- | ------------- |
| number    | `Number` |               |
| bigint    | `BigInt` |               |
| math    | `Math`   | `math` package              |
| date    | `Date`   | `time` package |
#### Text processing
| Names | JS/TS | Go  |
| ---------- | ---------- | --- |
| string           | `String`   | `string`    |
| regexp           | `RegExp`   | `regexp` package    |
#### Indexed collections
| Names | JS/TS          | Go  |
| ---------- | ------------------- | --- |
| array           | `Array`             | `slice`    |
| int8array           | `Int8Array`         | `int8` slice    |
| uint8array           | `Uint8Array`        | `uint8` slice    |
| uint8clampedarray           | `Uint8ClampedArray` | `uint8` slice with clamping    |
| uint16array           | `Int16Array`        | `int16` slice    |
| uint16array           | `Uint16Array`       | `uint16` slice    |
| int32array           | `Int32Array`        | `int32` slice    |
| uint32array           | `Uint32Array`       | `uint32` slice    |
| bigint64array           | `BigInt64Array`     | `int64` slice (for signed integers) with `big.Int` for arbitrary precision    |
| biguint64array           | `BigUint64Array`    | `uint64` slice with `big.Int` for arbitrary precision    |
| float32array           | `Float32Array`      | `float32` slice    |
| float64array           | `Float64Array`      | `float64` slice    |
#### Keyed collections
| Names | JS/TS | Go |
| ---- | ---- | ---- |
| map | `Map` | `map` |
| set | `Set` | `map` (using keys with a dummy value) |
| weakmap | `WeakMap` |  |
| weakset | `WeakSet` |  |
#### Structured data
| Names | JS/TS               | Go  |
| ----- | ------------------- | --- |
| arraybuffer      | `ArrayBuffer`                    |     |
| sharedarraybuffer      | `SharedArrayBuffer` |     |
| dataview      | `DataView`          |     |
| atomics      | `Atomics`           |     |
| json      | `JSON`              | `encoding/json` package    |
#### Managing memory
| Name    | JS/TS                  | Go  |
| --- | ---------------------- | --- |
| weakref    | `WeakRef`              | `GC`    |
| finalizationregistry    | `FinalizationRegistry` | `GC`    |
#### Control abstraction objects
| Names | JS/TS | Go |
| ---- | ---- | ---- |
| iterator | `Iterator` | usually use |
| asynciterator | `AsyncIterator` | `goroutines, ` |
| promise | `Promise` | `and channel` |
| generatorfunction | `GeneratorFunction` | for control |
| asyncgeneratorfunction | `AsyncGeneratorFunction` | abstraction |
| generator | `Generator` | and |
| asyncgenerator | `AsyncGenerator` | asynchronous |
| asyncfunction | `AsyncFunction` | programming |

#### Reflection
| Names    | JS/TS     | Go  |
| --- | --------- | --- |
| reflect    | `Reflect` | `reflect` package    |
| proxy    | `Proxy`   |     |
#### Internationalization
| Names | JS/TS | Go |
| ---- | ---- | ---- |
| intl | `Intl` | `golang.org/x/text` |
| collator | `Intl.Collator` |  |
| datetimeformat | `Intl.DateTimeFormat` |  |
| displaynames | `Intl.DisplayNames` |  |
| durationformat | `Intl.DurationFormat` |  |
| listformat | `Intl.ListFormat` |  |
| locale | `Intl.Locale` |  |
| numberformat | `Intl.NumberFormat` |  |
| pluralrules | `Intl.PluralRules` |  |
| relativetimeformat | `Intl.RelativeTimeFormat` |  |
| segmenter | `Intl.Segmenter` |  |
### Statements
#### Control flow
| Names | JS/TS         | Go  |
| ---------- | ------------- | --- |
| return           | `return`      | `return`    |
| break           | `break`       | `break`    |
| continue           | `continue`    | `continue`    |
| throw           | `throw`       | `panic` (for exceptional cases)    |
| if...else           | `if...else`   | `if...else`    |
| switch           | `switch`      | `switch`    |
| try...catch           | `try...catch` | `defer`, `panic`, and `recover` mechanism    |
#### Declaring variables
| Names | JS/TS   | Go                                                         |
| ----- | ------- | ---------------------------------------------------------- |
| var(local)   | `var`   | `:=` Recommended.                   |
| var(global)      |         | `var` Not Recommended.           |
| let(local)   | `let`   | `:=`  |
| let(global)      |         | `var`                                                           |
| const | `const` | `const`                                                    |
#### Functions and classes
| Names    | JS/TS             | Go  |
| --- | ----------------- | --- |
| function    | `function`        | `func`    |
| function generator    | `function*`       |     |
| asynchronous function    | `async function`  | `go func`    |
| asynchronous function generator    | `async function*` |     |
| class    | `class`           | `struct` with `pointer receivers`    |
#### Iterations
| Names | JS/TS | Go |
| ---- | ---- | ---- |
| do...while | `do...while` | use `for` with a condition |
| for | `for` | `for` |
| for...in | `for...in` | use `range` with a map or slice |
| for...of | `for...of` | use `range` with a slice or array) |
| for-await...of | `for await...of` |  |
| while | `while` | use `for` with a condition |

#### Others
| Names | JS/TS | Go |
| ---- | ---- | ---- |
| empty | Empty | use an empty statement `;` |
| block | Block | use curly braces `{}` for blocks |
| expression_statement | Expression statement | include expressions directly |
| debugger | `debugger` | external tools or `fmt.Println` |
| export | `export` | determined by the capitalization |
| import | `import` | `import` |
| label | label | use labels for `goto` statements |
| with | `with` (deprecated) |  |
### Expressions and operators
#### Primary expressions
| Names    | JS/TS             | Go  |
| --- | ----------------- | --- |
| this    | `this`            |     |
| literals    | Literals          | similar to JavaScript    |
| array    | `[]`              | `[]`    |
| object initializer    | `{}`              | `map[string]interface{}`    |
| function    | `function`        | `func`    |
| class    | `class`           |     |
| function generator    | `function*`       |     |
| async function    | `async function`  |     |
| async function generator    | `async function*` |     |
| regexp    | `/ab+c/i`         | `regexp.MustCompile("ab+c")`    |
| template_literals    | `` `string` ``    | use concatenation or the `fmt` package    |
| grouping    | `( )`             | `( )`    |
#### Left-hand-side expressions
| Names    | JS/TS              | Go  |
| --- | ------------------ | --- |
| property accessors    | Property accessors | use struct fields or map access    |
| optional chaining    | `?.`               | use if statements or helper function    |
| new    | `new`              | `new`    |
| new.target    | `new.target`       | use `reflect` package    |
| import.meta    | `import.meta`      |     |
| super    | `super`            |     |
| import    | `import()`         | `import`    |
#### Increment and decrement
| Names    | JS/TS | Go  |
| --- | ----- | --- |
| increment    | `A++` | `A++`    |
| decrement    | `A--` | `A--`    |
| increment    | `++A` | `++A`    |
| decrement    | `--A` | `--A`    |
#### Unary operators
| Names    | JS/TS    | Go  |
| --- | -------- | --- |
| delete    | `delete` | `delete`    |
| void    | `void`   |     |
| typeof    | `typeof` | `typeof`    |
| unary_plus    | `+`      | `+` |
| unary_negation    | `-`      | `-` |
| bitwise_not    | `~`      | `^`    |
| logical_not    | `!`      | `!`    |
| await    | `await`  | `go`    |
#### Arithmetic operators
| Name    | JS/TS | Go |
| --- | ---------- | ---------- |
| exponentiation    | `**`       | `math.Pow()` (for floating-point numbers)           |
| multiplication    | `*`        | `*`           |
| division    | `/`        | `/`           |
| remainder    | `%`        | `%`           |
| addition    | `+`        | `+`           |
| subtraction    | `-`        | `-`           |
#### Relational operators
| Names    | JS/TS              | Go    |
| --- | ------------------ | --- |
| Less than    | `<`     | `<`    |
| Greater than    | `>`  | `>`    |
| less than or equal    | `<=`               | `<=`    |
| greater than or equal    | `>=`               | `>=`    |
| instanceof    | `instanceof`       |     |
| in    | `in`               |     |
#### Equality operators
| Names    | JS/TS | Go    |
| --- | ----- | --- |
| equality    | `==`  | `==`    |
| inequality    | `!=`  | `!=`    |
| strict equality    | `===` | `==` (for most types)    |
| strict inequality    | `!==` | `!=` (for most types)    |
#### Bitwise shift operators
| Names    | JS/TS | Go  |
| --- | ----- | --- |
| left shift    | `<<`  | `<<`    |
| right shift    | `>>`  | `>>`    |
| unsigned right shift    | `>>>` |     |
#### Binary bitwise operators
| Sign    | JS/TS | Go    |
| --- | ----- | --- |
| `&`    | bitwise_and   | address of / create pointer    |
| `\|`    | bitwise_or  | dereference pointer    |
| `^`    | bitwise_xor   | send / receive operator    |
#### Binary logical operators
| Name    | JS/TS  | Go    |
| --- | ------ | --- |
| Logical and    | `&&`   | `&&`    |
| Logical or    | `\|\|` | `\|\|`    |
| Nullish Coalescing    | `??`   |     |
#### Conditional (ternary) operator
| Names | JS/TS | Go |
| ---- | ---- | ---- |
| ternary operator | `(condition ? ifTrue : ifFalse)` |  |

#### Assignment operators
| Name | JS/TS | Go |
| ---- | ---- | ---- |
| assignment | `=` | `=` |
| multiplication assignment | `*=` | `*=` |
| division assignment | `/=` | `/=` |
| remainder assignment | `%=` | `%=` |
| addition assignment | `+=` | `+=` |
| subtraction assignment | `-=` | `-=` |
| left shift assignment | `<<=` | `<<=` |
| right shift assignment | `>>=` | `>>=` |
| unsigned right shift assignment | `>>>=` |  |
| bitwise and assignment | `&=` | `&=` |
| bitwise xor assignment | `^=` | `^=` |
| bitwise or assignment | `\|=` | `\|=` |
| exponentiation assignment | `**=` |  |
| logical and assignment | `&&=` |  |
| logical or assignment | `\|\|=` |  |
| nullish coalescing assignment | `??=` |  |
| destructuring assignment | `[a, b] = arr`,  `{ a, b } = obj` |  |
#### Yield operators
| Names | JS/TS | Go |
| ---- | ---- | ---- |
| yield | `yield` |  |
| yield generator | `yield*` |  |
#### Spread syntax
| Name    | JS/TS    | Go    |
| --- | -------- | --- |
| spread syntax    | `...obj` |     |
#### Comma operator 
| Name    | JS/TS | Go    |
| --- | ----- | --- |
| comma operator    | `,`   | `,`    |
### Functions
| Names | JS/TS | Go |
| ---- | ---- | ---- |
| Arrow Functions | `() => expression` | `func() expression` |
| Default parameters | `function fnName(param1 = defaultValue1, /* …, */ paramN = defaultValueN) {}` | define a function with variadic parameters |
| Rest parameters | `function f(a, b, ...theArgs) {}` | Variadic parameters in Go: `func(a, b int, theArgs ...int)` |
| arguments | `arguments[n]; // nth argument` | methods are defined on types in Go. |
| Method definitions | `({ property(parameters) {}, })` | methods are defined on types in Go. |
| Method definitions - with computed keys | `({ [expression](parameters) {}, })` |  |
| getter - property | `{ get prop() { /* … */ } }`, | use regular functions or methods |
| getter - expression | `{ get [expression]() { /* … */ } }` |  |
| setter - property | `{ set prop(val) { /* … */ } }` | use regular functions or methods |
| setter - expression | `{ set [expression](val) { /* … */ } }` |  |
### Classes
| Names | JS/TS | Go |
| ---- | ---- | ---- |
| `constructor` | `constructor(argument0, argument1, /* …, */ argumentN) { /* … */ }` | `type ClassName struct { // define a struct  }` then `func NewClassName() *ClassName { return &ClassName { key: val }}` - use builder pattern |
| `extends` | `class ChildClass extends ParentClass { /* … */ }` | `type ChildStruct struct { ParentStruct /* … */ }` |
| Private properties | (under proposal) in class, `#privateField;`   `#privateMethod() { // … }`  | (No direct equivalent, but you can use unexported fields/methods) |
| Public class fields | in class,  `instanceField;`, `static staticField;` | In a struct, `InstanceField Type` and `StaticField Type` |
| static | in class, class `static staticField;` | In a struct, `StaticField Type` |
| Static initialization blocks | `class ClassWithSIB { static { // …  } }` | initialization logic can be placed in an `init` function or handled at runtime. |
### Additional reference pages
- [[_Resources/Programming Languages/javascript/index#Additional reference pages|javascript]]
- [[_Resources/Programming Languages/typescript/index|Typescript]]
- [[_Resources/Programming Languages/go/index#Other packages|go]]
- [[_Resources/Programming Languages/dart2/index|dart2]]

