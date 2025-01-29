Tags: [[Typescript]] [[webdev]] [[Programming]]

## `typeof` type guards
`typeof` return strings: 
- `"string"`
- `"number"`
- `"bigint"`
- `"boolean"`
- `"symbol"`
- `"undeifned"`
- `"object"`
- `"function"`
## Truthiness Narrowing 
The following values coerce all to `false`:
- `0`
- `NaN`
- `""`
- `0n`
- `null`
- `undeifned`
All other values get coerced to `true`. Any value can be coerced to `boolean` by running them through the `Boolean` function or putting `!!` in front.
It can be useful for guarding values like `null` by comparing them to `false`
## Equality Narrowing 
Typescript also uses `switch` and equality checks (`===` strict equality ,`!==`,`==` loose equality,`!=`) to narrow types. Checking something `== null` also checks if it's potentially `undefined` (and viceversa).
## The `in` Operator Narrowing
`in` checks if an object or its prototype has a propriety with a name 
## `instanceof` Narrowing 
`<name1> instanceof <name2>` checks whether the prototype chain of `<name1>` contains `<name1>.prototype`. `instanceof` is also a type guard 
## Assignments
Typescript loos at the right side of the assignment and narrows the left side appropriately
## Control Flow Analysis
If because of a type guard a part of the union set can't reach the rest of the function, the set is narrowed to what can still go through the function.
When a variable is analized, control flow can split off and re-merge over and over again, and that variable can be observed to have a different type at each point
## Using Type Predicates
`<parameterName> is <type>`, parameterName must be the name of a parameter from the current function signature. Anytime the function containing the predicate is called, the variable in question will be narrowed to a specific type of the origial type.
## Assert Functions
Types can also be narrowed using assert functions
## Discriminated Unions
When every type in a union contains a common propriety with literal types, Typescript considers that to be a discriminated union, and can narrow out the members pf the union
## The `never` Type 
When all the options of a union have been narrowed, and so all the possibilities have been removed, the `never` type represent a state which shouldn't exists
## Exhaustiveness checking
The `never` type is assignable to every type, however no type is assignable to `never`. This means that it can be relied on to turn up to do exhaustive checking in a `swithc` statement
