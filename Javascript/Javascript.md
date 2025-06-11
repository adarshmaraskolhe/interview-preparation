```javascript
console.log("Javascript")


let x = [1,2,3].map(x => { });
console.log(x);

let x1 = [1,2,3].map(async x => { });
console.log(x1);

let x3 = [1,2,3].filter(async x => x % 2 === 0);
console.log(x3);

let x4 = [1,2,3].filter( x => x % 2 === 0);
console.log(x4);

```
# Javascript Interview Questions

## Q.1 let vs const vs var

**Answer:** 

* **let :** 
    * **Scope:** Block-scoped. Variables declared with let are only accessible within the block (e.g., inside an if statement, loop, or function) they are declared in.

    * **Reassignment:** Can be reassigned but not redeclared within its scope.
    
    * **Hoisting:** Variables declared with let are not hoisted.

    * **Temporal Dead Zone:** Has a temporal dead zone, making them inaccessible before declaration.  

    * ```javascript
        function test() {
            // console.log(b); // ReferenceError
            let b = 20;
            console.log(b); // 20
        }

    ```

* **const :** 
    * **Scope:** Block-scoped. Variables declared with let are only accessible within the block (e.g., inside an if statement, loop, or function) they are declared in.

    * **Reassignment:** Value must be initialized during declaration. Can not be reassigned and not redeclared within its scope but objects/arrays can still be mutated

    * **Hoisting:** Variables declared with const are not hoisted.

    * **Temporal Dead Zone:** Has a temporal dead zone, making them inaccessible before declaration. 

    * ```javascript
        const c = 30;
        // c = 40; // Error: Assignment to constant variable

        const obj = { x: 1 };
        obj.x = 2; // ✅ Allowed (mutation)

        ```

* **var :** 
    * **Scope:**  Function-scoped. Variables declared with var are accessible throughout the function they are declared in, even within blocks.

    * **Reassignment:** Can be reassigned and redeclared within its scope.
    
    * **Hoisting:** Variables declared with var are hoisted, meaning they can be accessed before they are declared (though their value will be undefined).
    
    * **Temporal Dead Zone:** Does not have a temporal dead zone. 

    * ```javascript
        function test() {
            console.log(a); // undefined (hoisted)
            var a = 10;
            console.log(a); // 10
        }

        ```

## Q.2 Hoisting

**Answer:** 
* Hoisting in JavaScript is a mechanism where declarations of variables, functions, and classes are moved to the top of their scope before code execution. This behavior allows you to use these elements before they are declared in your code. 

* **How Hoisting Works:**
During the compilation phase, JavaScript's engine processes the code and allocates memory for declarations. It essentially "lifts" these declarations to the top of their scope, whether it's the global scope or a function's scope. However, only the declarations are hoisted, not the initializations.


## Q.3 Temporal Dead Zone

**Answer:** 
The Temporal Dead Zone (TDZ) is a behavior in JavaScript that applies to variables declared with let and const. It refers to the period between entering the scope and the actual declaration of the variable. During this period, the variable cannot be accessed and will throw a ReferenceError if you try to use it. 


## Q.4 `==` vs `===`

**Answer:** 

* **`==`:** This operator performs type coercion if the operands have different types. It attempts to convert the operands to a common type before making the comparison. For example, it will convert a string to a number if the other operand is a number.

```js
'5' == 5        // true  (string '5' → number 5)
0 == false      // true  (false → 0)
null == undefined // true
[] == ''        // true  (both become "")
[] == 0         // true
[1] == 1        // true

```

* **`===`:** This operator does not perform any type conversion. It compares both the values and types of the operands. It will return true only if the values and types are identical.

```js
'5' === 5       // false (string vs number)
0 === false     // false (number vs boolean)
null === undefined // false
[] === ''       // false
1 === 1         // true

```

## Q.5 Closures

**Answer:** A closure in JavaScript is a function that remembers and has access to variables from its outer (enclosing) function's scope, even after the outer function has finished executing. This combination of a function and its lexical environment allows the inner function to maintain access to the outer function's variables. 

Closures are created every time a function is created in JavaScript. They enable functions to have "private" variables, encapsulate data, and create public methods to interact with it. 

```js
function outerFunction() {
  let outerVar = "Hello";
  function innerFunction() {
    console.log(outerVar);
  }
  return innerFunction;
}

let myClosure = outerFunction(); // `outerFunction` returns `innerFunction`, with access to `outerVar`

myClosure(); // Output: Hello

```

## Q.6 Spread (`...`) vs Rest (`...`)

**Answer:** 