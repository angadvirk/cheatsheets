# JavaScript
1. Higher-order function is a function that does at least one of the following: takes one or more functions as arguments (i.e., procedural parameters), or returns a function as its result.

2. Pure functions: No-side effects. Used a lot in Functional Programming.

3. Curry: f(n, m) → f’(n)(m)
https://blog.benestudio.co/currying-in-javascript-es6-540d2ad09400 
```javascript
multiply = (n, m) => (n * m)
multiply(3, 4) === 12 // true 
curryedMultiply = (n) => ( (m) => multiply(n, m) )
triple = curryedMultiply(3)
triple(4) === 12 // true
```

4. Immutability: `splice()` method changes the original array where as `slice()` doesn’t change the original array and returns a new one.

5. Hoisting: Declaration at top.

6. Event Bubbling

7. `undefined` vs. `null`:
- `undefined`: the default value for a variable that doesn't have a value assigned to it, or a function that doesn't return anything.
- `null`: similar idea (represents an empty value), but it is something that the developer assigns explicitly.

8. `===` vs. `==`
- `==` is abstract comparison. Runs a type conversion before performing the comparison. Most linters tell you to never use it, as it is weird.
- `===` is strict equality, which checks for equality on both the type and value, which gives you much more predictable behavior.

9. Event delegation

10. `null` object typeof

11. `defer` attribute in `script` tag: forces the script to be loaded and executed only once the document has fully loaded. 

12. Primitives: fundamental building blocks of JavaScript. They are immutable, meaning that their value can't be changed directly. The variable containing them can be reassigned a different value though.
- `string`
- `number`
- `boolean`
- `null`
- `undefined`

13. JavaScript is a dynamic, weakly-typed language, so we don't use type annotations.

14. Objects: represent more complex data structures like arrays, custom objects, functions, etc. Objects are a collection of keys & values or properties, and can be mutated after being assigned to a variable. 

15. If something is not a primitive type, then it inherits from `object`.

16. Conditional statements: `if (condition)`, `else`, `else if (condition)`.

17. JavaScript always tries to coerce a value into a Boolean when encountered within a conditional statement. 'truthy' values are converted to `true`, while 'falsy' values become `false`.

18. Anything that is an object is truthy, even empty arrays and empty objects. So:
```javascript
!! {} // true
!! [] // true
```

19. A string that has length > 0 will be truthy, but an empty string (`""` or `''`) will be falsy.

20. The number `0` is falsy, but all other numbers are truthy.

21. `!!` can be used before a value or variable to coerce it to Boolean yourself.

22. `&&` represents a logical AND. `||` is a logical OR.

23. Ternary operator: shorthand syntax for `if` / `else`. 

24. `switch` statements.

(To be continued...)

# ES6
`var` is hoisted to the top of the current scope.

`let` is block level.

`const` is similar, but once assigned a value, you cannot assign it another value.

When using spread, you are expanding a single variable into more:

```javascript
var abc = ['a', 'b', 'c'];
var def = ['d', 'e', 'f'];
var alpha = [ ...abc, ...def ];
// alpha == ['a', 'b', 'c', 'd', 'e', 'f'];
```

When using rest arguments, you are collapsing all remaining arguments of a function into one array:

```javascript
function sum( first, ...others ) {
    for ( var i = 0; i < others.length; i++ )
        first += others[i];
    return first;
}
// sum(1, 2, 3, 4) == 10;
```

