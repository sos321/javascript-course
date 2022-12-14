## Notes for the JS Behind the Scenes section

- JS Behind the Scenes
  - Call stack - code is executed here
  - Heap - objects are stored here
  - JIT Compiled language
    - Parsing - creates abstract syntax tree from code
    - Compilation - converts to machine code
    - Execution - executes rightaway
    - Optimization - during execution optimizes the machine code
  - Web APIs - functionality provided by the browser engines
  - Execution context - envirovment in which piece of code is executed, stores all the neccesary information for that
    - Variable Envirovment
    - Scope chain
    - this keyword
  - Call stack - place where execution contexts get stacked to keep track where we are in execution
  - Scoping - area in which a ceartain variable is available
    - Global scope
    - Function scope
    - Block scope
  - Hoisting - scanning the code for variables/function so they can be executed before declaration
    - functions are hoisted
    - let & const NOT hoisted
      - TDZ - Temporal death zone (we cannot access variable before declaration)
  - `this`keyword - special variable created for every execution context
    - not static (value can change depending on situation)
      - method - value of the object calling the method
      - simple function - no value
      - Event listener - value of the DOM element attached to
  - Method borrowing - copying a method from one object to antoher
  - Arrow func x Regular func
    - Arrow funcs **don’t** get \*\*\*\*their own this keyword
      - Never use an arrow function for methods
    - Arrow funcs are used in nested funcs inside a method to inherit the this object
    - Arrow funcs don’t get the arguments object
  - Primitives (number, string, bool, ...) x Objects (Reference values) (object literal, array, function, ...)
    - Primitives stored in the E**xecution contexts** x Objects stored in the **Heap**
    - primitives hold memory address in the stack, not the actual value
    - reference values hold the memory address in the stack that points to the memory address in the heap that stores the Object
    - const [reference values] can be changed because we are not changing the memory address
    - `Object.assign` - merges two objects into a one really new object (used for shallow coping only)
    - Deep cloning is done with external libraries
