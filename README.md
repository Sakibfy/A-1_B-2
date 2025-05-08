
# 🎯 TypeScript Insights: Understanding keyof and any | unknown | never Types.






## FAQ ?

#### Why Use keyof?
 It provides a way to write safer, more generic functions by ensuring only valid property names are used.


#### Difference Between any, unknown, and never in TypeScript

Understanding these three fundamental types helps avoid unsafe code and improves type safety.

📌 any — Turn Off Type Checking

.Use Case: When you want to opt-out of type checking.

. Behavior: Disables all TypeScript safety.

📌 unknown — Safe Alternative to any

. Use Case: When a value’s type isn’t known at declaration but you don’t want to lose type safety.

.Behavior: Requires type checking before usage.

📌 never — Represents the Impossible
. 
Use Case: For functions that never return (e.g., they throw or loop forever).

. Behavior: Indicates unreachable code or failure scenarios.

🧠 Final Thoughts

.keyof improves generic function safety by narrowing inputs to known keys.

.Understanding the differences between any, unknown, and never is crucial for writing safe, predictable TypeScript code.

### How you can declare a explicit variables in Typescript?
 In typeScript, you can declare static variables using the colons (:) followed by the data type of the explicit type. You can not assign a value of some other data type to a static variable. The values of the same data type can be assigned.

### Describe the "any" type in TypeScript?

The any data type will allow you to assign the value of any data type to a variable. Sometimes, when the data is coming from other resouces like API call or user entered data. In that case, you may not aware of the type of the data so you can use the any data type to assign the value of any kind to a variable.

### What are the advantages of using TypeScript?
 There are a lot of advantages of using TypeScript, some of them are listed below:

The TypeScript code can compile down to the JavaScript code that is runnable on every browser.
It allow us to declare strongly or statically typed variables.
It consist of advanced features like code completion, intelliSense etc.
It supports namespace concept with the help of modules.
TypeScript throw errors at the compilation time during development unlike of JavaScript that shows errors at the runtime.

### List some disadvantages of using TypeScript?

There also exist some disadvantages of using TypeScript as listed below:

The concept of abstract classes is not supported by TypeScript.
Code Compilation is a time taking process in TypeScript.
A extra step of converting the TypeScript code into JavaScript code requires while running TypeScript.
A definition file needs to be added for using any external or third party library. All the external libraries not have the definition file.
The quality of all the definition files need to be correct.

### Explain the void type in TypeScript?

It is just opposite of any type. The void type represents the unavailability of the data type for any variable. It is mainly used with the functions that returns nothing. The variables defined using the void keyword can only be assigned with the null and undefined values.