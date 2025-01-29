Tags: [[Typescript]] [[webdev]] [[Programming]] 

## Function Type Expressions
`function <name>(fn: (<proprietyName>: <type1>,...) => <type2>)`. 
The syntax means that it is a function takes a parameter with a `<type1>` type and returns a value of `<type2>` value. An alias can be assigned to a function type: `type <name> = (fn: (<proprietyName>: <type1>,...) => <type2>)`.
If a parameter type isn't specified, it's implicitly `any`
## Call Signatures
Functions can have proprieties in addition to be callable 
`type <name1> = {...; (<arg>: <name2>): <type>;...}`
`function <name>(fn: <name1>){}`
The syntax is slightly different compared to a function type expression, `:` is used between the parameters and the return type rather than `=>`
## Construct Signatures
With the `new` keyword in front of a call signature it is possible to construct a signature
`type <constName> = {new <arg>: <name>): <objName>}`
`function fn(ctor: <constName>){}`
## Generic Functions
In Typescript generics are used when a corrispondence between two values needs to be described. With a type parameter and `Type`:
`function <name><Type>(<arg>: <Type>): Type | undefined`
by using `Type` in two places , a link between the input and the output of the function is created.
The type in `Type` is inferred.
The `Type` can be constrained by writing an `extend` clause
...
## Optional Parameters
an optional parameter is marked with `?` before in the parameter. the parameter type will be `<type>|undefined`. A parameter can also have a default value `<parameter> = <value>`.
## Function Overload
overloading
## `this` in a Function 
A parameter called `this` cannot appear in the parameters list

