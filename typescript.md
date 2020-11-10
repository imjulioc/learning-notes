# TypeScript

- Install as dev dependency
- Supports *_* for large numbers legibility
- Supports *enum* types
- Semicolon *:* for type inference

## Type system

- Extends ES primitives types (number, string, boolean)
- *null*
- *undefined*
- *void*
- *array*
- *tuple*
- *object*

## Typing

Examples:

```
let a: number = 5
```

```
const sum: (n: number, m: number) ⇒ number
sum = (n, m) ⇒ n + m
```

## Classes

Computed properties by *get* and *set* functions.

### Properties modifiers

- *private* modifier (TypeScript)
- *#* modifier (ECMAScript)
- *readonly* similar to **final** in **Java**
- *protected* similar to *private* but still allows to access a inherited property

### Class modifiers

- *abstract* abstract classes, similar to **Java**

### Class inheritance

- *constructor* method must call super() if implementing new *attributes*

## Types

You can create your own types with the keyword "type". Example:

```
type UserData = {
 username: string, password: string
}
```

- *|* union and discrimination
- *&* intersection

## Interfaces

Interfaces are similar to types, but more oriented to POO. They support access modifiers and inheritance like classes.

You could have hybrid interfaces as:

```
interface Foo {
 c: (x, y) => number,
 name: string,
}
```

wich means Foo is a callable and also has an attribute *name*.

### Casting

Using the keyword *as*. Example:

```
function foo(x: SomeInterface) {
 let y = x as OtherInterface
 ....
}
```

### Guards

Using the keyword *is*. Example:

```
function isThisType(x: SomeInterface): x is OtherInterface {
 return x.attributeInSomeInterface && x.attributeInOtherInterface
}
```

## Generics

TypeScript supports generics type.

Example:

```
interface X<T> {
 a: T
}
const b: X<string>
```

```
function someFunction<T>(a: T): T {...}
someFunction<string>("Hello")
```

*Note: TS allows to use verbosity names for generics, so it is recommended to use it, instead of just "T"*
