# New Syntax

This parser adds certain new syntax to the language. Some come from Apache Royale, some from Samsung HARMAN, and some from other ECMAScript variants.

## Destructuring

```
const { x } = o;
[y] = o1;
```

**Non-null**: non-null operator is supported within destructuring patterns.

## Optional Chaining

```
o?.x
o?.[k]
o?.()
```

## Raw String Literal

Samsung HARMAN added a `@` prefix to string literals, designing them such that escape sequences are uninterpreted.

```
@""
```

## Triple String Literal

ECMAScript 4 introduced a triple string literal that spans multiple lines and ignores indentation.

```
const s =   """
            Text.
            """
s == "Text."
```

## Nullish Coalescing

```
x ?? y
x ??= y
```

## Non-null Operator

```
o!
```

## Keywords as Identifiers

Certain contexts allow for using any reserved word as an identifier, such as function names and variable names.

```
function default(): void {}
```

## Abstract attribute

The `abstract` attribute is valid at classes and methods.

## Static attribute

The `static` attribute is valid at classes.

## Type definition

```
type T1 = T2
```

## Enumeration definition

```
enum E1 {
    const M1
    const M2 = "m2"
    const M3 = ["m3", 10]

    function f1(): void {}
}
[Set]
enum E2 {
    const M1, M2
}
```

## Array Initializer

```
// Rest operator
[...o]
```

## Object initializer

```
// Rest operator
( { ...o } );

// Trailing comma
( { x: 10, } );

// Shorthand field
( { x } );
```

## Generators

```
function f() {
    // Yield operator
    yield 10
}
```

## Asynchronous methods

```
function f() {
    // Await operator
    await f1()
}
```

## Switch Type Statement

ECMAScript 4 introduced a `switch type` statement.

```
switch type (o) {
    case (d: Date) {
        trace(d.valueOf())
    }
    default {
        trace("Not a Date")
    }
}
```

## Configuration Directive

`configuration { ... }` means conditional compilation with `if`, `else if` and `else` branches. A limited set of expressions are valid and translate to a different syntactic construct:

* `q::x` translates to an identifier whose name is literally `"q::x"` without a qualifier.
* `x` asks whether a constant `x` is present.
* `k="v"` translates to `k == "v"`.
* `k=v` translates to `k == "v"`.
* `k!="v"` goes as is.
* `k!=v` translates to `k != "v"`.
* `x && y`
* `x || y`
* `(x)`
* `!x`

```
configuration {
    if (k=3) {
        trace("k=3")
    } else {
        trace("k!=3")
    }
}
```

## Embed Expression

```
const o: ByteArray = embed { source: "data.bin", type: "application/octet-stream" }
```

## Parameterized Types

```
class C1.<T> {}
```

## Function Type Expression

The function type expression is as is in ECMAScript fourth edition, but not including the `this` parameter.

A suffix `=` indicates an optional parameter.

```
type F = function(T, Number=, ...): T
type F = function(T, Number=, ...[T]): T
```

## Meta Properties

```
import.meta
```

## Non-Nullable Type Expression

```
type T1 = T!
```

## Nullable Type Expression

```
type T1 = T?
type T2 = ?T
```

## Void Type Expression

`void` is allowed as a type expression everywhere.

## Array Type Expression

```
type A1 = [T]
```

## Tuple Type Expression

```
type T1 = [E1, E2]
```

## Aliasing Imports

```
import x = ns.y;

// Open public of ns and set "ns1" to NamespaceSet(ns public, ns internal)
import ns1 = ns.*;
ns1::y
```

## Negated In/Is

```
k not in o
v is not T
```

## Exponentiation

```
n ** p
```

## Function Body

* Function bodies may consist of an expression. 

```
const f = function(): Number (10)
```

## Numeric Literal

* Binary literal
* Underscore separators

```
0b1011
10_000
```

## Regular Expression

* Line terminators allowed within a regular expression literal.

```
/(?:)
./m
```

## Float Suffix

Samsung HARMAN introduced a `f` suffix to the *NumericLiteral* productions.

```
0f
```
