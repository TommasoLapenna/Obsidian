Tags: [[webdev]] [[Programming]]
## Primitives
- `string`
- `number`: There aren't int, float, ecc.
- `boolean`
## Arrays
- `<type>[<number>]`
- `Array<number>`
## Any
Every syntactical legal kind of operation can be performed on a variable defined as `any` (it's not type-checked), such as accessing any proprieties of it (thi will return a type of `any`), call it like a function ecc. The `noImplicitAny` flag counts any implicit `any` as error.
## Type Annotations on Variables
An additional type annotation can be added to specify the type of variables
- `const`
- `var`: Available through all the function in which they are defined
- `let`: Available only in the block where they are defined
## Functions
`function [<functionName>]([<type>]: <parameter>, ...)[: [Promise]<returnType>]{}`
## Anonymous Functions
When a function appears in a place where Typescript can determine how it's going to be called, the parameters of the function are automatically given types
## Object Types
`<objName>: {<attName>[?]: <type>[|<type>|...];...}`
with `?` the value is marked as optional (`undefined` might need to be checked). with `|`  a union type is defined, that means that the value can be of either type, but an operation on it is valid only if it's valid for every member of the union
## Type Aliases
`type <name> = <type or objectType>[|<type>|...];`
A type alias can be also used to crate different versions of a same type 
## Interfaces
`interface <name> {<attName>: <type>;...}`
whereas a type cannot be extended, in an interface is possible to ass new proprieties
- Extending an interface:  `interface <int1> extends <int2> {<attName>: <type>;...}` 
- Extending a type via intersections: `type <type1> = <type2> & {<attName>: <type>;...}`
- Adding new fields to an existing interface: `interface <existingIntName> {<attName>: <type>;...}`
Different use cases:
- type alias name may appear in error message, interfaces will always be named in error messages
- Type aliases may not participate in declaration merging, but interfaces can
- Interfaces may only be used to declare the shapes of objects, not rename primitives
-  Interface names will always appear in their original from in error messages, but only when they are used by name.
- Using interfaces with `extends` can often be more performant for the compiler than type aliases with intersections
## Type Assertions
`<type1> <name1> = <name2> as <type2> [as <type> ...]`
Because type assertions are removed at compile time, there is no runtime checking associated with a type. Type assertion can only be made to convert a more specific type to a less specific one
## Literal Types 
`<varName>: <value>[|<value>|...]`
By combining literal types with unions is possible to create a set of known values ( the same is possibile with non-literal types)
## Literal Interface 
To change a literal value in an object extra steps are needed, that's because the type of a literal is the value itself, and not string. 2 solutions:
- `"<name>" as "<name>"`
- `{...} as const`
## `null` and `undefined`
`null` and `undefined` are basically the same type, but they behave differently depending on the the `strictNullFlag`:
- Off: values that might be `null` o `undefined` can still be accessed,  `null` and `undefined` can be assigned to a propriety of any type 
- On: the `null` and `undefined` value must be tested (with an `if`). just like checking for `undefined` before using an optional propriety, it can be narrowed down to check for values that might be `null`
Adding `!` after any expression is effectively a type assertion that the value isn't `null` or `undefined`
## Enums
Enums are added in Typescript 
## Less Common Primitives
- `bigint`
- `symbol` 